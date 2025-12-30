# LSTM vs BERT: A Comparative Study on Multi-Label Toxic Comment Classification

## 📌 Overview

This project presents a comparative analysis between a **BiLSTM-based neural network** and a **fine-tuned BERT model** for **multi-label toxic comment classification**.

Rather than focusing only on accuracy, the goal is to understand **where traditional sequence models fail and why transformer-based models perform better**, especially on **implicit and context-dependent abusive language**.

---

## 🎯 Problem Statement

Online platforms must automatically detect harmful language such as:

- Toxic comments  
- Insults  
- Threats  
- Hate speech  

Traditional NLP models often struggle with indirect or non-profane abuse.  
This project benchmarks whether **BERT’s contextual understanding** provides a meaningful advantage over an **LSTM baseline**.

---

## 🧪 Dataset

- **Source:** Jigsaw Toxic Comment Classification dataset  
- **Task:** Multi-label classification  
- **Labels:**
  - toxic
  - severe_toxic
  - obscene
  - threat
  - insult
  - identity_hate

---

## 🏗️ Models Implemented

### 1️⃣ BiLSTM Baseline (TensorFlow / Keras)

**Architecture:**
```
Text → Integer Encoding → Embedding → BiLSTM → Dense Layers → Sigmoid Outputs
```

**Characteristics:**
- Sequential token processing
- Effective for explicit toxic words
- Limited contextual understanding

This model is used strictly as a **baseline**.

---

### 2️⃣ BERT (DistilBERT Fine-Tuned)

**Architecture:**
```
Text → WordPiece Tokenization → Transformer Encoder → Classification Head
```

**Characteristics:**
- Context-aware semantic representations
- Strong performance on implicit insults
- Fine-tuned for multi-label toxicity classification

---

## 🔍 Qualitative Comparison (Key Insight)

**Input Sentence:**

> *"You are a disgrace and a waste of space."*

| Model  | Toxic | Insult |
|------|------|------|
| BiLSTM | ✅ True | ❌ False |
| BERT   | ✅ True | ✅ True |

**Observation:**

- The **BiLSTM model** detects general toxicity but fails to classify the sentence as an insult due to the absence of explicit profanity.
- The **BERT model** correctly identifies the insult, demonstrating stronger contextual and semantic understanding.

---

## 🖥️ Interactive Demo (Gradio)

Two Gradio-based interfaces were implemented:

- LSTM toxicity predictor  
- BERT toxicity predictor  

Users can input text and observe **model-specific predictions in real time**.

---

## 🧠 Key Learnings

- LSTM models rely heavily on token-level patterns.
- BERT captures sentence-level meaning and intent.
- Transformer architectures significantly outperform sequence models on implicit abuse.
- Qualitative error analysis is essential beyond raw metrics.

---

## 🚀 Future Work

- Side-by-side LSTM vs BERT comparison UI


---
