## Ateliers MLOps - IMT A -- Intersemestre 2025

L'idée des ateliers est de commencer à utiliser certains outils qui peuvent être d'utilité pour faire du MLOps.


   --------ENGLISH VERSION-----------
# MLOps for Clinical Trials — IMT Atlantique Workshop Project

This project was developed as part of the MLOps workshops held at IMT Atlantique during the Intersemester 2025. The goal is to explore the integration of modern MLOps tools for managing machine learning workflows.

-------------------------
##  Project Objectives

The project aims to design a complete MLOps pipeline for predicting drug approval outcomes based on real-world clinical trials data.  
The pipeline ensures:

- Reproducibility of ML experiments (via MLflow)
- Workflow orchestration (via Apache Airflow)
- Containerization and environment consistency (via Docker)
- Automation and scalability of training & deployment

---

##  Tech Stack

- **Python**: Data manipulation, preprocessing, modeling
- **Jupyter Notebooks**: Prototyping & experimentation
- **MLflow**: Experiment tracking, model management
- **Apache Airflow**: DAG-based workflow orchestration
- **Docker**: Containerized environment
- **Miniconda**: Dependency and environment management
- **Git & GitHub**: Version control and collaboration

## Porject Structure 
mlops-project-main/
│
├── airflow/                    # Airflow DAGs, plugins, logs, and configuration
│   ├── dags/                  # DAG files for orchestration
│   ├── logs/                  # Airflow execution logs (excluded in .gitignore)
│   ├── plugins/               # Custom Airflow plugins
│   └── config/                # Airflow configuration files
│
├── notebooks/                 # Jupyter Notebooks for experimentation and training
│   ├── data/                 # Raw data used for modeling
│   ├── cert/                 # Certificate-related files
│   └── *.ipynb               # Notebooks including preprocessing and ML pipelines
│
├── docker-compose.yml         # Docker setup for MLflow, Airflow, etc.
├── .gitignore                 # Ignore unnecessary files (envs, logs, etc.)
├── LICENSE                    # Project license
├── README.md                  # Project documentation
└── TPS/                       # Additional resources

## installation and setups 

# Clone the repository
git clone https://github.com/AchrafEssaleh/mlops-project-main.git
cd mlops-project-main

# Install Miniconda (if not already installed)
bash Miniconda3-latest-MacOSX-arm64.sh

# Restart your terminal, then create and activate the conda environment
conda create --name mlops_env python=3.11
conda activate mlops_env

# Install required Python packages
pip install -r notebooks/requirements.txt

# Launch all services using Docker Compose
docker-compose up --build

## ML Pipeline Overview

1. Data Ingestion:
   - Load raw clinical trial data from the TDC dataset

2. Data Preprocessing:
   - Handle missing values, encoding, and normalization
   - Feature engineering based on domain knowledge

3. Model Training:
   - Train a Random Forest Classifier
   - Evaluate using cross-validation and metrics

4. Experiment Tracking:
   - Use MLflow to log parameters, metrics, and models

5. Workflow Orchestration:
   - Schedule and manage pipeline with Apache Airflow DAGs

6. Deployment & Reproducibility:
   - Use Docker & MLflow for reproducible and containerized runs

## Experiment Tracking with MLflow

The ML pipeline uses MLflow to track and log the following:

- Model parameters (e.g., number of estimators, depth)
- Evaluation metrics (e.g., accuracy, precision, recall)
- Model artifacts (e.g., trained models, plots)
- Training runtime and environment metadata

To visualize experiments and runs locally, launch the MLflow tracking UI:

```bash
mlflow ui
```

Then open your browser and navigate to:
http://localhost:5000


**Team Contributors**:
## Authors & Contributions

This project was developed as part of the MLOps workshops at **IMT Atlantique** in January 2025, by a team of six members.

The workload was collaboratively split, with particular attention dedicated to:

- Designing and implementing core data pipelines  
- Developing machine learning models and tuning hyperparameters  
- Integrating MLflow for robust experiment tracking and reproducibility  
- Structuring the project architecture and documentation  
- Supporting the setup of containerized environments and workflow orchestration  

Special care was taken to ensure that the foundational components — data processing, modeling logic, and MLOps integration — were well designed and extensible.










