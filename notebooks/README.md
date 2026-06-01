# Notebooks

This directory will contain Jupyter notebooks documenting experiments, model evaluations, and analyses conducted during the Afyalugha project.

## Planned Notebooks

| Notebook | Phase | Description |
|----------|-------|-------------|
| `01_corpus_analysis.ipynb` | Month 3 | Analysis of the Swahili medical corpus: term distribution, dialect coverage, category breakdown |
| `02_tokenization_study.ipynb` | Month 3 | Comparison of tokenization strategies for Swahili medical text (NLLB vs. MT5 vs. custom) |
| `03_ner_baseline.ipynb` | Month 4 | Baseline NER evaluation on Masakani NER vs. fine-tuned model |
| `04_intent_classification.ipynb` | Month 4 | Intent classifier training and evaluation |
| `05_triage_validation.ipynb` | Month 6 | Clinical validation of triage scoring against physician assessments |
| `06_bias_analysis.ipynb` | Month 9 | Fairness analysis: performance across age, gender, education, dialect |
| `07_impact_analysis.ipynb` | Month 12 | Final impact evaluation: user growth, barrier reduction, triage accuracy |

## Setup

```bash
pip install jupyter pandas numpy matplotlib transformers
jupyter notebook
```

## Reproducibility

All notebooks include:
- Random seed settings
- Full dependency versions
- Dataset version references
- Clear instructions to reproduce results
