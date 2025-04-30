# 🏥 Ortho Department Medical Assistant Chatbot

This project is an AI-powered orthopedic medical assistant chatbot built using Python and Google's Gemini API (via `google-generativeai`). It is designed to assist with patient pre-screening by collecting symptoms, identifying affected body parts, clarifying ambiguities, and generating a structured report suitable for orthopedic consultation.

---

## 🚀 Features

- ✅ Accepts both **text and voice input**
- ✅ Uses **Gemini 1.5 Flash** model for symptom analysis
- ✅ Recognizes orthopedic symptoms and related body parts
- ✅ Automatically asks follow-up questions: **duration, severity, and location**
- ✅ Integrates **fuzzy matching** and **sentiment analysis**
- ✅ Generates a **clean summary report** in both JSON and PDF format
- ✅ Handles ambiguous inputs using Gemini's generative reasoning

---
🗄️ MongoDB Integration (with Encryption & RBAC)

This project uses MongoDB for storing patient records securely. Key features include:
    •    🔐 Client-Side Field-Level Encryption (CSFLE) using a local KMS provider
    •    📞 Sensitive fields like phone numbers are encrypted before storage
    •    🛡️ Role-Based Access Control (RBAC) for admins and doctors
    •    ☁️ Compatible with MongoDB Atlas using SRV URI

Make sure to:
    •    Start mongocryptd if using auto-encryption
    •    Set up roles and access policies in MongoDB
    •    Use certifi for TLS certificates in cloud setups

⸻

🌐 Multilingual Support

The assistant can accept inputs in multiple languages, including:
    •    Hindi
    •    English
    •    Other Indian languages (with proper TextBlob and fuzzy logic tuning)

Features:
    •    🗣️ Voice input works across languages (if properly configured)
    •    🌍 Uses TextBlob translation/sentiment features to assist multilingual understanding
    •    🧠 Gemini model handles multilingual prompts intelligently

## 📦 Requirements

Install the required dependencies before running:

```bash
pip install google-generativeai fuzzywuzzy textblob SpeechRecognition fpdf gtts requests
```

---

## 🧠 Technologies Used

- **Google Generative AI** (Gemini Flash) for symptom clarification and summaries
- **FuzzyWuzzy** for matching user input
- **TextBlob** for sentiment analysis
- **SpeechRecognition** for voice input handling
- **FPDF** for PDF report generation
- **gTTS** for optional speech output and translation (text-to-speech)

---

## 🔑 Gemini API Key

Set your Gemini API key before using:

```python
import google.generativeai as genai

api_key = 'YOUR_API_KEY_HERE'
genai.configure(api_key=api_key)
```

---

## 🩺 Workflow

1. **Collect Patient Info**: name, contact, age, gender
2. **Symptom Entry**: via text or speech
3. **Follow-Up Questions**: duration, severity, type, and associated symptoms
4. **Summary Generation**: JSON + plain-text + PDF
5. **Medical History**: ongoing/past conditions optionally added

---

## 📄 Output Example

```json
{
  "user_details": {
    "name": "John Doe",
    "age": 32,
    "phone": "XXXXXXXXXX",
    "gender": "Male"
  },
  "symptom_data": [
    {
      "symptom": "knee pain",
      "location": "left knee",
      "duration": "2 weeks",
      "severity": "moderate",
      "type": "sharp",
      "associated_symptoms": ["swelling"]
    }
  ],
  "medical_conditions": ["Diabetes"],
  "overall_summary": "The patient reports left knee pain for 2 weeks, with moderate sharp pain and swelling, possibly indicating ligament strain or internal injury."
}
```

---

## 🖥️ How to Run

Open the notebook in Google Colab or Jupyter:

```bash
jupyter notebook final.ipynb
```

Follow the notebook cells in order to:
- Set API key
- Collect patient inputs
- Generate summary
- Save PDF report

---

## 📌 Notes

- This assistant is designed for **preliminary orthopedic screening only**.
- Ensure compliance with data privacy laws if using real patient data.
- The PDF includes only the plain summary text — no extra headers or labels.
