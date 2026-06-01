# Source Code

This directory contains the source code for the Afyalugha system.

## Structure

```
src/
├── nlp/           # Core NLP pipeline
│   ├── ner.py     # Named Entity Recognition
│   ├── intent.py  # Intent classification
│   ├── triage.py  # Symptom triage engine
│   └── pipeline.py # End-to-end NLP pipeline
├── chatbot/       # Chatbot interfaces
│   ├── app.py     # Main Streamlit web app
│   ├── whatsapp.py # WhatsApp Cloud API integration
│   └── sms.py     # Africa's Talking SMS integration
├── evaluation/    # Evaluation scripts
│   ├── ner_eval.py # NER evaluation
│   ├── triage_eval.py # Triage accuracy evaluation
│   └── bias_eval.py # Fairness/bias assessment
└── api/           # FastAPI backend
    ├── main.py    # API entry point
    ├── routes/    # API route handlers
    └── models.py  # Pydantic data models
```

## Development Status

Code will be added progressively through the 12-month project timeline:
- **Month 3:** Data preprocessing scripts
- **Month 4:** Initial NLP pipeline
- **Month 6:** Model v1.0 + evaluation
- **Month 9:** Full chatbot code (AGPL 3.0 release)

## Setup

```bash
pip install -r requirements.txt
python src/chatbot/app.py
```

## Live Demo

[https://afya-lugha.runable.site/](https://afya-lugha.runable.site/)

**WhatsApp:** +14155238886
