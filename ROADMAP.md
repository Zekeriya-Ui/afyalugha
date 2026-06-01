# Afyalugha: 12-Month Implementation Roadmap

## Overview

| Phase | Months | Focus | Budget (Cash) | Budget (Compute) |
|-------|--------|-------|---------------|------------------|
| Phase 1 | 1–3 | Foundation | $25,000 | $20,000 |
| Phase 2 | 4–6 | Model Development | $75,000 | $150,000 |
| Phase 3 | 7–9 | Pilot Deployment | $50,000 | $50,000 |
| Phase 4 | 10–12 | Scale & Impact | $50,000 | $80,000 |
| **Total** | | | **$200,000** | **$300,000** |

---

## Phase 1: Foundation (Months 1–3)

### Month 1 — Partnerships & Infrastructure
- [ ] Finalize partnerships with 10 health facilities
- [ ] Recruit clinical advisory board (4 members)
- [ ] Set up data infrastructure and secure storage
- [ ] Execute partnership agreements
- [ ] Obtain IRB approval for data collection
- [ ] **Deliverable:** Partnership agreements signed; IRB approved

### Month 2 — Corpus Building Begins
- [ ] Curate Swahili medical terminology corpus (target: 2,500 terms)
- [ ] Build parallel Swahili-English dataset framework
- [ ] Begin annotation pipeline setup
- [ ] Train annotators
- [ ] **Deliverable:** Corpus v1.0 (2,500 terms)

### Month 3 — Foundation Complete
- [ ] Complete corpus (5,000+ terms)
- [ ] Select and configure base model (NLLB-200 primary)
- [ ] Begin tokenization adaptation experiments
- [ ] Release dataset publicly under CC BY 4.0
- [ ] **Deliverable:** Dataset public open source; model environment ready

---

## Phase 2: Model Development (Months 4–6)

### Month 4 — Core NLP Pipeline
- [ ] Fine-tune Swahili medical NER model
- [ ] Build intent classification system (8 intent classes)
- [ ] Initial evaluation: target NER ≥75% accuracy
- [ ] Develop chatbot interface (WhatsApp/SMS)
- [ ] Build explainability layer (SHAP)
- [ ] **Deliverable:** Beta chatbot v0.5

### Month 5 — Iteration
- [ ] Continue fine-tuning based on evaluation results
- [ ] Internal validation on 100 test cases (clinician review)
- [ ] Refine triage scoring algorithm
- [ ] UX testing with 5 pilot health workers

### Month 6 — Model Complete
- [ ] Complete fine-tuning (achieve ≥75% NER accuracy)
- [ ] Internal validation complete
- [ ] Release fine-tuned NER model (MIT license)
- [ ] **Deliverable:** Model v1.0; evaluation report

---

## Phase 3: Pilot Deployment (Months 7–9)

### Month 7 — First Clinics Go Live
- [ ] Deploy to 3 pilot clinics
- [ ] Train health workers (2-day training program)
- [ ] Begin patient onboarding
- [ ] **Target:** 3 clinics live; 500 users

### Month 8 — Expansion
- [ ] Expand to 7–8 additional clinics
- [ ] Collect usage data and patient feedback
- [ ] Iterate on UX based on real-world feedback
- [ ] **Target:** 10 clinics live; 5,000 users

### Month 9 — Mid-Pilot Assessment
- [ ] Monitor performance metrics against targets
- [ ] Conduct mid-pilot evaluation (clinical audit: 100 interactions)
- [ ] Refine model based on real-world data
- [ ] **Target:** 10,000 users; performance report

---

## Phase 4: Scale & Impact Assessment (Months 10–12)

### Month 10 — Scaling
- [ ] Scale to 5,000 users/day
- [ ] Publish medical corpus (CC BY 4.0)
- [ ] Submit academic paper to African NLP venue
- [ ] Conduct impact survey (n ≥ 500 patients)
- [ ] Finalize explainability framework
- [ ] **Target:** 40,000 users; impact report v1; dataset published; paper submitted

### Month 11 — Final Preparation
- [ ] Continue scaling operations
- [ ] Prepare final evaluation study
- [ ] Begin sustainability plan execution
- [ ] Train 5 local developers in Swahili NLP

### Month 12 — Project Completion
- [ ] **Reach 50,000 users** ✓
- [ ] Complete final evaluation
- [ ] Develop and publish sustainability plan
- [ ] Present at African NLP conference
- [ ] Release chatbot source code (AGPL 3.0)
- [ ] **Deliverable:** Final report + conference presentation + all open-source releases

---

## Key Milestones

```
Month 1  ──●── IRB Approved; Partnerships Signed
Month 3  ──●── 5,000-term corpus released (CC BY 4.0)
Month 6  ──●── NER Model v1.0 released (MIT)
Month 7  ──●── First 3 clinics live
Month 9  ──●── 10,000 users reached; 10 clinics live
Month 10 ──●── Academic paper submitted
Month 12 ──●── 50,000 users; Full open-source release
```

---

## Risk Mitigation Timeline

| Risk | Mitigation Phase | Owner |
|------|------------------|---------|
| Model accuracy below target | Phase 2 (Month 5 iteration) | PI + Masakani |
| Patient adoption slow | Phase 3 (community engagement) | Clinic coordinator |
| Compute cost overrun | Monthly GPU monitoring from Month 4 | PI |
| Regulatory changes | Phase 1 (Ministry of Health engagement) | PI + Legal |
| IRB delay | Month 1 (early submission) | PI |
