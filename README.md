# 🏠 NYC Airbnb Room Type Predictor

A Machine Learning classification project that predicts the **room type of Airbnb listings in New York City** using listing, location, pricing, review, and availability features.

## 🌐 Live Demo

🚀 **Live Application:** [NYC Airbnb Room Type Predictor](https://nyc-airbnb-room-type-predictor-ml-1.onrender.com/)

🔗 **Live API:** [FastAPI API](https://nyc-airbnb-room-type-predictor-ml.onrender.com/)

📖 **API Documentation:** [Swagger API Docs](https://nyc-airbnb-room-type-predictor-ml.onrender.com/docs)

---

## 📌 About The Project

The **NYC Airbnb Room Type Predictor** uses historical Airbnb listing data to build a machine learning model capable of predicting the type of room offered by a listing.

The project covers the complete Machine Learning workflow:

**Data → EDA → Preprocessing → Feature Engineering → Model Training → Evaluation → Model Selection → Prediction API**

### 🎯 Prediction Target

The model predicts the Airbnb room type:

* `Entire home/apt`
* `Private room`
* `Shared room`

This is a **multiclass classification** problem.

---

## ✨ Features

* 📊 Exploratory Data Analysis
* 🧹 Data Cleaning & Preprocessing
* ⚙️ Feature Engineering
* 🔤 Categorical Feature Encoding
* 📏 Numerical Feature Scaling
* 🧩 Missing Value Handling using SimpleImputer
* ⚖️ Class Imbalance Handling
* 🤖 Multiple Machine Learning Algorithms
* 🎯 Model Comparison
* 🔧 Hyperparameter Optimization
* 💾 Trained ML Pipeline
* 🚀 FastAPI Prediction API

---

## 🧠 Machine Learning Workflow

```text
NYC Airbnb Dataset
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
Feature Engineering
        ↓
Preprocessing
        ↓
Class Imbalance Analysis
        ↓
Multiple Model Training
        ↓
Model Comparison
        ↓
Best Model Selection
        ↓
Trained ML Pipeline
        ↓
FastAPI
        ↓
Room Type Prediction
```

---

## 📊 Dataset

The project uses the **New York City Airbnb Open Data** dataset.

Important features include:

| Feature               | Description             |
| --------------------- | ----------------------- |
| `neighbourhood_group` | NYC borough             |
| `neighbourhood`       | Neighborhood            |
| `latitude`            | Listing latitude        |
| `longitude`           | Listing longitude       |
| `price`               | Listing price           |
| `minimum_nights`      | Minimum nights required |
| `number_of_reviews`   | Total reviews           |
| `reviews_per_month`   | Monthly review average  |
| `availability_365`    | Annual availability     |
| `room_type`           | Prediction target       |

---

## 🤖 Machine Learning

Multiple classification algorithms were trained and evaluated to determine the most suitable model for the Airbnb room-type prediction task.

### Models Compared

| Model               |  Accuracy |  F1 Score |
| ------------------- | --------: | --------: |
| Logistic Regression | **65.9%** | **0.522** |
| Decision Tree       | **78.2%** | **0.647** |
| Random Forest       | **85.1%** | **0.715** |
| Gradient Boosting   | **85.0%** | **0.705** |

### 🏆 Best Performing Model

**Random Forest** achieved the highest overall performance:

* **Accuracy:** 85.1%
* **F1 Score:** 0.715

Gradient Boosting performed very closely:

* **Accuracy:** 85.0%
* **F1 Score:** 0.705

Based on the evaluation results, **Random Forest was selected as the final prediction model**.

---

## ⚖️ Class Imbalance Handling

The Airbnb room-type dataset contains an **imbalanced target distribution**, meaning some room categories have significantly more samples than others.

To reduce the effect of class imbalance, `class_weight` was applied to selected classification models.

### Class Weight Configuration

| Model               | Class Weight              |
| ------------------- | ------------------------- |
| Logistic Regression | `class_weight="balanced"` |
| Decision Tree       | `class_weight="balanced"` |
| Random Forest       | `class_weight="balanced"` |
| Gradient Boosting   | Not applied               |

Gradient Boosting were evaluated **without class weighting**, while Logistic Regression, Decision Tree and Random  used balanced class weights.

This allowed the models to be compared under different imbalance-handling strategies rather than applying the same configuration to every algorithm.

> **Note:** Accuracy alone can be misleading for imbalanced classification. Therefore, F1 Score was also considered when comparing model performance.

---

## 📈 Model Evaluation

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

The **F1 Score** was given additional importance because the dataset contains imbalanced room-type classes.

---

## 🚀 FastAPI

The trained ML pipeline is integrated with **FastAPI** to provide real-time predictions through a REST API.

### Endpoints

```http
GET  /
POST /predict
```

Example prediction response:

```json
{
  "prediction": "Private room"
}
```

Swagger API documentation is available at:

```text
http://127.0.0.1:8000/docs
```

---

## 🛠️ Tech Stack

**Language**

* Python

**Data Science & Machine Learning**

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

**API & Deployment**

* FastAPI
* Uvicorn
* Pydantic

**Tools**

* Jupyter Notebook
* Git
* GitHub

---

## 📁 Project Structure

```text
NYC-Airbnb-Room-Type-Predictor/
│
├── AB_NYC_2019.csv
├── nyc_airnb_room.ipynb
├── main.py
├── Model_Pipeline.pkl
├── index.html
├── script.js
├── style.css
├── runtime.txt
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 💻 Installation

### Clone Repository

```bash
git clone https://github.com/YashPatel1912/NYC-Airbnb-Room-Type-Predictor-ML.git
cd NYC-Airbnb-Room-Type-Predictor-ML
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run FastAPI

```bash
python -m uvicorn main:app --reload
```

Open:

```text
http://127.0.0.1:8000/
```

API documentation:

```text
http://127.0.0.1:8000/docs
```

---

## 👨‍💻 Author

**Yash Patel**

Computer Engineering Student | Full Stack Developer | Machine Learning & DevOps Enthusiast

---

⭐ **If you find this project useful, consider giving it a star!**
