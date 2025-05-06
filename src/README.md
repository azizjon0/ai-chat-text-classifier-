# Source Code – Machine Learning Models

This folder contains the core code used to build, train, and evaluate different machine learning models for classifying chatbot messages.

## 📂 Files

| Filename                    | Description |
|----------------------------|-------------|
| `SVC.ipynb`                | Implements a Support Vector Classifier (SVM) with linear kernel. Achieved the best results with 93% accuracy. |
| `MultinomialNB.ipynb`      | Naive Bayes classifier using TF-IDF features. Lightweight, fast, but slightly less accurate. |
| `LogisticRegression.ipynb` | Binary/multi-class classification using logistic regression. Performed well with fast inference. |
| `RandomForestClassifier.ipynb` | Random forest ensemble model. Slower but provides good interpretability. |
| `README.md`                | This file – describes the contents of this directory. |

## 🧠 Notes

- All models use the same preprocessing pipeline: TF-IDF vectorization, label encoding, and class balancing with oversampling.
- The dataset is excluded for privacy reasons – see the `/data/README.md` for dataset structure.
- Models were tested on the same train/test split (80/20) for fair comparison.

---

Feel free to reuse or adapt these notebooks to build multi-label or deep learning versions.

