# Spam Mail Detection using the Pattern Growth Approach  
**Final Term Project – Data Mining**

## Group Members
- **Luong Anh Huy** – 22520550  
- **Pham Dong Hung** – 22520521  
- **Phan Cong Minh** – 22520884  
- **Instructor**: Vo Nguyen Le Duy  

---

## Overview

This project explores the application of the **Frequent Pattern Growth (FP-Growth)** algorithm and **Association Rule Mining** to classify spam emails. While these methods are typically used in data mining rather than classification tasks, they provide an interesting alternative for spam detection, leveraging frequent co-occurrence of words in spam vs. non-spam messages.

---

## Dataset

- **Source**: [Kaggle SMS Spam Collection Dataset](https://raw.githubusercontent.com/mohitgupta-1O1/Kaggle-SMS-Spam-Collection-Dataset-/master/spam.csv)
- **Size**: 5,572 emails
  - **Spam**: 747 messages (13.41%)
  - **Ham**: 4,825 messages (86.59%)

### Preprocessing Steps:
- Removed irrelevant columns and retained `label` and `message`
- Text normalization: lowercasing, removing punctuation, etc.
- Stopword removal
- Label encoding (`ham` → 0, `spam` → 1)
- Removed duplicates
- Tokenized messages into word lists

---

## Methodology

### FP-Growth Algorithm
- A data mining technique for mining frequent itemsets without candidate generation
- Uses **FP-tree** for efficient pattern storage

### Association Rule Mining
- Derives rules like: `{word1, word2} → {spam}`  
- Metrics used: **support**, **confidence**

### Classification Process
- Messages are tokenized and transformed into transaction format
- FP-Growth is used to generate frequent word sets for spam and ham
- Association rules are derived for each class
- A new message is classified based on which set of rules (spam or ham) it matches more strongly (higher confidence)

---

## Results & Analysis

### Pros:
- Capable of finding meaningful word associations in spam vs. ham
- Efficient with large datasets

### Cons:
- Struggles with **imbalanced datasets**
- Sensitive to chosen **support/confidence thresholds**
- Generates a large number of rules, hard to manage
- Not commonly used for classification, so performance lags behind standard models (e.g., Logistic Regression, Naive Bayes)

---

## Comparison with Traditional Classifiers

Though not the primary focus, the study mentions that traditional classifiers like Logistic Regression and Naive Bayes generally outperform the FP-Growth + AR combination in classification tasks.

---

## Limitations & Future Work

### Challenges:
- Low accuracy on unseen/spontaneous examples
- Poor generalization due to lack of multi-dataset training

### Future Directions:
- Enhance preprocessing and feature engineering
- Train and evaluate on multilingual datasets
- Combine FP-Growth with modern classifiers for hybrid models
---

## 🎓 Course Information

- **Subject**: Data Mining  
- **Institution**: University of Information Technology – VNUHCM  
- **Semester**: Final Term Project  

---
