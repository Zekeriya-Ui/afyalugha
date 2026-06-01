# Data Collection & Annotation Strategy

## Overview

Afyalugha's data strategy focuses on building the first open-source Swahili medical NLP corpus — curated specifically for coastal Kenya's healthcare context and released under CC BY 4.0 for global benefit.

---

## Target Corpus Composition

| Category | Target Count | Source |
|----------|-------------|--------|
| General medical terms | 2,000 | AMREF Kenya; medical glossaries |
| Disease names & symptoms | 1,000 | WHO Swahili materials; clinic consultations |
| Medications & dosages | 800 | AMREF; clinical advisor validation |
| Anatomy terms | 500 | Medical glossaries |
| Coastal dialect variations | 400 | Community health workers; linguist |
| Procedural terms | 300 | Clinical officer; AMREF |
| **Total** | **5,000+** | |

---

## Data Sources

### Primary Sources

| Source | Content | Size | License |
|--------|---------|------|--------|
| AMREF Kenya | Swahili health education materials | 500 terms | Permission granted |
| WHO Swahili Health Materials | Public health messaging | 200 documents | CC BY |
| Swahili-English Medical Glossary | Clinical terminology | 1,000 terms | Research agreement |
| Local Clinic Consultations | De-identified symptom descriptions | 1,000 examples | IRB approved |
| SWAC Word 24 | QA base pairs | Varies | Research use |

### Secondary Sources

- AfroMT parallel corpus (Swahili-English subset)
- OpenSuperMed multilingual medical terms
- Wikipedia Swahili medical articles (public domain)

---

## Annotation Pipeline

### Step 1: Raw Text Ingestion
```
Raw text → Encoding normalization → Sentence segmentation → Coastal dialect detection
```

### Step 2: Initial Annotation
- **Tool:** Label Studio (open source)
- **Schema:** IOB2 tagging (B-SYMPTOM, I-SYMPTOM, B-DRUG, etc.)
- **Annotators:** 2 trained Swahili-speaking annotators per document

### Step 3: Clinical Validation
- Clinical officer reviews all medical entity annotations
- Flagged disagreements resolved by clinical advisory board
- **Target inter-annotator agreement:** Cohen's κ ≥ 0.85

### Step 4: Dialect Normalization
- Swahili linguist normalizes coastal dialect variants
- Multiple surface forms mapped to canonical entries
- Dialect variation documented and preserved in metadata

### Step 5: Quality Assurance
- 10% random audit by clinical advisor
- Automated consistency checks (entity spans, label distribution)
- Final review before public release

---

## Privacy & De-identification

### De-identification Protocol

All clinic consultation data passes through a strict de-identification pipeline:

1. **Named entity removal:** patient names, clinician names, facility-specific identifiers
2. **Date generalization:** specific dates → month/year only
3. **Geographic generalization:** specific village/street → county level only
4. **Age bucketing:** exact ages → age groups (18-30, 31-50, etc.)
5. **Clinical audit:** De-identified samples reviewed by clinical officer before annotation

### Retention Policy

- Raw (identified) consultation notes: **deleted immediately** after de-identification
- De-identified corpus: retained for project duration and post-project open release
- Annotated training data: versioned and archived under CC BY 4.0

---

## Open Release Plan

| Month | Release | License | Platform |
|-------|---------|---------|----------|
| 3 | Corpus v1.0 (2,500 terms) | CC BY 4.0 | GitHub + HuggingFace |
| 6 | Corpus v2.0 (5,000+ terms) + annotations | CC BY 4.0 | GitHub + HuggingFace |
| 12 | Evaluation benchmark | CC BY 4.0 | GitHub + Masakani Africa |

All data will be published with full documentation: source attribution, annotation guidelines, known limitations, and suggested citation.
