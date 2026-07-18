<div align="center">

# 🩺 Disease Detection & Medicine Recommendation System

### AI-powered symptom checker that predicts diseases and recommends care — instantly.

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-Web%20App-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML%20Model-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://vercel.com/)

</div>

---

## ✨ Overview

Type in your symptoms, and this app tells you the **likely disease** — along with a description, **precautions**, **medications**, **diet recommendations**, and a **workout plan** to help you recover. It's a full-stack machine learning web app built with **Flask** on the backend and a **Support Vector Classifier (SVC)** trained on a multi-class symptom-to-disease dataset.

> ⚠️ **Disclaimer:** This project is for educational purposes only and is **not** a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified physician.

---

## 🚀 Features

| Feature | Description |
|---|---|
| 🔍 **Symptom-based Prediction** | Enter comma-separated symptoms and get an instant disease prediction |
| 📖 **Disease Description** | Learn what the predicted disease actually means |
| 🛡️ **Precautions** | Get 4 key precautionary steps to manage the condition |
| 💊 **Medication Suggestions** | Receive relevant medicine recommendations |
| 🥗 **Diet Plan** | Personalized dietary guidance for recovery |
| 🏋️ **Workout Recommendations** | Suggested exercises suited to the condition |
| 🌐 **Multi-page Web App** | Home, About, Blog, Contact & Developer pages |

---

## 🧠 How It Works

```
┌─────────────────┐     ┌──────────────────┐     ┌─────────────────────┐
│  User Symptoms   │ --> │  SVC ML Model    │ --> │  Predicted Disease   │
│  (comma sep.)    │     │  (svc.pkl)       │     │                      │
└─────────────────┘     └──────────────────┘     └──────────┬───────────┘
                                                              │
                     ┌────────────────────────────────────────┼─────────────────────────┐
                     ▼                        ▼                ▼                        ▼
              Description CSV         Precautions CSV    Medications CSV          Diet & Workout CSV
```

1. **Input** — the user submits symptoms via the web form.
2. **Vectorization** — symptoms are mapped into a binary feature vector using a 132-symptom dictionary.
3. **Prediction** — a pre-trained **SVC (linear kernel)** model predicts one of 41 diseases.
4. **Enrichment** — the app looks up the disease across five datasets (`description`, `precautions`, `medications`, `diets`, `workout`) and returns a complete health summary.

---

## 🤖 Model Training

Multiple classifiers were benchmarked during development (see the included Jupyter notebook):

- ✅ **Support Vector Classifier (SVC)** — *selected model*
- Random Forest Classifier
- Gradient Boosting Classifier
- K-Nearest Neighbors
- Multinomial Naive Bayes

The final **SVC (linear kernel)** model was serialized with `pickle` and is loaded by the Flask app at runtime for real-time predictions.

---

## 🗂️ Project Structure

```
├── main.py                                              # Flask application & routes
├── model/
│   └── svc.pkl                                          # Trained SVC model
├── Dataset/
│   ├── description.csv                                  # Disease descriptions
│   ├── precautions_df.csv                                # Precautionary measures
│   ├── medications.csv                                   # Medication data
│   ├── diets.csv                                         # Diet recommendations
│   └── workout_df.csv                                    # Workout suggestions
├── templates/
│   ├── index.html                                        # Home / prediction page
│   ├── about.html                                        # About page
│   ├── blog.html                                         # Blog page
│   ├── contact.html                                       # Contact page
│   └── developer.html                                     # Developer info page
├── Disease detection and medicine recommendation system.ipynb   # Model training notebook
├── requirements.txt                                       # Python dependencies
├── pyproject.toml                                         # Project metadata
├── vercel.json                                            # Vercel deployment config
└── .gitignore
```

---

## ⚙️ Getting Started

### 1️⃣ Clone the repository
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

### 2️⃣ Install dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Run the app
```bash
python main.py
```

### 4️⃣ Open in your browser
```
http://127.0.0.1:5000
```

---

## 🌍 Routes

| Route | Description |
|---|---|
| `/` | Home page with the symptom prediction form |
| `/predict` | Handles form submission and returns prediction results |
| `/about` | About the project |
| `/blog` | Blog page |
| `/contact` | Contact page |
| `/developer` | Meet the developer |

---

## 🛠️ Tech Stack

- **Backend:** Flask (Python)
- **Machine Learning:** scikit-learn (SVC)
- **Data Handling:** pandas, numpy
- **Frontend:** HTML (Jinja2 templates)
- **Deployment:** Vercel

---

## 🧾 Symptom Format

Symptoms must be entered comma-separated, matching the model's known symptom list, e.g.:

```
itching, skin_rash, joint_pain, high_fever
```

---

## 📌 Roadmap Ideas

- [ ] Add a searchable/autocomplete symptom selector in the UI
- [ ] Expose a REST API endpoint for predictions
- [ ] Add confidence scores to predictions
- [ ] Add unit tests and CI pipeline
- [ ] Improve model accuracy with additional data & tuning

---

<div align="center">

Made with ❤️ and a lot of `pip install`

⭐ **If you find this project useful, consider giving it a star!** ⭐

</div>
