**Sentiment Analysis Project (Assignment-IV, CSL7640)**
---

## 📌 Overview

This project implements a sentiment analysis system for both **binary** (positive/negative) and **multi-class** (positive/neutral/negative) classification. It compares two deep learning models:
- Feed-Forward Neural Network (FFNN)
- Recurrent Neural Network using Long Short-Term Memory (LSTM)

We evaluate model performance on:
- **IMDB movie review dataset** (binary classification)
- **SemEval Twitter dataset** (multi-class classification)

---

## 🧹 Preprocessing

### IMDB Dataset
- Clean, pre-labeled reviews
- 20% sampled for reduced compute
- Optional 90/10 train-dev split

### Twitter Dataset
- Extensive cleaning:
  - Remove invalid/missing rows
  - Map labels: Negative → 0, Neutral → 1, Positive → 2
  - Normalize mentions, URLs, punctuation
  - Remove short and duplicate tweets
- Final size after sampling: 11,228 examples

---

## 🧠 Models

### 1. Feed-Forward Neural Network (FFNN)
- Two hidden layers: 256 and 128 units
- ReLU activation, BatchNorm, Dropout
- Uses Sigmoid (binary) / Softmax (multi-class)
- Trained using:
  - **BCELoss** for binary
  - **CrossEntropyLoss** for multi-class
- Early stopping for efficient training

### 2. Long Short-Term Memory (LSTM)
- Embedding + LSTM + BatchNorm + Dropout + Output
- Handles sequential text using GloVe embeddings
- 5-Fold Cross-Validation to ensure generalization
- Trained with early stopping and class-specific metrics

---

## 📊 Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- Training/Validation Loss & Accuracy Curves

---

## 📈 Results Summary

### FFNN:
- Accuracy: **67.46%**
- F1 Score: **0.6769**

### LSTM:
- Accuracy: **70.38%**
- F1 Score: **0.7125**
- Outperformed FFNN on all major metrics

**Conclusion:**  
LSTM demonstrates superior performance in capturing sequential information in text, making it more suitable for sentiment classification, especially for short noisy texts like tweets.

---
## 📌 Key Takeaways

* LSTM is better suited for handling text with temporal dependencies
* Clean, preprocessed input significantly improves model performance
* Cross-validation is crucial for robust evaluation

