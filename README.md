# 🧠 Fake News Detection System

> Detecting misinformation using Machine Learning, Deep Learning & Google Fact Check API

![Python](https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-1.57-red?style=for-the-badge&logo=streamlit)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.21-orange?style=for-the-badge&logo=tensorflow)
![Scikit-Learn](https://img.shields.io/badge/ScikitLearn-Latest-green?style=for-the-badge&logo=scikit-learn)
![HuggingFace](https://img.shields.io/badge/🤗%20Hugging%20Face-Spaces-yellow?style=for-the-badge)

---

## 🌐 Live Demo

> 🔗 **[Click here to try the app](https://huggingface.co/spaces/ANSHULmavi07/fake-news-detector)**
>
> _(If the app shows "Starting...", wait 60 seconds — it wakes up automatically)_

---

## 📌 Project Overview

This project is an end-to-end **Fake News Detection Web Application** built as part of a Machine Learning assignment. It scrapes real-world fact-check data from [PolitiFact](https://www.politifact.com/), trains multiple ML and Deep Learning models, and deploys them in an interactive web app where users can enter any news statement and get an instant verdict.

---

## 🗂️ Dataset

- **Source:** Scraped from [PolitiFact.com](https://www.politifact.com/factchecks/list/) — ~300 pages
- **Total Records:** ~2900+ fact-checked statements
- **Features:** `authors`, `dates`, `statements`, `sources`, `targets`
- **Target:** Binary classification — `1 = Real`, `0 = Fake`
- **Class Distribution:** ~94% Fake / ~6% Real (highly imbalanced → handled with SMOTE)

---

## 🔍 Exploratory Data Analysis (EDA)

- ✅ Missing value detection & removal
- ✅ Duplicate detection & removal
- ✅ Class distribution visualization
- ✅ Text length & word count analysis
- ✅ WordCloud for most common words
- ✅ Real vs Fake word comparison
- ✅ Correlation heatmap
- ✅ Outlier detection via boxplot

---

## ⚙️ Data Preprocessing

- Lowercasing & punctuation removal
- Stopword removal using NLTK
- TF-IDF Vectorization (for ML models)
- Keras Tokenizer + Padding (for Deep Learning models)
- **SMOTE** applied to handle class imbalance

---

## 🤖 Models Trained

| Model | Type | Description |
|-------|------|-------------|
| **Best ML Model** | Traditional ML | Trained inside a sklearn Pipeline with TF-IDF |
| **ANN** | Deep Learning | Artificial Neural Network using Keras |
| **RNN** | Deep Learning | Recurrent Neural Network using Keras |

### 🗳️ Final Verdict Logic
A **majority voting** system is used:
- If 2 or more models say **"Fake"** → Final verdict = ❌ Fake
- If 2 or more models say **"Real"** → Final verdict = ✅ Real

---

## 🌐 Google Fact Check API

The app also queries the **Google Fact Check Tools API** in real-time to cross-verify the statement against known fact-checked claims from trusted publishers worldwide.

---

## 🖥️ Web Application

Built with **Streamlit** and deployed on **Hugging Face Spaces**.

### Features:
- 📰 Enter any news statement
- 🧠 Get predictions from ML, ANN, and RNN models
- 🗳️ See the final majority-vote verdict
- 🌐 Cross-check with Google Fact Check API
- 🎨 Custom dark-themed UI with color-coded results



## 📁 Project Structure

```
fake-news-detector/
│
├── app.py                  # Streamlit web application
├── requirements.txt        # Python dependencies
├── Dockerfile              # Container configuration
│
├── best_ml_model.pkl       # Trained ML Pipeline (TF-IDF + Classifier)
├── tokenizer.pkl           # Keras Tokenizer for DL models
├── ann_model.h5            # Trained ANN model
├── rnn_model.h5            # Trained RNN model
│
└── README.md               # This file
```

---

## 🚀 How to Run Locally

```bash
# 1. Clone the repository
git clone https://huggingface.co/spaces/ANSHULmavi07/fake-news-detector
cd fake-news-detector

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the app
streamlit run app.py
```

---

## 📦 Dependencies

```
streamlit
joblib
tensorflow==2.21.0
scikit-learn
requests
numpy
nltk
```

---

## 🧪 Sample Test Cases

| Statement | Expected Result |
|-----------|----------------|
| "Vaccines contain microchips" | ❌ Fake |
| "Government launched new education policy" | ✅ Real |
| "The earth is flat" | ❌ Fake |

---

## 👨‍💻 Author

**Anshul Mavi**
- 🤗 Hugging Face: [@ANSHULmavi07](https://huggingface.co/ANSHULmavi07)

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use and modify.

---

## 🙏 Acknowledgements

- [PolitiFact](https://www.politifact.com/) for the fact-check data
- [Hugging Face Spaces](https://huggingface.co/spaces) for free hosting
- [Google Fact Check Tools API](https://developers.google.com/fact-check/tools/api) for real-time verification
- [Streamlit](https://streamlit.io/) for the web framework
