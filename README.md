# EIACD-Student-Intervention-System-SL

## Project Overview

This project implements a machine learning pipeline to predict students at risk of academic failure and provide targeted intervention recommendations. Using the UCI Student Performance dataset, the system identifies students who may need additional support to succeed academically, with a specific focus on accurately predicting students who will fail.

## Motivation

Early identification of at-risk students is crucial for providing timely academic support. Traditional methods often rely on reactive approaches after students have already begun to fail. This project takes a proactive approach by using machine learning to predict academic outcomes before failure occurs, allowing educators to implement targeted interventions when they can be most effective.

## Dataset

The analysis uses the UCI Student Performance dataset, which contains information about secondary education students in Portugal, including:

- Demographic information (age, gender, family size)
- Social factors (family relationships, alcohol consumption)
- Academic history (previous failures, study time)
- School-related features (absences, extra educational support)

The target variable is whether a student passes or fails their final exam. For more information about each feature, you can view `student-data-information.txt`.

## Key Features

- **Fail-Focused Prediction**: Optimized specifically to identify students who will fail, prioritizing recall and precision for the fail class
- **Class Imbalance Handling**: Uses SMOTE (Synthetic Minority Over-sampling Technique) to address class imbalance
- **Feature Engineering**: Creates composite features that capture study commitment, alcohol consumption and parent education
- **Model Comparison**: Evaluates multiple classification algorithms with metrics focused on fail prediction
- **Threshold Optimization**: Provides detailed threshold analysis to optimize the trade-off between precision and recall
- **Risk Stratification**: Categorizes students into risk levels (High, Moderate, Low, Very Low) for targeted interventions

## Technical Approach

The project follows a comprehensive machine learning workflow:

1. **Data Exploration and Visualization**
   - Examines feature distributions and relationships
   - Analyzes class imbalance
   - Identifies key predictors of academic failure

2. **Data Preprocessing**
   - Feature engineering to create composite risk indicators
   - Encoding categorical variables
   - Handling class imbalance with SMOTE

3. **Model Development**
   - Implements multiple classification algorithms
   - Uses class weights to prioritize fail prediction
   - Evaluates models using fail-specific metrics (precision, recall, F1)

4. **Hyperparameter Tuning**
   - Optimizes model parameters for fail prediction
   - Performs threshold analysis to balance precision and recall

5. **Intervention System**
   - Identifies students needing intervention
   - Categorizes by risk level
   - Provides tiered intervention recommendations

## Results

The system achieves strong performance in identifying students at risk of failure, with:

- High recall for the fail class, ensuring few at-risk students are missed
- Balanced precision to minimize unnecessary interventions
- Effective risk stratification for resource allocation
- Clear identification of key risk factors

## Key Findings

The analysis identified several strong predictors of academic failure:

1. **Previous failures**
2. **Absences**
3. **Study time**
4. **Parent education level**
5. **Alcohol consumption**
6. **Family relationships**
7. **Higher education aspirations**

## Usage

The project is implemented as a Jupyter notebook that can be run end-to-end. To use:

1. Clone repo and create conda environment:
   ```bash
   # Installation (using conda)
   git clone https://github.com/PedroNJorge/EIACD-Student-Intervention-System-SL
   cd EIACD-Student-Intervention-System-SL
   conda create -f environment.yml -n env
   ```
2. Install ipykernel to able to use kernels inside Jupyter:
   ```bash
   python -m ipykernel install --user --name <kernel_name> --display-name "<display_name>"
   jupyter-notebook eda.ipynb
   ```
3. Inside the Jupyter Notebook, select the kernel with the chosen name.

## Acknowledgments

- UCI Machine Learning Repository for providing the dataset
- Cortez, P., & Silva, A. M. G. (2008). "Using data mining to predict secondary school student performance"

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
