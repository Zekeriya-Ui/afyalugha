# Ethical Considerations

## Guiding Principles

Afyalugha is designed with patient safety, privacy, and dignity as non-negotiable priorities. This document outlines the ethical framework governing all aspects of data collection, model development, and deployment.

---

## 1. Patient Privacy & Data Protection

### Data De-identification
- All patient data is de-identified before any use in model training
- No Personally Identifiable Information (PII) is retained beyond the active session
- De-identification follows Kenya Data Protection Act (2019) and HIPAA-equivalent standards
- An independent Data Protection Officer (DPO) audits compliance quarterly

### Storage & Security
- Patient interaction data stored in HIPAA-compliant encrypted cloud storage
- Access limited to de-identified analytics data only
- Penetration testing conducted annually
- Breach notification protocol: 72-hour disclosure to relevant authorities

---

## 2. Informed Consent

- Patients are **clearly informed** the chatbot is AI-assisted, not a medical diagnosis
- Consent is obtained in **Swahili** (the patient's primary language)
- Patients can **opt out** at any time without consequence to their healthcare
- Health workers explain the system before first use
- All Swahili-language consent forms reviewed by Swahili linguist on advisory board

---

## 3. Bias Mitigation

### Training Data Bias
- Fairness-aware training to address linguistic disparities
- Performance monitored across age, gender, education level, and dialect
- Acceptance threshold: <5% performance gap across demographic dimensions
- Dataset diversity reviewed by community health workers

### Algorithmic Fairness
- Regular audits of triage recommendations for systematic disparities
- Coastal dialect variations explicitly included in training data
- Senior clinician reviews any identified performance disparities

---

## 4. Clinical Safety

### Escalation Protocol
- **All triage outputs include explicit medical disclaimers in Swahili**
- High-severity symptoms automatically trigger clinician escalation flag
- Uncertain model outputs (confidence <0.7) are flagged for human review
- The system explicitly cannot diagnose; it only triages and informs

### Prohibited Uses
- The chatbot **must not** be used as a substitute for emergency medical care
- Users presenting emergency symptoms are directed to call 999 immediately
- No medication dosage advice beyond pre-validated WHO guidelines

---

## 5. Cultural Alignment

- Community engagement with local health workers throughout development
- Cultural appropriateness of health messaging validated by community advisory group
- Traditional healing practices acknowledged respectfully; not dismissed
- Gender-sensitive language used in all outputs

---

## 6. IRB & Regulatory Compliance

- IRB approval obtained before any patient data collection (Month 1)
- Ongoing compliance reviewed by clinical advisory board monthly
- Ministry of Health engaged from Month 1 to ensure regulatory alignment
- Project positioned as **clinical decision support**, not autonomous diagnosis
