# 🧠 Hybrid Sentiment Analysis with Emoji Understanding

This project implements a **hybrid sentiment analysis system** that combines machine learning and rule-based techniques to analyze social media text, including emojis, and classify sentiment as positive, negative, or neutral.

Unlike traditional models, this system explicitly accounts for **emoji sentiment**, making it more aligned with real-world communication.

---

## 🚀 Key Features

- 📊 Machine Learning-based sentiment classification using **Multinomial Naive Bayes**
- 🔤 Text preprocessing with **TF-IDF feature extraction**
- 😀 Rule-based **emoji sentiment analysis**
- 🔗 Hybrid model combining text + emoji sentiment
- 📈 Performance evaluation using:
  - Accuracy, Precision, Recall, F1-score
  - Confusion Matrix
  - ROC Curve & AUC Score
- ⚖️ Comparison with multiple models:
  - TextBlob
  - VADER
  - Flair
  - RoBERTa (Transformer-based)
- 🧪 Interactive sentiment testing using user input
- 🖥️ Simple UI using `ipywidgets` for real-time predictions

---

## ⚙️ Methodology

### 1. Data Collection
- Used a subset (10,000 samples) of the **Sentiment140 dataset**
- Balanced dataset with positive and negative tweets

### 2. Data Preprocessing
- Removed:
  - Usernames (@)
  - Links
  - Special characters
- Converted text to lowercase
- Removed stopwords using NLTK

---

### 3. Feature Engineering
- Applied **TF-IDF (Term Frequency - Inverse Document Frequency)**
- Converted text into numerical feature vectors

---

### 4. Model Training
- Used **Multinomial Naive Bayes classifier**
- Dataset split:
  - 75% training
  - 25% testing
- Evaluated using ROC-AUC and classification metrics

---

### 5. Emoji Sentiment Analysis (Rule-Based)

- Emoji dataset processed to assign:
  - `1 → Positive`
  - `0 → Negative`
- Sentiment determined based on frequency of usage in positive vs negative contexts

Example:❤❤😡 → [1, 1, 0] → Average = 0.66 (Positive leaning)

---

### 6. Hybrid Sentiment Calculation

- Text and emoji are processed separately:
  - Text → ML model
  - Emoji → Rule-based system

- Final sentiment score:

- Final Score = (Text Score + Emoji Score) / (Number of Emojis + 1)


- Output classified as:
  - Positive
  - Negative
  - Neutral

---

## 🧪 Example

| Input                     | Text Sentiment | Emoji Sentiment | Final Score | Prediction |
| ------------------------- | -------------- | --------------- | ----------- | ---------- |
| i hate this love song 😡❤ | 0.45           | 0.50            | 0.48        | Negative   |
| I love it 😍💖            | 0.71           | 0.60            | 0.66        | Positive   |
| Its terrible 😡😠         | 0.22           | 0.30            | 0.26        | Negative   |
| Not sure 🤔😐             | 0.62           | 0.50            | 0.56        | Positive   |
| Great job 😄👏            | 0.61           | 0.75            | 0.68        | Positive   |
| i hate everything 😤💔    | 0.12           | 0.20            | 0.16        | Negative   |
| Check out this link 😎📱  | 0.75           | 0.80            | 0.78        | Positive   |
| Meh… I don’t care 😐      | 0.50           | 0.40            | 0.45        | Negative   |
| This is amazing 😍✨       | 0.80           | 0.90            | 0.85        | Positive   |
| Worst day ever 😭💀       | 0.10           | 0.15            | 0.13        | Negative   |

---

## 📊 Model Evaluation

The model was evaluated using:

- Accuracy  
- Precision  
- Recall  
- F1 Score  
- Confusion Matrix  
- ROC Curve (AUC Score)  

Visualization includes:
- Confusion matrix heatmap
- ROC curve plot
- Performance comparison bar charts

---

## ⚖️ Model Comparison

The system compares results across multiple models:

| Model       | Type                  |
|------------|----------------------|
| Naive Bayes | ML (custom trained)  |
| TextBlob    | Lexicon-based        |
| VADER       | Rule-based (social media optimized) |
| Flair       | Deep learning        |
| RoBERTa     | Transformer-based    |

This allows analysis of:
- Accuracy vs complexity
- Lightweight vs deep models

---

## 🛠️ Technologies Used

- Python  
- Pandas, NumPy  
- NLTK  
- Scikit-learn  
- Matplotlib, Seaborn  
- Emoji  
- Transformers (HuggingFace)  
- Google Colab  
- Ipywidgets  

---
> All implementation is contained within a single notebook.

---
## ⚠️ Limitations

- Difficulty handling sarcasm and context
- Emoji meaning varies across cultures
- Rule-based emoji system lacks contextual awareness
- Limited dataset size (subset used)

---

## 🔮 Future Improvements

- Use deep learning for emoji sentiment
- Improve context awareness (sarcasm detection)
- Expand dataset (multilingual + larger samples)
- Optimize hybrid weighting instead of simple averaging

---

