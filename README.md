# Emotia: AI Diary 

An AI-powered emotional diary that detects multiple emotions from journal-style text entries and responds with empathetic, supportive feedback in real time.

Built using Deep Learning, Flask, PyTorch, and TF-IDF-based multi-label emotion classification.

---

## Overview

**Emotia** is an intelligent emotional journaling system designed to analyze diary entries and identify human emotions from text. Unlike traditional sentiment analysis systems that only predict positive or negative emotions, Emotia supports **multi-label emotion detection**, meaning a single diary entry can express multiple emotions simultaneously.

The project aims to create a safe and supportive AI diary experience by combining:

* Emotion Detection
* Mental Health Risk Awareness
* Supportive AI Responses
* Lightweight Real-Time Inference

---

##  Features

*  Multi-label emotion classification
*  Detects 28 emotions using Google's GoEmotions dataset
*  Fast real-time predictions
*  Empathetic AI-generated responses
*  Mental health risk detection layer
*  Modern Glassmorphism UI
*  Handles class imbalance effectively
*  Diary-specific synonym expansion

---

##  System Architecture

```text
User Input
   ↓
Text Cleaning
   ↓
Synonym Expansion
   ↓
TF-IDF Vectorization
   ↓
Feature Scaling
   ↓
Deep MLP Model
   ↓
Sigmoid Activation + Thresholding
   ↓
Safety Logic
   ↓
Supportive Response Generation
```

---

##  Text Preprocessing

The preprocessing pipeline includes:

* Lowercasing
* URL & HTML removal
* Special character cleaning
* Space normalization
* Diary-language synonym expansion

Example:

```text
"I'm SAD!!!"
→ "im sad"
```

Custom diary-related mappings improve emotional understanding for words like:

```text
"empty" → sadness, hopelessness
"numb" → grief, loneliness
```

---

##  Feature Engineering

### TF-IDF Vectorization

* Top 7000 informative features
* Stopword removal
* Sparse representation for efficiency

### Feature Scaling

* MaxAbsScaler used to preserve sparsity

### Class Imbalance Handling

* Weighted loss functions for rare emotions

---

##  Deep Learning Model

### Architecture

| Layer          | Details            |
| -------------- | ------------------ |
| Input Layer    | 7000 Units         |
| Hidden Layer 1 | 512 Units + ReLU   |
| Hidden Layer 2 | 256 Units + ReLU   |
| Dropout        | 30%                |
| Output Layer   | 28 Sigmoid Outputs |

### Why MLP Instead of BERT?

* Faster training
* Lightweight deployment
* CPU-friendly
* Excellent performance for short diary text

---

##  Dataset

This project uses the **GoEmotions Dataset** developed by Google Research.

* ~58,000 Reddit comments
* 28 emotion labels
* Multi-label annotations

---

##  Safety & Ethical Design

Emotia includes a deterministic safety layer for detecting emotionally critical situations.

### Safety Logic Includes:

* Crisis-related keyword detection
* High-risk emotion combinations
* Supportive bridge-to-human responses

The system is **not intended for medical diagnosis**.

---

##  Model Performance

| Metric             | Score     |
| ------------------ | --------- |
| Hamming Accuracy   | 87.93%    |
| Multi-label Recall | High      |
| Inference Speed    | Real-time |

### Strongly Detected Emotions

* Grief
* Fear
* Gratitude
* Love

---

##  Tech Stack

### Backend

* Python
* Flask
* PyTorch
* Scikit-learn

### Frontend

* HTML
* CSS
* JavaScript

### ML Techniques

* TF-IDF
* Multi-label Classification
* Deep MLP Neural Network

---

##  Project Structure

```bash
Emotia/
│
├── app.py
├── model/
│   ├── emotion_model.pth
│   ├── tfidf_vectorizer.pkl
│   └── scaler.pkl
│
├── templates/
├── static/
├── preprocessing/
├── responses/
├── dataset/
└── README.md
```

---

##  Installation

Clone the repository:

```bash
git clone https://github.com/your-username/emotia-ai-diary.git
cd emotia-ai-diary
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the Flask app:

```bash
python app.py
```

---

##  Future Improvements

* Transformer/BERT integration
* Personalized emotion tracking
* Voice-based diary entries
* Emotion visualization dashboard
* Daily emotional analytics

---

##  Contributors

* Quratulain
* Areeba Naeem
* Radeel Ayesha

---

##  License

This project is developed for academic and educational purposes.

---

## ❤️ Final Note

Emotia was created to explore how AI can support emotional expression in a thoughtful and human-centered way. The project combines deep learning with empathetic interaction design to create a safer and more emotionally aware journaling experience.
