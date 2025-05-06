# ai-chat-text-classifier-

This project is a university machine learning assignment focused on building an intelligent system to classify chatbot messages by category for the **Japeto Chat** platform. The model is optimized for real-time performance and high accuracy in multi-class classification.

---

## 📌 Project Overview

- **Goal:** Automatically categorize chatbot-generated messages into more than 20 categories.
- **Accuracy Achieved:** **93%** with SVM model.
- **Models Compared:** Support Vector Machine (SVM), Naive Bayes, Logistic Regression, Random Forest.
- **Dataset Size:** 1500 user-AI message pairs (anonymized).
- **Multi-class classification** with future potential for multi-label support.

---

## 🔧 Methodology

- **Vectorization:** TF-IDF with bigrams (`ngram_range=(1,2)`), stopword removal, 5000 max features.
- **Data Preprocessing:** Label encoding, class balancing using `RandomOverSampler`.
- **Evaluation Metrics:** Accuracy, Precision, Recall, F1-Score.
- **Train/Test Split:** 80/20 split, `random_state=42`.
- **Average Prediction Time:** **0.000081 seconds per message**.

---

## 🧠 Models Summary

| Model              | Accuracy | Avg Time / Msg |
|-------------------|----------|----------------|
| SVM (linear)      | 93%      | 0.00008s       |
| Naive Bayes       | 90–93%   | 0.000001s      |
| Logistic Regression | ~91%   | 0.000001s      |
| Random Forest     | ~91%     | 0.000032s      |

---

## 📂 Repository Structure

```bash
├── report/                # Full academic report (PDF)
├── src/                   # Model training and evaluation scripts
├── notebooks/             # Jupyter notebooks (EDA, training)
├── data/                  # Not included – see explanation below
├── requirements.txt       # Dependencies
├── README.md              # This file
