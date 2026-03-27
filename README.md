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

Input: i hate this love song 😡❤
Text Sentiment Score: 0.45
Emoji Sentiment Score: 0.50
Final Sentiment Score: 0.48
Final Prediction: Negative

Input: I love it 😍💖
Text Sentiment Score: 0.71
Emoji Sentiment Score: 0.60
Final Sentiment Score: 0.66
Final Prediction: Positive

Input: Its terrible 😡😠
Text Sentiment Score: 0.22
Emoji Sentiment Score: 0.30
Final Sentiment Score: 0.26
Final Prediction: Negative

Input: Not sure 🤔😐
Text Sentiment Score: 0.62
Emoji Sentiment Score: 0.50
Final Sentiment Score: 0.56
Final Prediction: Positive

Input: Great job 😄👏
Text Sentiment Score: 0.61
Emoji Sentiment Score: 0.75
Final Sentiment Score: 0.68
Final Prediction: Positive

Input: i hate everything 😤💔
Text Sentiment Score: 0.12
Emoji Sentiment Score: 0.20
Final Sentiment Score: 0.16
Final Prediction: Negative

Input: Check out this link 😎📱
Text Sentiment Score: 0.75
Emoji Sentiment Score: 0.80
Final Sentiment Score: 0.775
Final Prediction: Positive

Input: Meh… I don’t care 😐
Text Sentiment Score: 0.50
Emoji Sentiment Score: 0.40
Final Sentiment Score: 0.45
Final Prediction: Negative

Input: This is amazing 😍✨
Text Sentiment Score: 0.80
Emoji Sentiment Score: 0.90
Final Sentiment Score: 0.85
Final Prediction: Positive

Input: Worst day ever 😭💀
Text Sentiment Score: 0.10
Emoji Sentiment Score: 0.15
Final Sentiment Score: 0.125
Final Prediction: Negative
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

