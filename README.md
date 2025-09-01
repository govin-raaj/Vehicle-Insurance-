# 🚀 Vehicle Data MLOps Project

An **end-to-end MLOps pipeline** demonstrating modern machine learning practices – from **data ingestion, validation, transformation, training, model registry, CI/CD, to cloud deployment on AWS EC2**.

This project is designed not only as a technical implementation but also as a **portfolio showcase** to highlight skills in:

✅ **Machine Learning** (EDA, feature engineering, model training, evaluation)
✅ **MLOps** (workflow orchestration, CI/CD, AWS integration, Docker, GitHub Actions)
✅ **Cloud & Database** (MongoDB Atlas, AWS S3, EC2, IAM, ECR)
✅ **Software Engineering** (logging, exception handling, modular project structure, local package management)

---

## 📂 Project Structure

```
.
├── constants
├── config_entity
├── artifact_entity
├── component
├── pipeline
├── app.py / demo.py
├── requirements.txt
├── setup.py
├── pyproject.toml
└── notebook/
```

---

## ⚙️ Getting Started

### 🔧 Project Setup

```bash
# 1. Create project template
python template.py

# 2. Setup virtual environment
conda create -n vehicle python=3.10 -y
conda activate vehicle

# 3. Install dependencies
pip install -r requirements.txt

# 4. Verify local packages
pip list
```

---

## 🗄️ MongoDB Atlas Integration

* **Cloud database setup** for storing and retrieving structured data.
* **Steps covered:**

  * Create a project & free cluster (M0)
  * Setup DB user & IP access (`0.0.0.0/0`)
  * Obtain connection string (Python driver 3.6+)
  * Push dataset from Jupyter notebook → Verify in MongoDB Atlas

📒 Example notebook: `notebook/mongoDB_demo.ipynb`

---

## 📜 Logging & Exceptions

* Centralized **logging** for monitoring pipeline execution
* **Custom exception handling** for robust error tracking
* Both integrated & tested in `demo.py`

---

## 🔄 Workflow Components

1. **Data Ingestion**

   * Fetch data from MongoDB
   * Transform into pandas DataFrame
   * Save ingestion artifacts

2. **Data Validation**

   * Schema-based validation (`config/schema.yaml`)
   * Missing/invalid data checks

3. **Data Transformation**

   * Feature engineering
   * Estimator setup

4. **Model Trainer**

   * Train ML model
   * Store artifacts

5. **Model Evaluation & Pusher**

   * Evaluate trained model vs previous version
   * Push to **AWS S3 model registry**

---

## ☁️ AWS Cloud Setup

* **IAM User** with `AdministratorAccess`
* **AWS S3** for model storage
* **Environment Variables** for access & secret keys
* **Configuration files** for S3 integration

### Example constants:

```python
MODEL_EVALUATION_CHANGED_THRESHOLD_SCORE: float = 0.02
MODEL_BUCKET_NAME = "my-model-mlopsproj"
MODEL_PUSHER_S3_KEY = "model-registry"
```

---

## 🐳 CI/CD with Docker & GitHub Actions

* **Dockerized application** with `Dockerfile` & `.dockerignore`
* **GitHub Actions workflow** for CI/CD pipeline (`.github/workflows/aws.yaml`)
* **AWS ECR** for storing Docker images
* **AWS EC2 (Ubuntu)** as deployment server (self-hosted runner)

🔑 GitHub Secrets Required:

* `AWS_ACCESS_KEY_ID`
* `AWS_SECRET_ACCESS_KEY`
* `AWS_DEFAULT_REGION`
* `ECR_REPO`

---

## 🌐 Deployment

* Application runs on **EC2 instance**
* Custom TCP port `5000` opened for access
* Launch app at:

```
http://<EC2-PUBLIC-IP>:5080
```

---

## 📊 Features

* ✅ End-to-End ML Pipeline
* ✅ Cloud-native (MongoDB + AWS S3 + EC2 + ECR)
* ✅ Automated CI/CD with GitHub Actions
* ✅ Dockerized microservice
* ✅ Robust logging & exception handling
* ✅ Modular, production-grade project structure

---

## 🛠️ Tech Stack

* **Languages**: Python (3.10), YAML
* **ML/DL**: Pandas, NumPy, Scikit-learn
* **Database**: MongoDB Atlas
* **Cloud**: AWS S3, EC2, ECR, IAM
* **DevOps**: Docker, GitHub Actions (CI/CD)
* **Tools**: Logging, Exception handling, Jupyter

---

## 🎯 Project Workflow Summary
* Data Ingestion ➔ Data Validation ➔ Data Transformation
* Model Training ➔ Model Evaluation ➔ Model Deployment
* CI/CD Automation with GitHub Actions, Docker, AWS EC2, and ECR

---

This README provides a structured walkthrough of the MLOps project, showcasing the end-to-end pipeline, cloud integration, CI/CD setup, and robust data handling capabilities.

---
