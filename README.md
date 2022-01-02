# ✈️ Flight Sentiment Analysis and Detection

Transformer-based sentiment classification of airline-related tweets into **positive**, **neutral**, or **negative** using DistilBERT and Twitter-RoBERTa. The goal is to help airlines monitor customer feedback by automatically analyzing public sentiment on Twitter.

---

## 🔧 Models Used

- **DistilBERT** (Baseline)
- **Twitter-RoBERTa** (Improved, with upsampled neutral class)

---

## 🧠 Training Summary

### DistilBERT

| Epoch | Training Loss | Validation Loss |
|-------|----------------|------------------|
| 1     | 0.4183         | 0.4282           |
| 2     | 0.2668         | 0.4427           |
| 3     | 0.1959         | 0.5070           |

### Twitter-RoBERTa

| Epoch | Training Loss | Validation Loss |
|-------|----------------|------------------|
| 1     | 0.2514         | 0.3052           |
| 2     | 0.1686         | 0.3149           |
| 3     | 0.0971         | 0.3588           |

---

## 📊 Evaluation Results

### DistilBERT

| Sentiment | Precision | Recall | F1-Score | Support |
|-----------|-----------|--------|----------|---------|
| Negative  | 0.87      | 0.94   | 0.90     | 1835    |
| Neutral   | 0.72      | 0.60   | 0.65     | 620     |
| Positive  | 0.80      | 0.76   | 0.78     | 473     |
| **Accuracy** |         |        | **0.84** | 2928    |

### Twitter-RoBERTa

| Sentiment | Precision | Recall | F1-Score | Support |
|-----------|-----------|--------|----------|---------|
| Negative  | 0.94      | 0.90   | 0.92     | 1836    |
| Neutral   | 0.89      | 0.92   | 0.90     | 1836    |
| Positive  | 0.79      | 0.83   | 0.81     | 472     |
| **Accuracy** |         |        | **0.90** | 4144    |

---

## 🔄 Model Comparison

| Metric            | DistilBERT | Twitter-RoBERTa |
|------------------|------------|-----------------|
| Accuracy          | 84%        | **90%**         |
| Neutral F1-Score  | 0.65       | **0.90**        |
| Tweet Tone Handling | Moderate | **Strong**      |
| Dataset Balanced  | ❌         | ✅               |

---

## ✅ Conclusion

This project showcases an end-to-end approach to sentiment analysis on noisy, real-world social media data using transformer-based models. Starting with a baseline DistilBERT model, we identified key limitations in handling neutral and sarcastic tweets. To address this, we introduced Twitter-RoBERTa, a model pretrained specifically on tweets, and applied class balancing through upsampling. The improved model achieved a significant performance boost, reaching 90% accuracy and a 0.90 F1-score for the previously underperforming neutral class.

This work highlights practical challenges in natural language understanding and demonstrates model selection, fine-tuning, and evaluation best practices for building robust sentiment classification systems.

---
