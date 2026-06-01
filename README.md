# 🏥 Afyalugha — Swahili AI for Patient Triage & Health Access

[![License: AGPL v3](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)](LICENSE)
[![Dataset License: CC BY 4.0](https://img.shields.io/badge/Dataset-CC%20BY%204.0-green.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Status: Active Development](https://img.shields.io/badge/Status-Active%20Development-orange.svg)]()
[![Sector: Healthcare](https://img.shields.io/badge/Sector-Healthcare-red.svg)]()

> **Deploying Swahili Language AI for Patient Triage and Health Information Access in Coastal Kenya**

**Afyalugha** (from Swahili: *afya* = health, *lugha* = language) deploys a Swahili-language AI chatbot for symptom triage and health information retrieval in coastal Kenya. The project addresses critical language barriers that prevent **60% of rural patients** from accessing accurate health information in English-only digital health tools.

---

## 🌍 The Problem

Africa has over 2,000 languages, yet most AI systems are built on English corpora. Even Swahili — spoken by 200M+ people — lacks adequate NLP coverage for medical applications. In coastal Kenya:

- **90%+ of coastal Kenyans** use Swahili as their primary language
- **Almost all digital health tools** are English-only
- Medical AI chatbots trained on Western corpora **misdiagnose 30% more frequently** in African languages
- Current NLP models exhibit **44% lower translation accuracy** for Swahili medical text
- Less than **1% of public Kenya-available NLP corpora** contain African medical text

---

## 🎯 Project Objectives

| Objective | Target |
|-----------|--------|
| Medical NER accuracy | ≥85% (vs. 58% Masakani baseline) |
| Unique patients reached | 50,000 in Year 1 |
| Language barrier reduction | 40% reduction in self-reported barriers |
| Triage accuracy improvement | ≥5% vs. English-only tools |
| Open-source medical terms | 5,000+ terms under CC BY 4.0 |
| Health facility deployments | 10 clinics (Mombasa, Kilifi, Kwale) |

---

## 🏗️ System Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                    USER INTERFACES                           │
│         WhatsApp │ SMS │ Web App │ Speech-to-Text            │
└──────────────────┬───────────────────────────────────────────┘
                   │
┌──────────────────▼───────────────────────────────────────────┐
│               SWAHILI NLP PIPELINE                           │
│  ┌──────────────┐  ┌───────────────┐  ┌──────────────────┐  │
│  │ Named Entity │  │    Intent     │  │  Symptom Triage  │  │
│  │ Recognition  │  │Classification │  │    Function      │  │
│  └──────────────┘  └───────────────┘  └──────────────────┘  │
│                                                              │
│  Base Model: NLLB-200 / MT5 (Swahili-adapted tokenization)  │
│  Fine-tuning: AfroMT-style Swahili medical corpus           │
└──────────────────┬───────────────────────────────────────────┘
                   │
┌──────────────────▼───────────────────────────────────────────┐
│            EXPLAINABLE OUTPUT LAYER                          │
│    SHAP-based interpretability │ Clinician review flags      │
│    Medical disclaimers │ Swahili + English responses         │
└──────────────────────────────────────────────────────────────┘
```

---

## 📁 Repository Structure

```
afyalugha/
├── README.md                          # Project overview (this file)
├── PROPOSAL.md                        # Full grant proposal
├── ARCHITECTURE.md                    # Technical architecture deep-dive
├── ROADMAP.md                         # 12-month implementation timeline
├── BUDGET.md                          # Detailed budget breakdown
├── IMPACT.md                          # Impact metrics and evaluation framework
├── CONTRIBUTING.md                    # Contribution guidelines
├── LICENSE                            # AGPL 3.0
├── docs/
│   ├── ethics.md                      # Ethical considerations
│   ├── data-strategy.md               # Data collection and annotation strategy
│   └── sustainability.md              # Post-grant sustainability plan
├── src/
│   ├── nlp/                           # NLP pipeline source code
│   ├── chatbot/                       # Chatbot interface code
│   ├── evaluation/                    # Evaluation scripts
│   └── api/                           # API server
├── data/
│   ├── README.md                      # Data sources and licensing
│   └── sample/                        # Sample anonymized data
└── notebooks/
    └── README.md                      # Jupyter notebooks for experiments
```

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/Zekeriya-Ui/afyalugha.git
cd afyalugha

# Install dependencies
pip install -r requirements.txt

# Run the chatbot locally
python src/chatbot/app.py
```

**Live Demo:** [https://afya-lugha.runable.site/](https://afya-lugha.runable.site/)

**WhatsApp AI Chatbot:** +14155238886

---

## 🤝 Partners

| Partner | Role |
|---------|------|
| Masakani Committee | NLP expertise & code review |
| AMREF Kenya | Medical terminology validation |
| Local Coastal Clinics | Pilot deployment & patient access |
| WHO Swahili Health Materials | Public health messaging corpus |

---

## 📜 Open Source Commitments

| Resource | License | Release |
|----------|---------|--------|
| Swahili Medical NER Model | MIT | Month 6 |
| Chatbot Source Code | AGPL 3.0 | Month 9 |
| Medical Terminology Corpus (5,000+ terms) | CC BY 4.0 | Month 3 |
| Evaluation Benchmark | CC BY 4.0 | Month 12 |
| Research Papers | Open Access (CC BY) | Month 12 |

---

## 📊 Funding

- **Cash Request:** $200,000
- **Compute Credits:** $300,000
- **Sector:** Application Track — Healthcare
- **Duration:** 12 months
- **Funder:** Lingua Africa (applied)

---

## 👤 Principal Investigator

**Zacharia Maganga Nyambu** — Quantitative researcher based in Mombasa, Kenya. Specializing in statistical modeling, Python data analysis, and software deployment. Motivated by direct observation of language barriers to healthcare in coastal Kenya.

- 📍 Mombasa, Kenya
- 🌐 [Blog](https://kapitals-pi.blogspot.com/)
- 🐙 [GitHub](https://github.com/Zekeriya-Ui)

---

## 📄 License

- **Source Code:** [AGPL 3.0](LICENSE)
- **Dataset:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
- **Research Papers:** Open Access (CC BY)

---

*Afyalugha is an African-led, community-driven AI project advancing linguistic equity in healthcare.*
