⚙️ Machine Failure Analysis & Predictive Maintenance

An End-to-End Machine Learning Project for Industrial Failure Prediction and Failure-Type Classification

This project applies Machine Learning, Data Analysis, and Business Intelligence to industrial predictive maintenance. It aims to identify machines at risk of failure, estimate failure probability, classify potential failure types, and present insights through interactive visualizations.

The project combines Python-based data analysis and machine learning with Power BI dashboards to transform industrial data into actionable insights.

---

📌 Project Overview

Unexpected machine failures can lead to production downtime, maintenance costs, and operational disruption.

This project explores how machine learning can support predictive maintenance by analyzing machine operating conditions and identifying patterns associated with equipment failure.

The solution focuses on two machine learning tasks:

- Binary Failure Prediction: Predict whether a machine is likely to experience a failure.
- Failure-Type Classification: Classify the potential failure into one of the supported failure categories.

The results are complemented by visual analytics to help users understand machine behavior, failure patterns, and operational risks.

🎯 Project Objectives

- Analyze industrial sensor and operating-condition data.
- Identify patterns associated with machine failures.
- Develop machine learning models for failure prediction.
- Classify potential failure types.
- Evaluate model performance using multiple classification metrics.
- Communicate findings through Python visualizations and Power BI dashboards.
- Explore how data-driven methods can support predictive maintenance decisions.

🗂️ Dataset

The project uses the AI4I 2020 Predictive Maintenance Dataset, a public dataset designed for predictive maintenance research.

The dataset contains 10,000 records describing machine operating conditions and failure outcomes.

Dataset characteristic| Description
Total records| 10,000
Target tasks| Failure prediction and failure-type classification
Data type| Structured industrial data
Main inputs| Machine type, temperature, rotational speed, torque, and tool wear

Input Features

Feature| Description
"Type"| Machine product type
"Air temperature [K]"| Ambient air temperature in Kelvin
"Process temperature [K]"| Machine process temperature in Kelvin
"Rotational speed [rpm]"| Rotational speed in revolutions per minute
"Torque [Nm]"| Operating torque in Newton-metres
"Tool wear [min]"| Tool wear time in minutes

These features provide information about machine operating conditions that may be associated with failure.

🧠 Machine Learning Workflow

The project follows a structured machine learning workflow:

1. Data Understanding — inspect the dataset, feature distributions, and target variables.
2. Exploratory Data Analysis (EDA) — analyze patterns, relationships, and failure distributions.
3. Data Preprocessing — prepare features and targets for modeling.
4. Class Imbalance Handling — apply "SMOTENC" to the training data to address class imbalance.
5. Model Training — develop models for binary failure prediction and failure-type classification.
6. Model Evaluation — evaluate predictions using multiple classification metrics.
7. Risk Interpretation — translate predicted failure probabilities into risk categories.
8. Visualization and Reporting — present findings through Python visualizations and Power BI dashboards.

🤖 Machine Learning Tasks

Model 1 — Binary Failure Prediction

The first model predicts whether a machine is expected to experience a failure.

Objective: Identify potentially at-risk machines from their operating conditions.

The task is challenging because failure cases represent only a small proportion of the dataset. Therefore, accuracy alone is insufficient to evaluate the model.

Model 2 — Failure-Type Classification

The second model classifies the potential failure into one of the supported categories:

- "HDF"
- "OSF"
- "Other"
- "PWF"
- "TWF"

Objective: Provide more detailed information about the predicted failure category.

The performance of individual categories is important because some failure types occur much less frequently than others.

📊 Model Evaluation

The following metrics summarize the reported model evaluation results.

Binary Failure Prediction

Metric| Reported result
Accuracy| 95%
Precision| 36%
Recall| 65%
F1-score| 0.46
ROC-AUC| 0.962
PR-AUC| 0.597

Interpretation

The model demonstrates strong ranking ability according to its ROC-AUC score. Its reported recall indicates that it identifies a meaningful proportion of failure cases, while its precision shows that false alarms remain an important challenge.

This trade-off matters in predictive maintenance: missing a real failure and generating an unnecessary maintenance alert can have different operational costs.

Failure-Type Classification

Metric| Reported result
Accuracy| 88%
Macro Precision| 0.80
Macro Recall| 0.79
Macro F1-score| 0.79
Weighted F1-score| 0.88

Interpretation

The results indicate useful classification performance across the evaluated failure categories. Macro-averaged metrics are included to give each category equal weight, rather than allowing the most common classes to dominate the overall score.

Performance for rare categories should be interpreted cautiously because the test set contains relatively few examples of some failure types.

«Evaluation note: These figures represent the reported results from the project notebook. The dataset is imbalanced, and the evaluation contains limitations associated with rare failure categories and threshold selection. The results should therefore be treated as experimental findings, not as proof of production readiness.»

📈 Power BI Dashboards

<div align="center">Dashboard 1

<img src="https://raw.githubusercontent.com/esmailemrany/machine-failure-analysis/main/PowerBi1.png" width="90%" alt="Power BI Dashboard 1" />Dashboard 2

<img src="https://raw.githubusercontent.com/esmailemrany/machine-failure-analysis/main/PowerBi2.png" width="90%" alt="Power BI Dashboard 2" />Dashboard 3

<img src="https://raw.githubusercontent.com/esmailemrany/machine-failure-analysis/main/PowerBi3.png" width="90%" alt="Power BI Dashboard 3" /></div>---

🐍 Python Analysis and Visualizations

<div align="center">Python Visualization 1

<img src="https://raw.githubusercontent.com/esmailemrany/machine-failure-analysis/main/Python1.png" width="90%" alt="Python Visualization 1" />Python Visualization 2

<img src="https://raw.githubusercontent.com/esmailemrany/machine-failure-analysis/main/Python2.png" width="90%" alt="Python Visualization 2" />Python Visualization 3

<img src="https://raw.githubusercontent.com/esmailemrany/machine-failure-analysis/main/Python3.png" width="90%" alt="Python Visualization 3" /></div>
🛠️ Technologies Used

- Python — data analysis and model development.
- Pandas — data manipulation.
- NumPy — numerical operations.
- Scikit-learn — machine learning and model evaluation.
- Imbalanced-learn — handling class imbalance with "SMOTENC".
- Matplotlib / Seaborn — data visualization.
- Power BI — interactive business intelligence and reporting.
- Jupyter Notebook — experimentation and documentation.
- Joblib — saving and loading model-related artifacts.

📁 Repository Structure

machine-failure-analysis/
│
├── مشروع_التنبؤ_بالاعطال.ipynb
├── README.md
├── requirements.txt
│
├── PowerBi1.png
├── PowerBi2.png
├── PowerBi3.png
│
├── Python1.png
├── Python2.png
├── Python3.png
│
├── model1_type_encoder.pkl
└── model2_type_encoder.pkl

The notebook documents the analysis and modeling workflow. The encoder files support the associated categorical-feature processing.

🚀 Getting Started

1. Clone the Repository

git clone https://github.com/esmailemrany/machine-failure-analysis.git
cd machine-failure-analysis

2. Install Dependencies

pip install -r requirements.txt

3. Open the Notebook

Launch Jupyter Notebook:

jupyter notebook

Open "مشروع_التنبؤ_بالاعطال.ipynb" and follow the notebook cells to explore the data, preprocessing steps, modeling workflow, and evaluation results.

Note: Reproducing the full workflow may require obtaining the dataset and ensuring that any referenced files are available at the paths expected by the notebook.

⚠️ Limitations and Future Improvements

This project is an experimental predictive maintenance solution built using a public dataset. Several improvements would be needed before considering deployment in an industrial environment.

Potential next steps include:

- Evaluating models on independent, unseen data.
- Using cross-validation and more robust evaluation procedures.
- Investigating decision thresholds without tuning them on the final test set.
- Improving precision while maintaining useful failure recall.
- Collecting more examples of rare failure categories.
- Calibrating predicted probabilities before interpreting them as operational risk.
- Testing the approach on real industrial data.
- Building a deployment pipeline with monitoring and model-version tracking.

💡 Key Learnings

This project provided practical experience with:

- End-to-end machine learning workflows.
- Exploratory data analysis on industrial data.
- Class imbalance and its effect on classification.
- Multi-class and binary classification.
- Evaluation beyond accuracy.
- Model interpretation and operational risk considerations.
- Combining machine learning outputs with business intelligence dashboards.
- Communicating technical results through visual reporting.

👨‍💻 Author

Esmail Emrany

Artificial Intelligence & Data Science Student

GitHub: "esmailemrany" (https://github.com/esmailemrany)

---

This project is an educational and portfolio project exploring machine learning techniques for predictive maintenance. It is not a validated industrial safety or maintenance system.
