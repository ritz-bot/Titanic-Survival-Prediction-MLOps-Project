
# 🚢 Titanic Survival Prediction - MLOps Project

This repository contains the implementation of the third project in the MLOps series: **Titanic Survival Prediction**. While the dataset is widely used in introductory machine learning tutorials, this project emphasizes **advanced MLOps practices** over basic model building. The focus is on building **scalable, production-ready pipelines**, including **ETL processes**, **feature management**, and **model monitoring**.

---

## 📚 Table of Contents

- [🎯 Objective](#-objective)  
- [❓ Problem Statement](#-problem-statement)  
- [✨ Highlights](#-highlights)  
- [📂 Dataset](#-dataset)  
- [⚙️ Workflow](#-workflow)  
- [🛠️ Technologies Used](#-technologies-used)  
- [📋 Prerequisites](#-prerequisites)  
- [⚙️ Installation and Setup](#-installation-and-setup)  
- [🚀 Usage](#-usage)  
- [🗂️ Data & Code Versioning](#-data--code-versioning)  
- [🤝 Contributing](#-contributing)  


---

## 🎯 Objective

The goal of this project is to demonstrate an **end-to-end MLOps workflow** for a classic machine learning task—Titanic Survival Prediction. By working with a familiar dataset, we prioritize **MLOps best practices** such as:

- Implementing automated ETL pipelines.
- Integrating a feature store.
- Monitoring for data and concept drift.
- Building a scalable and maintainable deployment pipeline.

This project acts as a **blueprint for real-world production systems**, ensuring **reliability, scalability, and observability**.

---

## ❓ Problem Statement

The Titanic dataset includes passenger data used to predict survival outcomes from the Titanic disaster.

- **Input Features**:  
  `PassengerId`, `Pclass`, `Name`, `Sex`, `Age`, `SibSp`, `Parch`, `Ticket`, `Fare`, `Cabin`, `Embarked`
- **Output Label**:  
  `Survived` (1 = survived, 0 = did not survive)

The aim is to train a **binary classification model** while implementing full MLOps workflows (data ingestion, transformation, training, monitoring, etc.).

---

## ✨ Highlights

This project moves beyond simple ML scripts, focusing on **production-level infrastructure**:

- **ETL Pipelines with Astronomer Airflow**  
  Automates data extraction (from GCP), transformation, and loading into PostgreSQL.

- **Feature Store with Redis (via Docker)**  
  Stores training and inference features efficiently for scalable ML systems.

- **Monitoring with Prometheus & Grafana**  
  Tracks model predictions, drift metrics, and system health via time-series dashboards.

- **Drift Detection with Alibi Detect or Evidently**  
  Identifies data distribution shifts between training and live data.

- **Flask Web App Interface**  
  Simple frontend to input passenger details and get predictions.

- **Modular & Versioned Pipelines**  
  All workflows (training, data ingestion, etc.) are modular and version-controlled (Git + DVC optional).

---

## 📂 Dataset

- **Source**: [Kaggle Titanic Dataset](https://www.kaggle.com/c/titanic)
- **Format**: CSV (`train.csv`, `test.csv`)
- **Usage**: Upload to a GCP bucket for ETL ingestion.

---

## ⚙️ Workflow

1. **Database Setup** – Load CSV to GCP buckets  
2. **ETL Pipeline** – Airflow DAGs transform and load to PostgreSQL  
3. **Feature Store** – Redis Docker container stores features  
4. **Model Training Pipeline** – Ingest → Process → Train → Evaluate  
5. **App Interface** – Flask app for user interaction  
6. **Monitoring** – Prometheus and Grafana for health and performance  
7. **Drift Detection** – Evidently or Alibi for detecting input drift  

---

## 🛠️ Technologies Used

| Category         | Tools/Technologies |
|------------------|--------------------|
| ML & Data        | Scikit-learn, Pandas, NumPy, Joblib |
| ETL & Pipelines  | Astronomer Airflow, PostgreSQL, GCP Buckets |
| Feature Store    | Redis (Docker) |
| Web App          | Flask, HTML/CSS |
| Monitoring       | Prometheus, Grafana |
| Drift Detection  | Evidently, Alibi Detect |
| Versioning       | GitHub, DVC (optional) |
| Containerization | Docker |

---

## 📋 Prerequisites

- Python 3.8+
- Docker installed
- GCP account (Free Tier is sufficient)
- Astronomer CLI (for Airflow)
- Git installed

---

## ⚙️ Installation and Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/mlops-titanic-survival.git
cd mlops-titanic-survival

# Set up virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Upload Titanic CSVs to your GCP bucket

# Initialize Airflow project
astro dev init

# Start Redis via Docker
docker run -p 6379:6379 redis

# Set up PostgreSQL (Docker or local)
```




## 🚀 Usage

```bash
# Run training pipeline
python src/pipelines/train_pipeline.py

# Launch the Flask app
python app.py  # Visit http://localhost:5000

# Start Prometheus
prometheus --config.file=prometheus.yml

# Launch Grafana and connect Prometheus


# Trigger Airflow DAGs via UI
```
**## 🗂️ Data & Code Versioning

- **Code**: Versioned using **Git** & **GitHub**.
- **Data**:
  - **Small datasets**: Store directly in the repository.
  - **Large datasets**: Use **[DVC](https://dvc.org/)** for efficient versioning and tracking.

---

## 🤝 Contributing

Contributions are welcome!

To contribute:

```bash
# 1. Fork the repository

# 2. Create a new feature branch
git checkout -b feature/your-feature

# 3. Make your changes and commit
git commit -m "Add new feature"

# 4. Push to your fork
git push origin feature/your-feature

# 5. Open a Pull Request on GitHub
**
```
