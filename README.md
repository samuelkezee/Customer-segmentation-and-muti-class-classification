# Customer Segmentation and Classification Project

This project is an end-to-end machine learning solution for customer segmentation and classification, built with a focus on MLOps principles. The system takes raw customer data, segments customers into meaningful groups, and then classifies new customers into those segments.

## Directory Structure

```
├── data
│   ├── raw
│   └── processed
├── notebooks
├── src
│   ├── pipelines
│   ├── stages
│   └── utils
├── tests
├── README.md
├── main.py
└── pyproject.toml
```

## MLOps Pipeline Stages

The project is structured as a modular pipeline with the following stages:

### 1. Manual Data Ingestion

The pipeline begins by reading a new dataset (e.g., a CSV file) that has been manually placed in the `data/raw` directory.

### 2. Exploratory Data Analysis (EDA)

An initial analysis is performed to understand the data's characteristics, including distributions, correlations, data quality, missing values, and outliers. This is typically done in a Jupyter notebook found in the `notebooks` directory.

### 3. Data Transformation Pipeline

A dedicated pipeline in `src/pipelines` handles all data preprocessing. This includes:
- Feature engineering
- Scaling numerical features
- Encoding categorical variables
- Dimensionality reduction (e.g., PCA)

### 4. Unsupervised Clustering & Evaluation

The core analytical phase where multiple clustering algorithms are implemented and compared on the processed data. This can include:
- K-Means
- DBSCAN
- Gaussian Mixture Models
- Hierarchical Clustering

Models are evaluated using metrics like the Silhouette Score and Davies-Bouldin Index to assess cluster quality.

### 5. Best Model Selection & Label Creation

The best-performing clustering model is selected based on evaluation metrics. The cluster labels assigned by this model are then used as the target variable for the next stage.

### 6. Supervised Classification Model

The problem shifts to supervised learning. A multi-class classification model (e.g., Random Forest, XGBoost) is trained using the original features and the newly created cluster labels as the target.

### 7. Deployment & Inference

The final output is a trained classification pipeline. When new customer data is provided, the pipeline preprocesses it and predicts the customer's segment.

## Getting Started

### Prerequisites

- Python 3.11 or higher
- The dependencies listed in `pyproject.toml`

### Installation

1. Clone the repository.
2. Install the required dependencies: `pip install -r requirements.txt` (Note: you will need to create a requirements.txt from pyproject.toml)

## Usage

To run the main application, execute the following command:

```bash
python main.py
```
