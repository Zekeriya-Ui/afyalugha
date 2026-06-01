# Afyalugha: Impact Metrics & Evaluation Framework

## Theory of Change

```
INPUTS                ACTIVITIES              OUTPUTS              OUTCOMES
──────────────────────────────────────────────────────────────────────────────
Funding ($500k)  →  Build NLP pipeline  →  Swahili chatbot   →  Patients access
Compute credits  →  Annotate corpus     →  5,000-term corpus →  health info in
Clinical team    →  Deploy to clinics   →  10 clinics live   →  Swahili
Partnerships     →  Train health        →  50,000 users      →  Reduced language
                    workers                                      barriers (40%)
                                                             →  Improved triage
                                                                accuracy (+5%)
```

---

## Primary Impact Metrics

| Metric | Baseline | Target (Year 1) | Measurement Method |
|--------|----------|-----------------|-------------------|
| Unique users | 0 | 50,000 | Chatbot analytics |
| Language barrier reduction | 60% report language barrier | 40% reduction | Pre/post patient surveys |
| Triage accuracy | 60% correct (English tool) | 75% correct (+25%) | Clinical validation of outputs |
| Medical NER accuracy | 58% (Masakani NER) | ≥85% accuracy | Evaluation on test set |
| Translation error rate | 44% lower (NLLB-244 baseline) | <20% error rate | BLEU score comparison |

---

## Secondary Impact Metrics

| Metric | Target |
|--------|--------|
| Patient satisfaction score | ≥4.0/5.0 |
| Clinic trust in system | ≥70% rate system as helpful |
| Open source dataset downloads | 500+ (researchers/organizations) |
| Academic publications | 2 papers |
| Policy engagement | 1 government health ministry meeting |

---

## Evaluation Framework

### Quantitative Evaluation

- **A/B testing:** chatbot vs. English-only tool for triage accuracy
- **Pre/post surveys:** language barrier self-reporting (n ≥ 500 patients)
- **Usage analytics:** daily active users, session duration, completion rates
- **NLP benchmarks:** NER F1, BLEU scores, intent classification accuracy

### Qualitative Evaluation

- **In-depth interviews:** 15 patients (purposive sampling across age, gender, education)
- **Clinician focus groups:** 4 sessions with community health workers
- **Clinical audit:** 100 chatbot interactions reviewed by physician
- **Case studies:** 3 documented impact stories per quarter

### Bias & Fairness Assessment

| Dimension | Method |
|-----------|--------|
| Age | Performance stratified by age group (18-30, 31-50, 51+) |
| Gender | Accuracy comparison across male/female/other patients |
| Education level | Performance vs. self-reported education |
| Coastal dialect | NER accuracy for different coastal Swahili variants |
| Condition type | Triage accuracy by disease category (malaria, TB, maternal) |

**Acceptance threshold:** <5% performance gap across any demographic dimension.

---

## Measurement Timeline

| Month | Evaluation Activity |
|-------|--------------------|
| 3 | Corpus quality audit (inter-annotator agreement) |
| 6 | Model performance report (NER, intent, triage accuracy) |
| 9 | Mid-pilot report (5,000 users, clinical audit 100 cases) |
| 10 | Impact survey launch (n ≥ 500) |
| 12 | Final evaluation report + academic paper submission |

---

## Long-term Impact Vision (Years 2–5)

- **750,000 patients** across Kenya within reach of Swahili health AI
- **Expand to 3 new counties** (Lamu, Tana River, Taita-Taveta)
- **Additional language support:** Giriama, Digo, Pokomo (coastal Bantu languages)
- **Integration with Kenya's national health information system (DHIS2)**
- **Policy influence:** Evidence base for Ministry of Health's digital health strategy
- **Research impact:** Swahili medical NLP benchmark becomes a community standard
