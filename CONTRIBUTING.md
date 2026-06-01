# Contributing to Afyalugha

Thank you for your interest in contributing to Afyalugha! This is an African-led, community-driven project, and we welcome contributions from developers, clinicians, linguists, and researchers.

---

## Ways to Contribute

### 🔬 Research & NLP
- Improve Swahili medical NER models
- Expand the medical terminology corpus
- Develop evaluation benchmarks
- Research bias mitigation techniques

### 💊 Clinical
- Validate medical terminology
- Review chatbot responses for clinical accuracy
- Contribute de-identified symptom descriptions
- Join the clinical advisory board

### 🗣️ Linguistics
- Add coastal Swahili dialect variations
- Improve tokenization for Swahili medical text
- Validate Swahili translations of medical terms

### 💻 Engineering
- Improve chatbot response latency
- Add new interface channels
- Enhance SHAP explainability integration
- Improve SMS/WhatsApp integrations

---

## Development Setup

```bash
# Fork and clone
git clone https://github.com/YOUR_USERNAME/afyalugha.git
cd afyalugha

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt

# Run tests
python -m pytest tests/
```

---

## Contribution Guidelines

### Code Contributions

1. **Fork** the repository
2. **Create a branch:** `git checkout -b feature/your-feature-name`
3. **Write tests** for any new functionality
4. **Follow PEP 8** for Python code
5. **Document** all functions and modules
6. **Submit a Pull Request** with a clear description

### Data Contributions

- All contributed data must be de-identified (no patient PII)
- Medical terminology must be clinically validated
- Provide source attribution where applicable
- By contributing data, you agree to CC BY 4.0 licensing

### Clinical Validation

- Clinical reviewers must have relevant medical credentials
- All clinical feedback is documented and attributed
- Disputes in medical accuracy are resolved by the clinical advisory board

---

## Code of Conduct

We are committed to a welcoming, inclusive community. All contributors must:

- Respect diverse perspectives and backgrounds
- Use welcoming and inclusive language
- Prioritize patient safety in all decisions
- Follow responsible AI development practices

---

## Contact

- **Project Lead:** Zacharia Maganga Nyambu
- **GitHub:** [Zekeriya-Ui](https://github.com/Zekeriya-Ui)
- **Live App:** [afya-lugha.runable.site](https://afya-lugha.runable.site/)
- **WhatsApp Chatbot:** +14155238886
