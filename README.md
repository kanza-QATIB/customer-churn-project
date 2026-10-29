# Customer Churn Analysis and Prediction

## Project Overview

This project analyzes customer data from a fictional telecommunications company to better understand customer churn.

The project covers several stages of a data project:

- loading and inspecting the data;
- checking data quality and preparing the dataset;
- analyzing trends with statistics and visualizations;
- training a machine learning model to estimate churn risk;
- progressively building a data pipeline with data engineering tools.

This project is part of my learning journey in data science and data engineering.

> **Project status:** In progress. Results and tools will be added to this README as the project develops.

## Problem Statement

A company wants to better understand which customer profiles are associated with a higher risk of cancellation.

The question explored in this project is:

> Can a customer’s characteristics and subscription details be used to estimate whether they may leave the company?

The model will produce an estimate based on the available data. This estimate is not certain, and it does not prove that any particular feature causes a customer to leave.

## Dataset Source

This project uses the **IBM Telco Customer Churn** dataset, which is publicly available in IBM’s GitHub repository:

- [IBM dataset repository](https://github.com/IBM/telco-customer-churn-on-icp4d)
- [CSV file](https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv)

The dataset describes fictional customers of a telecommunications company. Each row represents one customer. The columns contain information about the customer’s account, services, and subscription. The `Churn` column indicates whether the customer left (`Yes`) or stayed (`No`).

The data is used for learning and demonstration purposes. It may not represent the customers of a real company.

## Planned Tools

| Tool | Purpose |
|---|---|
| Python | Loading, preparing, and analyzing data |
| Google Colab | Running notebooks in a browser |
| pandas | Data manipulation |
| Matplotlib and Seaborn | Data visualization |
| scikit-learn | Data preparation and machine learning models |
| PostgreSQL | Storing data in a relational database |
| SQL | Querying and transforming data |
| dbt | Organizing SQL transformations and data quality tests |
| Airflow | Orchestrating pipeline tasks |
| GitHub | Version control and project presentation |

Some tools will be added in later stages. Their inclusion here describes the project’s planned direction; it does not necessarily mean they have already been implemented.

## Planned Repository Structure

```text
customer-churn-project/
├── notebooks/
│   ├── 01_exploration_churn.ipynb
│   └── 02_machine_learning_churn.ipynb
├── data/
│   └── README.md
├── scripts/
├── sql/
├── README.md
└── .gitignore
```

- `notebooks/` contains the data exploration and modeling notebooks.
- `data/` is reserved for data files. The CSV can be downloaded from the source listed above.
- `scripts/` will contain reusable Python scripts.
- `sql/` will contain SQL queries and transformations.
- `README.md` describes the project and provides instructions.

## Notebooks

### `01_exploration_churn.ipynb`

This notebook is used to:

- load the CSV file with pandas;
- inspect the dataset’s size and columns;
- check data types and missing values;
- examine the distribution of customers who left and stayed;
- create charts to explore trends;
- document initial observations.

### `02_machine_learning_churn.ipynb`

This notebook will be used to:

- define the target variable (`Churn`);
- split the data into training and test sets;
- prepare numerical and categorical columns;
- train an initial classification model;
- evaluate the model using several metrics;
- explain the limitations of the results.

The notebooks will be updated as each stage is completed.

## Opening the Notebooks in Google Colab

1. Open the project’s GitHub repository.
2. Click the notebook you want to view.
3. Click **Open in Colab**, if the button is available.

You can also open a notebook in Colab and select **File → Save a copy in GitHub** to publish a copy to your repository.

To run the notebooks, load the data from IBM’s public link in a Python cell:

```python
import pandas as pd

url = "https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv"
df = pd.read_csv(url)

df.head()
```

## Project Steps

### 1. Load and Explore the Data

- Download or read the CSV from IBM’s source.
- Inspect the dataset’s dimensions, columns, data types, and first rows.
- Understand the meaning of the key variables.

### 2. Check Data Quality

- Count missing values.
- Look for duplicate rows.
- Check data types.
- Examine unusual values before deciding how to handle them.

### 3. Exploratory Data Analysis

- Examine the distribution of `Churn`.
- Compare churn across contract types, services, and customer tenure.
- Create clear visualizations.
- Write descriptive observations.

### 4. Data Preparation and Machine Learning

- Prepare numerical and categorical features.
- Split the data into training and test sets.
- Build a baseline model.
- Evaluate its results and explain its errors.
- Optionally compare multiple models.

### 5. Data Engineering

- Load the raw data into PostgreSQL.
- Create SQL transformations.
- Organize tables into stages, such as raw data, prepared data, and an analysis table.
- Add data quality tests with dbt.
- Automate the pipeline with Airflow once the individual steps work separately.

### 6. Presentation

- Summarize the results in a dashboard or application.
- Add screenshots and a pipeline diagram.
- Document how to run the project and describe its limitations.

## Planned Evaluation Metrics

The model’s performance will be evaluated using several metrics:

- **Precision:** Among customers flagged as likely to leave, what proportion actually left?
- **Recall:** Among customers who left, what proportion did the model identify?
- **F1-score:** A combined measure of precision and recall.
- **Confusion matrix:** A breakdown of correct predictions and errors.
- **Accuracy:** The overall proportion of correct predictions. This should be interpreted carefully if the classes are imbalanced.

Metric values and model results will be added here after training and evaluation.

## Limitations

- The data describes a fictional company and may not reflect the real-world operations of a telecommunications provider.
- Observed trends are associations and do not demonstrate cause and effect.
- Model performance depends on the quality and representativeness of the data.
- A churn prediction can be wrong and should not be treated as certain.
- The project data alone cannot determine which customer retention action would be effective.

## Setup and Usage

The initial notebooks are designed to run in Google Colab. No local Python environment is required for this first stage.

Instructions for setting up PostgreSQL, dbt, Airflow, and Docker will be added when these components are integrated into the project.

## Author

**Kanza Qatib**  
Master’s student in Data Science and Systems Security, interested in data science, machine learning, and data engineering.

## Acknowledgments

Thanks to IBM for making this sample dataset available for learning and demonstration purposes.
