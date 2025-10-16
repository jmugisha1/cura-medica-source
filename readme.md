# Cura Medica — AI Medical Consultant Chatbot

A domain-specific Transformer chatbot that identifies possible diseases from symptoms and recommends the appropriate medical specialist. Fine-tuned from Gemma 3 (270M) with LoRA adapters. Lightweight, fast, and deployed with Gradio.

## Key features
- Symptom → disease prediction and specialist recommendation
- Fine-tuned Gemma 3 (270M) using LoRA via Unsloth
- Preprocessed combined medical datasets (Hugging Face + web-scraped specialist mappings)
- Simple Gradio web UI for interactive use
- Evaluation with BLEU and Perplexity

## Quickstart (Windows)
Clone and install:
```bash
git clone https://github.com/yourusername/cura-medica-chatbot.git
cd cura-medica-chatbot
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

Run:
- Notebook: `jupyter notebook generate.ipynb`
- Web UI: `python app.py`  (Gradio app)

## Model & training (summary)
- Base: unsloth/gemma-3-270m
- Fine-tuning: LoRA adapters, AdamW (8-bit)
- Split: 80% train / 20% val
- Hyperparameters: lr=2e-4, batch_size=4, epochs=3, grad_accum=8, warmup_steps=50

Evaluation (reported)
- BLEU: 0.0069273106
- Perplexity: 57.4340360

## Data & preprocessing
- Sources: FreedomIntelligence/Disease_Database, zaimasohail/symptom-disease-dataset, plus web-scraped specialist mappings
- Steps: cleaning, deduplication, normalization, tokenization (Gemma tokenizer), merged into symptom–disease–specialist format
- Notebooks:
  - cura-medica-data.ipynb — data cleaning & merging
  - cura-medica-v1.ipynb — final training & chatbot
  - generate.ipynb — generation, UI, and web-scraping helpers

## Deployment
- Deployed as a Gradio app (app.py) and suitable for Hugging Face Spaces.
- User flow: enter symptoms → model predicts likely disease and recommends specialist → view response in UI.

## Usage examples
Use raw symptom text (no surrounding quotes). Example inputs and expected responses:
```json
{"messages":[{"role":"user","content":"I have fever,cough,sore throat,runny or stuffy nose,muscle aches,headache,fatigue."},{"role":"model","content":"Based on your symptoms, you likely have flu. I recommend you see a General Physician."}]}
```
```json
{"messages":[{"role":"user","content":"I have cough,mucus production,shortness of breath,chest pain."},{"role":"model","content":"Based on your symptoms, you likely have bronchitis. I recommend you see a General Physician."}]}
```
```json
{"messages":[{"role":"user","content":"I have fever,cough,shortness of breath,chest pain,fatigue."},{"role":"model","content":"Based on your symptoms, you likely have pneumonia. I recommend you see a General Physician."}]}
```

## Limitations
- Not a substitute for professional medical diagnosis.
- Performance depends on dataset size and coverage; complex or rare cases may be inaccurate.
- Text-only input (no image analysis) in current release.

## Future work
- Add medical image support (X‑rays)
- Expand dataset and dialogue examples
- Improve confidence scoring and feedback loop

## Demo
Short demo video walkthrough: (link placeholder)

## Author
Joel Mugisha — Machine Learning Techniques I (Oct 2025)

## License
MIT
