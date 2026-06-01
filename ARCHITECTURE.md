# Afyalugha: Technical Architecture

## System Overview

Afyalugha is a multi-channel Swahili AI health assistant built on a fine-tuned NLP pipeline, served through WhatsApp, SMS, and a web interface.

---

## High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                      USER INTERFACES                            │
│                                                                 │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────────┐   │
│  │ WhatsApp │  │   SMS    │  │   Web    │  │ Speech-to-   │   │
│  │  (Cloud  │  │ (Africa's│  │   App    │  │ Text (opt.)  │   │
│  │   API)   │  │ Talking) │  │(Streamlit│  │              │   │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘  └──────┬───────┘   │
└───────┼─────────────┼─────────────┼────────────────┼───────────┘
        │             │             │                │
┌───────▼─────────────▼─────────────▼────────────────▼───────────┐
│                   API GATEWAY (FastAPI)                         │
│              Rate limiting │ Auth │ Request routing             │
└─────────────────────────┬───────────────────────────────────────┘
                          │
┌─────────────────────────▼───────────────────────────────────────┐
│               SWAHILI NLP PIPELINE                              │
│                                                                 │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │ 1. Preprocessing                                         │  │
│  │    Text normalization │ Swahili tokenization             │  │
│  │    Coastal dialect handling │ Code-switching detection   │  │
│  └──────────────────────────┬───────────────────────────────┘  │
│                             │                                   │
│  ┌──────────────────────────▼───────────────────────────────┐  │
│  │ 2. Named Entity Recognition (Medical NER)                │  │
│  │    Fine-tuned NLLB-200 on Swahili medical corpus         │  │
│  │    Entities: symptoms, medications, body parts,          │  │
│  │    diseases, dosages, temporal expressions               │  │
│  └──────────────────────────┬───────────────────────────────┘  │
│                             │                                   │
│  ┌──────────────────────────▼───────────────────────────────┐  │
│  │ 3. Intent Classification                                 │  │
│  │    Symptom reporting │ Information query                 │  │
│  │    Escalation request │ Follow-up                        │  │
│  └──────────────────────────┬───────────────────────────────┘  │
│                             │                                   │
│  ┌──────────────────────────▼───────────────────────────────┐  │
│  │ 4. Symptom Triage Engine                                 │  │
│  │    Severity scoring │ Urgency classification            │  │
│  │    Differential suggestion │ Referral threshold          │  │
│  └──────────────────────────┬───────────────────────────────┘  │
└─────────────────────────────┼───────────────────────────────────┘
                              │
┌─────────────────────────────▼───────────────────────────────────┐
│              KNOWLEDGE BASE                                     │
│  Swahili-English parallel medical corpus (5,000+ terms)        │
│  WHO guidelines (Swahili) │ AMREF terminology database          │
│  Local clinic symptom descriptions │ Drug information DB        │
└─────────────────────────────┬───────────────────────────────────┘
                              │
┌─────────────────────────────▼───────────────────────────────────┐
│         EXPLAINABLE OUTPUT LAYER                                │
│  SHAP-based interpretability │ Confidence scores               │
│  Medical disclaimer injection │ Clinician escalation flags     │
│  Dual-language output (Swahili primary + English backup)        │
└─────────────────────────────────────────────────────────────────┘
```

---

## Model Architecture

### Base Model Selection

| Model | Pros | Cons | Decision |
|-------|------|------|----------|
| **NLLB-200** (Primary) | Strong Swahili coverage; 200-language support; open weights | Larger compute footprint | **Selected** |
| **MT5** (Alternative) | Good multilingual baseline; smaller size | Weaker Swahili tokenization | Fallback option |
| GPT-4 API | Strong reasoning | Proprietary; high inference cost; no fine-tuning control | Excluded |
| AfroLM | Africa-focused | Limited medical domain coverage | Excluded |

### Fine-Tuning Strategy

```
Stage 1: Tokenization Adaptation
  └── Extend NLLB-200 tokenizer with 2,000+ Swahili medical terms
  └── Reduce tokenization fragmentation from 23% → <10%

Stage 2: Domain Adaptation Pre-training
  └── Continued pre-training on Swahili medical text (unlabeled)
  └── ~100M tokens from AfroMT-style corpus

Stage 3: Supervised Fine-tuning (SFT)
  └── NER: IOB tagging on 5,000-term annotated corpus
  └── Intent classification: 8 intents × 200 examples each
  └── Triage: symptom → severity mapping with clinical validation

Stage 4: RLHF-lite (Clinical Feedback)
  └── 100 clinician-reviewed outputs
  └── Preference data for response quality
```

---

## Data Pipeline

```
Raw Sources
    │
    ├── AMREF Kenya terminology (500 terms)
    ├── WHO Swahili health docs (200 docs)
    ├── Medical glossaries (1,000 terms)
    ├── De-identified clinic consultations (1,000)
    └── SWAC QA pairs
         │
         ▼
    Pre-processing
    ├── Text cleaning & normalization
    ├── Coastal dialect standardization
    ├── PII removal (patient de-identification)
    └── Format standardization
         │
         ▼
    Annotation Pipeline
    ├── NER annotation (IOB tagging)
    ├── Intent labeling
    ├── Clinical validation by advisory board
    └── Inter-annotator agreement (Cohen's κ ≥ 0.85 target)
         │
         ▼
    Final Dataset (CC BY 4.0)
    ├── 5,000+ Swahili medical terms
    ├── 1,600+ NER training examples
    └── 1,000+ QA pairs
```

---

## Deployment Infrastructure

```yaml
# Deployment stack
Compute:
  - GPU: A100 / V100 clusters (cloud)
  - Inference: Optimized with ONNX Runtime + INT8 quantization
  - Target latency: <2s per response

Storage:
  - Patient data: HIPAA-compliant encrypted cloud storage
  - Model artifacts: versioned S3-compatible object storage
  - Audit logs: append-only log store

Monitoring:
  - Performance: NER accuracy, BLEU scores, triage precision/recall
  - Usage: daily active users, session duration, completion rate
  - Safety: clinician escalation rate, disclaimer trigger rate
  - Drift: input distribution monitoring for model degradation

Interfaces:
  - WhatsApp: WhatsApp Cloud API (Meta)
  - SMS: Africa's Talking API
  - Web: Streamlit / FastAPI
  - Speech (optional): Mozilla DeepSpeech Swahili model
```

---

## Explainability Framework

All outputs include SHAP-based explanations for clinician review:

```python
# Example output structure
{
  "response_sw": "Dalili zako zinaonyesha uwezekano wa malaria...",
  "response_en": "Your symptoms suggest possible malaria...",
  "confidence": 0.82,
  "entities_detected": [
    {"text": "homa", "type": "SYMPTOM", "en": "fever", "confidence": 0.95},
    {"text": "maumivu ya kichwa", "type": "SYMPTOM", "en": "headache", "confidence": 0.91}
  ],
  "triage_level": "MODERATE",
  "escalate_to_clinician": false,
  "disclaimer": "Hii si uchunguzi wa daktari. Tafadhali wasiliana na daktari...",
  "shap_explanation": {"homa": 0.41, "maumivu_ya_kichwa": 0.28, "msimu": 0.13}
}
```

---

## Security & Privacy

- All patient interactions are **de-identified at ingestion**
- No Personally Identifiable Information (PII) stored beyond session
- **IRB approval** obtained before any data collection
- **End-to-end encryption** for WhatsApp channel (native)
- Annual **penetration testing** and vulnerability assessment
- Compliance: Kenya Data Protection Act (2019), HIPAA-equivalent standards
