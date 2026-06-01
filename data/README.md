# Data

This directory contains sample data and documentation for the Afyalugha Swahili medical corpus.

## Dataset Overview

**Name:** Afyalugha Swahili Medical Terminology Corpus

**License:** CC BY 4.0 — free to use with attribution

**Citation:**
```
Nyambu, Z. M. (2025). Afyalugha Swahili Medical Terminology Corpus.
Afyalugha Project, Mombasa, Kenya.
https://github.com/Zekeriya-Ui/afyalugha
```

## Release Schedule

| Version | Month | Size | Contents |
|---------|-------|------|---------|
| v0.1 (sample) | Month 1 | 100 terms | Sample entries for methodology review |
| v1.0 | Month 3 | 2,500 terms | Core medical terminology |
| v2.0 | Month 6 | 5,000+ terms | Full corpus with NER annotations |
| v3.0 | Month 12 | 5,000+ terms + QA | Final corpus with evaluation benchmark |

## Data Format

### Terminology Corpus (JSON)
```json
{
  "id": "AFY-0001",
  "swahili": "homa ya malaria",
  "english": "malaria fever",
  "category": "DISEASE",
  "dialect_variants": ["malaria", "homa ya mshumaa"],
  "icd10_code": "B54",
  "severity_hint": "HIGH",
  "source": "AMREF_Kenya",
  "validated_by": "Clinical Officer"
}
```

### NER Annotation Format (IOB2)
```
Nina  O
homa  B-SYMPTOM
nzito I-SYMPTOM
na    O
maumivu B-SYMPTOM
ya    I-SYMPTOM
viungo I-SYMPTOM
```

## Data Sources

All data is sourced with appropriate permissions. See [docs/data-strategy.md](../docs/data-strategy.md) for full details.

## Privacy

All patient-derived data is de-identified per the protocol in [docs/ethics.md](../docs/ethics.md). No PII is included in any released dataset.
