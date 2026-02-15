# 🐾 PawSenseAI
### AI-Based Pet & Cattle Health Assistance Chatbot

PawSenseAI is an NLP-driven conversational system designed to assist pet owners and cattle farmers with health, nutrition, and general care queries. The system combines semantic search with transformer-based response generation to provide context-aware answers through a Streamlit web interface.

## 📌 Overview

PawSenseAI integrates:

- Semantic Search using **SentenceTransformer (MiniLM)**
- Response generation using **fine-tuned FLAN-T5**
- **Firebase Realtime Database** for storing cattle health records and embeddings
- **Streamlit UI** for interactive access
- Optional **Speech-to-Text** and **Text-to-Speech** support

The application supports two service modes:
- 🐶 Pet Care Chatbot
- 🐄 Cattle Care Chatbot


## 🧠 System Workflow

1. User selects Pet Care or Cattle Care.
2. User submits a natural language query (text or speech).
3. Query is converted into embeddings using MiniLM.
4. Semantic similarity search retrieves top relevant Q&A pairs from Firebase.
5. A few-shot prompt is constructed using retrieved results.
6. The prompt is passed to the fine-tuned FLAN-T5 model.
7. Generated response is displayed and optionally converted to speech.
8. Session history is maintained during runtime.

This pipeline enables context-aware responses instead of purely generic answers.

## Process Flow of Sementic Search
<img width="2000" height="815" alt="image" src="https://github.com/user-attachments/assets/913a4632-6417-45f1-96cb-80f35ef630f2" />


## 🛠️ Tech Stack

### Programming & Framework
- Python
- Streamlit

### NLP & ML
- Hugging Face Transformers
- FLAN-T5 (fine-tuned)
- SentenceTransformers (MiniLM)
- TensorFlow
- PyTorch (for embeddings)

### Database
- Firebase Realtime Database

### Speech Integration
- Google Speech-to-Text API
- gTTS (Google Text-to-Speech)

## FLAN T5 Architecture
<img width="940" height="716" alt="image" src="https://github.com/user-attachments/assets/bea6d1e8-f781-4d43-8bae-c125462bc3d0" />

## 📂 Dataset Preparation

Data was collected and structured in Q&A format from:
- Public datasets (e.g., Kaggle)
- Veterinary resources
- Web-scraped sources (processed using BeautifulSoup)

Preprocessing steps:
- Text cleaning
- Tokenization
- Input-output formatting
- Tensor conversion
- Train-validation split

Embeddings were generated using MiniLM and stored for semantic retrieval.

## 🔍 Model Training

FLAN-T5 was:
- Loaded from a pretrained checkpoint
- Fine-tuned on curated pet and cattle care Q&A datasets
- Trained with defined hyperparameters (epochs, batch size, learning rate)

### Evaluation Metrics
- ROUGE Score
- BLEU Score
- F1 Score (for classification tasks)

## 📊 Preliminary Results

- Speech-to-Text accuracy ~90% in controlled environments
- Average response time: 2–3 seconds per query
- Secure handling of cattle health records in Firebase
- Context-aware responses generated using retrieval + generation pipeline

---

## 💡 Key Features

- Multi-species support (Pets & Cattle)
- Semantic retrieval before text generation
- Context-based few-shot prompting
- Optional voice input and output
- Session memory tracking
- Real-time database integration

<img width="1092" height="546" alt="image" src="https://github.com/user-attachments/assets/b55fdf98-f815-4f7f-9c81-43fe332c8a59" />
<img width="535" height="1156" alt="image" src="https://github.com/user-attachments/assets/8401555e-c5ec-4ed8-af1e-90ff85d88bf5" />
<img width="940" height="474" alt="image" src="https://github.com/user-attachments/assets/f87f2d8c-8134-4784-a6d6-0739a3579e9e" />

## 🖥️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Krishnan0022/PawSense-AI-using-NLP.git
cd PawSenseAI
```
2️⃣ Create Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
```
3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```
4️⃣ Configure Firebase

- Create a Firebase project

- Create your Db of pets anc cattle care data instances as shown below
<img width="1480" height="851" alt="image" src="https://github.com/user-attachments/assets/6e53d47c-0d5b-475d-9a34-a5481b0004a8" />
<img width="1479" height="961" alt="image" src="https://github.com/user-attachments/assets/670f6cd7-a201-4826-8316-c39db2f28fbc" />


- Download service account credentials

- Add credentials file to project directory

- Update Firebase configuration in the code

5️⃣ Run the Application
```bash
streamlit run app.py
```

🔮 Future Improvements
Multilingual support

- Enhanced personalization

- Improved contextual memory across sessions

- Expanded dataset coverage

- Better noise handling for speech input

👩‍💻 Contributors

- Krishnan V

- Rufina M

- Mahalakshmi Balan

Guide: Prof. Biji C.L

📜 License
This project is developed for academic purposes.
