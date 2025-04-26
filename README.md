# Flight Sentiment Analysis on Twitter Data  
**Initial Release:** September 2021  
**Last Updated:** April 2025  

## Overview
This project presents an end-to-end sentiment analysis pipeline for airline-related tweets, leveraging both classical machine learning and transformer-based models. The objective is to automatically classify tweets into **Positive**, **Neutral**, or **Negative** sentiments to help airlines monitor public feedback in real time.

The initial version, developed in 2021, focused on baseline models and fundamental NLP techniques. In 2025, the project was revisited to incorporate advanced transformer models, interpretability techniques, and a more structured ML workflow aligned with industry best practices.

---

## Project Timeline

- **Sept 2021:**  
  Project initiated with classical ML (**TF-IDF + Logistic Regression**)

- **Oct 2021:**  
  Integrated **DistilBERT** for improved sentiment classification

- **April 2025:**  
  Upgraded to **Twitter-RoBERTa** for domain-specific performance  
  • Added LIME for model interpretability  
  • Structured codebase for scalability  
  • Comprehensive evaluation on sarcasm and neutral tone handling

---

## Problem Statement
Airlines receive vast amounts of unstructured feedback via Twitter. Manual monitoring is inefficient and error-prone. This project automates sentiment detection to enable airlines to:

- Track customer satisfaction trends.
- Identify service-related issues proactively.
- Analyze sentiment shifts during disruptions (e.g., delays, cancellations).

---

## Approach

1. **Data Source:**  
   Publicly available [Tweets.csv](https://www.kaggle.com/datasets/crowdflower/twitter-airline-sentiment) dataset containing labeled airline tweets.

2. **Preprocessing:**  
   - Text cleaning (removal of URLs, mentions, hashtags).
   - Handling class imbalance via upsampling.
   - Extraction of airline handles for potential downstream analysis.

3. **Modeling Techniques:**  
   - **Baseline:** TF-IDF + Logistic Regression  
   - **Transformer Models:**  
     - DistilBERT (general-purpose)  
     - Twitter-RoBERTa (optimized for social media text)  

4. **Evaluation:**  
   - Metrics: Accuracy, Precision, Recall, F1-Score, Confusion Matrix.  
   - Special focus on handling **Neutral** sentiment and **sarcastic expressions**.

5. **Interpretability:**  
   Integrated **LIME** to explain model predictions at the individual tweet level.

---

## Results

| **Model**                | **Accuracy** | **Neutral F1-Score** | **Notes**                |
|--------------------------|--------------|----------------------|--------------------------|
| TF-IDF + LogisticRegression | 86%        | 0.84                 | Classical ML baseline    |
| DistilBERT               | 94%          | 0.92                 | General transformer      |
| Twitter-RoBERTa          | **95%**      | **0.94**             | Best overall performance |

- The Twitter-RoBERTa model demonstrated superior performance, particularly in managing informal language and common Twitter sarcasm.
- Challenges remain in detecting **implicit sarcasm** where no explicit negative keywords are present.

---

## Key Challenges
- **Sarcasm Detection:**  
  Tweets lacking explicit sentiment indicators can mislead models.
  
- **Neutral vs. Slightly Positive Tone:**  
  Statements with factual content but containing positive words were occasionally misclassified.

---

## Future Work
- Incorporate a dedicated **sarcasm detection module** prior to sentiment classification.
- Explore multi-task learning approaches combining sentiment and intent detection.
- Deploy the model via an API or integrate with a dashboard for real-time sentiment monitoring.
- Expand analysis to multilingual datasets using models like mBERT or XLM-RoBERTa.

