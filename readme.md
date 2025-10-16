# 🧠 Cura Medica – Domain-Specific Chatbot (Healthcare)

A domain-specific **Transformer-based chatbot** designed for healthcare-related queries. Built using **Hugging Face Transformers** and **TensorFlow**, this chatbot understands and generates medical advice and patient interaction responses.

## 🚀 Features
- Fine-tuned Transformer model (e.g., T5/GPT-2) for healthcare conversations  
- Preprocessed custom dataset of medical Q&A pairs  
- Interactive chatbot interface (Gradio/Flask)  
- Evaluated using BLEU, F1-score, and qualitative testing  

## 📁 Project Structure
├── cura-medica-data.ipynb – Dataset preparation and preprocessing  
├── cura-medica-notebook.ipynb – Model fine-tuning and evaluation  
├── generate.ipynb – Chatbot response generation & UI  
└── requirements.txt – Project dependencies  

## ⚙️ Installation
1. Clone this repository  
   `git clone https://github.com/yourusername/cura-medica-chatbot.git`  
   `cd cura-medica-chatbot`  
2. Create and activate a virtual environment  
   `python -m venv venv`  
   `source venv/bin/activate`  (Windows: `venv\Scripts\activate`)  
3. Install dependencies  
   `pip install -r requirements.txt`  

## 🧩 Requirements
Python 3.8+  
TensorFlow  
Transformers (Hugging Face)  
Gradio or Flask  
Pandas, NumPy, Scikit-learn  

## 🧪 Usage
To run the chatbot notebook or script:  
`jupyter notebook generate.ipynb`  
Or launch via web interface:  
`python generate.py`  

## 📊 Evaluation
Metrics used: BLEU, F1-score, Perplexity, and qualitative testing through real user queries.  

## 🎥 Demo
Watch demo video: [Demo Link Here]  
GitHub Repository: [Project Link Here]  

## 👨‍💻 Author
**Joel Mugisha** – AI & NLP Enthusiast  

## 📜 License
Licensed under the MIT License.
