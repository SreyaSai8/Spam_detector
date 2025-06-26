# 🧠 Spam Detector API

A production-grade, containerized microservice to classify text as **spam** or **not_spam**, powered by **scikit-learn** and **FastAPI**. The model is trained on India-specific spam data and operates fully offline. All runtime behavior is configurable via `config.json`.

---

## 🚀 Features

- Fast and lightweight REST API using **FastAPI**
- Classifies posts/comments using **Naive Bayes + TF-IDF**
- Fully **offline**, **containerized** (Docker-ready)
- Accepts **JSON** input and returns **label + confidence score**
- Driven via **runtime config** (`config.json`)
- Compliant with **JSON Schema** (`schema.json`)
- Includes health & version check endpoints
- Logs predictions (if enabled in config)

---

## 📁 Project Structure

spam-detector/
├── app/
│ ├── main.py # FastAPI app entry point
│ ├── generator.ipynb # Model loading and prediction logic
│ └── model/ # Pretrained model + vectorizer (.joblib)
├── config.json # Runtime settings (required)
├── schema.json # JSON structure for validation
├── data/
│ └── dataset.json # India-specific labeled dataset
├── Dockerfile # For containerized deployment
├── requirements.txt # Python dependencies
├── README.md # Project documentation
└── tests/
  └── test_predict.py # Unit tests


---

## config.json (Required)

Defines runtime model settings:

```json
{
  "model_name": "spam_Navie",
  "version": "1.0.0",
  "confidence_threshold": 0.6,
  "labels": ["spam", "not_spam"],
  "log_predictions": true
}
