# Emoji-Based Sentiment Analysis 😊📊

## Overview
This project performs **sentiment analysis on social media text**, including both **text and emojis**.

It uses a **hybrid approach**:
- Machine Learning (Naive Bayes) → for text
- Rule-Based Method → for emojis  

The goal is to better understand real-world online sentiment, where emojis play a big role.

---

## Features
- Classifies text as **Positive or Negative**
- Detects and analyzes **emoji sentiment**
- Combines text + emoji sentiment into a final result
- Uses **TF-IDF** for feature extraction
- Evaluates performance using:
  - Accuracy
  - Precision
  - Recall
  - F1 Score
  - ROC Curve
- Compares results with other models:
  - TextBlob
  - VADER
  - Flair
  - RoBERTa

---

## Dataset
- **Sentiment140 Dataset** (tweets)
- Custom **Emoji Sentiment Dataset**

---

## Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- NLTK
- Matplotlib, Seaborn
- Emoji library
- Google Colab

---

## How It Works

### 1. Data Preprocessing
- Clean tweets (remove links, usernames, symbols)
- Convert text to lowercase
- Remove stopwords
- Extract emojis separately

### 2. Feature Engineering
- Use **TF-IDF** to convert text into numerical features

### 3. Model Training
- Train a **Multinomial Naive Bayes classifier**
- Split data into training and testing sets

### 4. Emoji Sentiment
- Assign each emoji:
  - `1 = Positive`
  - `0 = Negative`
- Based on dataset frequency

### 5. Hybrid Sentiment Calculation
Final sentiment = average of:
- Text sentiment (ML model)
- Emoji sentiment (rule-based)

---

## Example

Input:"I love this product 😍😍"

Output:Positive Sentiment


---

## Results
- Achieved solid performance using Naive Bayes
- Hybrid approach improves real-world accuracy
- Model handles emoji-heavy text better than text-only models

---

## Extra Features
- Interactive input (user can test their own text)
- Sentiment percentage calculation
- Visualization:
  - Confusion Matrix
  - ROC Curve
  - Precision / Recall / F1 charts

---

## Limitations
- Limited dataset size (10k used from 1.6M)
- Emoji meanings can be context-dependent
- Sarcasm is difficult to detect
- Cultural differences affect interpretation

---

## Future Improvements
- Use deep learning models (LSTM, Transformers)
- Improve emoji understanding with ML
- Expand dataset (multi-language support)
- Better handling of sarcasm and context

