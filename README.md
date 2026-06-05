# 💤 SleepWell AI

### Explainable AI + RAG-based Sleep Health Assessment System

SleepWell AI is an intelligent healthcare assistant that predicts sleep disorder risks using machine learning and explains the prediction using SHAP explainability. The system further enhances trust by retrieving real medical literature from PubMed and EuropePMC and generating evidence-grounded recommendations using the Phi-3 Mini LLM.

---

# 🚀 Features

* ✅ Sleep disorder prediction using Random Forest
* ✅ Explainable AI with SHAP local feature explanations
* ✅ Personalized patient-level interpretation
* ✅ Retrieval-Augmented Generation (RAG)
* ✅ Live PubMed + EuropePMC evidence retrieval
* ✅ Phi-3 Mini LLM integration
* ✅ Interactive Gradio web interface
* ✅ Medical-safe response formatting
* ✅ Evidence-backed sleep hygiene recommendations

---

# 🧠 Problem Statement

Traditional healthcare ML systems often behave like black boxes.
Patients receive predictions but do not understand:

* why the prediction was made,
* which health factors contributed most,
* or what actions they should take.

SleepWell AI addresses this by combining:

1. Explainable machine learning,
2. Medical literature retrieval,
3. LLM-based reasoning.

The goal is to create a transparent and trustworthy AI healthcare assistant.

---

# 🏗 System Architecture

User Input → Random Forest Prediction → SHAP Explainability → PubMed/EuropePMC Retrieval → Phi-3 Mini LLM → Personalized Recommendation

---

# ⚙️ Tech Stack

## Machine Learning

* Scikit-learn
* Random Forest Classifier
* SHAP

## Retrieval & Embeddings

* Sentence Transformers
* FAISS Vector Search
* PubMed API
* EuropePMC API

## LLM

* Phi-3 Mini (GGUF)
* llama-cpp-python

## Frontend

* Gradio

## Data Processing

* Pandas
* NumPy

---

# 📂 Dataset

Dataset Used:

* Sleep Health and Lifestyle Dataset (Kaggle)

Features include:

* Sleep Duration
* Stress Level
* Physical Activity
* BMI Category
* Blood Pressure
* Heart Rate
* Daily Steps
* Sleep Disorder Labels

Target Classes:

* Healthy
* Insomnia
* Sleep Apnea

---

# 🔍 Explainable AI Pipeline

## Step 1 — Train Random Forest Model

The Random Forest classifier predicts the sleep disorder category based on lifestyle and health parameters.

## Step 2 — SHAP Explainability

TreeExplainer computes local SHAP values for every patient prediction.

This shows:

* which features increased risk,
* which features reduced risk,
* and how strongly each feature contributed.

Unlike global feature importance, SHAP explanations are personalized per patient.

## Step 3 — Retrieval-Augmented Generation

Relevant medical papers are retrieved from:

* PubMed
* EuropePMC

The retrieved evidence is injected into the Phi-3 Mini prompt to generate grounded recommendations.

---

# 🧪 Key Challenges Solved

## 1. Hallucination Reduction

Early LLM outputs sometimes generated unsupported medical claims.

Solution:

* strict prompt engineering,
* evidence-only constraints,
* citation-aware prompting.

---

## 2. Class Imbalance

Sleep disorder classes were imbalanced.

Solution:

* minority class upsampling,
* balanced Random Forest training.

---

## 3. SHAP Interpretation Alignment

LLM recommendations sometimes conflicted with SHAP explanations.

Solution:

* SHAP outputs were injected directly into the LLM prompt as reasoning context.

---

# 📊 Model Performance

Metrics Evaluated:

* Accuracy
* Precision
* Recall
* F1 Score

The Random Forest model achieved strong classification performance while maintaining interpretability.

---

# 🖥️ Gradio Interface

The application provides:

* Sleep disorder prediction
* Confidence score
* SHAP feature explanations
* Evidence-backed recommendations
* Retrieved research papers

---

# 📦 Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/SleepWell-AI.git
cd SleepWell-AI
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Run Application

```bash
python app.py
```


