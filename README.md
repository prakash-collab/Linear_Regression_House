# 🏡 House Price Prediction using Machine Learning & AWS

An end-to-end Machine Learning project that predicts house prices using supervised learning techniques. This project follows a production-oriented architecture by integrating Machine Learning with AWS services such as Amazon S3 and AWS Lambda to automate training and prediction workflows.

---

# 📌 Project Overview

The objective of this project is to build a scalable and production-ready House Price Prediction pipeline.

The project demonstrates:

* Exploratory Data Analysis (EDA)
* Data Preprocessing
* Feature Engineering
* Model Training & Evaluation
* Model Versioning
* Event-driven architecture using AWS Lambda
* Amazon S3 Integration
* CI/CD using GitHub Actions
* Modular Python Project Structure

---

# 🎯 Problem Statement

Given various characteristics of a house such as location, size, number of rooms, garage capacity, neighborhood, and other features, predict the selling price of the house using Machine Learning.

---

# 🏗️ Project Architecture

```text
                           +----------------------+
                           |  Housing Dataset     |
                           |      (CSV File)      |
                           +----------+-----------+
                                      |
                                      |
                                      ▼
                           +----------------------+
                           |      Amazon S3       |
                           |   training/ folder   |
                           +----------+-----------+
                                      |
                           S3 Object Created Event
                                      |
                                      ▼
                         +---------------------------+
                         |     AWS Lambda            |
                         |  (Training Function)      |
                         +------------+--------------+
                                      |
                                      ▼
                         +---------------------------+
                         | Data Ingestion            |
                         +------------+--------------+
                                      |
                                      ▼
                         +---------------------------+
                         | Data Preprocessing        |
                         +------------+--------------+
                                      |
                                      ▼
                         +---------------------------+
                         | Feature Engineering       |
                         +------------+--------------+
                                      |
                                      ▼
                         +---------------------------+
                         | Model Training            |
                         +------------+--------------+
                                      |
                                      ▼
                         +---------------------------+
                         | Model Evaluation          |
                         +------------+--------------+
                                      |
                                      ▼
                         +---------------------------+
                         | Best Model (.pkl)         |
                         +------------+--------------+
                                      |
                                      ▼
                           +----------------------+
                           | Amazon S3 Models     |
                           +----------+-----------+
                                      |
                                      ▼
                           Prediction Pipeline
                                      |
                                      ▼
                           +----------------------+
                           | input/*.csv          |
                           +----------+-----------+
                                      |
                                      ▼
                           +----------------------+
                           | Prediction Lambda    |
                           +----------+-----------+
                                      |
                                      ▼
                           +----------------------+
                           | predictions.csv      |
                           +----------------------+
```

---

# 📂 Project Structure

```text
HousePricePrediction/
│
├── .github/
│   └── workflows/
│       ├── ci.yaml
│       └── deploy.yaml
│
├── Data/
│   ├── Raw/
│   ├── Processed/
│   └── External/
│
├── Evaluation/
│   └── Model_Evaluation.py
│
├── lambda/
│   ├── training_handler.py
│   └── prediction_handler.py
│
├── Models/
│
├── Notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Feature_Engineering.ipynb
│   ├── 03_Model_Training.ipynb
│   └── 04_Model_Evaluation.ipynb
│
├── src/
│   ├── DataIngestion.py
│   ├── DataValidation.py
│   ├── Preprocessing.py
│   ├── FeatureEngineering.py
│   ├── ModelSelection.py
│   ├── Train.py
│   ├── Predict.py
│   ├── utils.py
│   └── config.py
│
├── tests/
│
├── faas-lambda.yaml
├── requirements.txt
├── README.md
└── LICENSE
```

---

# 🚀 Workflow

1. Upload the training dataset to the Amazon S3 `training/` folder.
2. Amazon S3 triggers the Training Lambda function.
3. The Lambda downloads the dataset.
4. Data preprocessing and feature engineering are performed.
5. Multiple Machine Learning models are trained.
6. The best-performing model is selected based on evaluation metrics.
7. The trained model is stored in Amazon S3.
8. Users upload new data to the `input/` folder.
9. The Prediction Lambda loads the trained model.
10. Predictions are generated and stored in the `output/` folder.

---

# 🤖 Machine Learning Models

The following algorithms will be implemented and compared:

* Linear Regression
* Ridge Regression
* Lasso Regression
* ElasticNet
* Random Forest Regressor
* Gradient Boosting Regressor
* XGBoost (Optional)
* LightGBM (Optional)

The best-performing model will be selected based on evaluation metrics.

---

# 📊 Evaluation Metrics

* Mean Absolute Error (MAE)
* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)
* R² Score

---

# ☁️ AWS Services Used

* Amazon S3
* AWS Lambda
* IAM Roles
* CloudWatch Logs

---

# 🛠️ Technologies Used

### Programming

* Python 3.x

### Machine Learning

* Scikit-learn
* NumPy
* Pandas
* Matplotlib
* Seaborn

### Cloud

* AWS Lambda
* Amazon S3

### DevOps

* Git
* GitHub
* GitHub Actions

---

# 📈 Future Enhancements

* MLflow Integration
* Docker Support
* FastAPI Deployment
* Model Versioning
* Feature Store
* Automated Data Validation
* Drift Detection
* CI/CD Deployment Pipeline
* Infrastructure as Code (Terraform/AWS CDK)
* Monitoring and Logging Dashboard

---

# 👨‍💻 Author

**Prakash Khare**

Machine Learning | Data Science | AWS | MLOps | Generative AI

---

# ⭐ If you find this project useful, consider giving it a star!
