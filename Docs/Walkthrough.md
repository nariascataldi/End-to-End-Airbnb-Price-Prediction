# Airbnb Price Prediction Project Walkthrough

This document provides a detailed walkthrough of the **Airbnb Price Prediction** project, explaining its structure, core components, and how the data flows from raw input to price prediction.

## 1. Project Overview
The goal of this project is to predict the price of Airbnb listings based on various features such as location, property type, room type, and amenities. It uses a machine learning model (CatBoost) trained on historical Airbnb data.

## 2. Directory Structure
The project is organized into modular components to ensure scalability and maintainability:

- **`src/Airbnb/`**: Contains the core logic of the application.
  - **`components/`**: Modular scripts for different stages of the ML pipeline.
    - `Data_ingestion.py`: Handles data loading and splitting (train/test).
    - `Data_transformation.py`: Performs data cleaning, feature engineering, and preprocessing.
    - `Model_trainer.py`: Trains the machine learning model and saves it.
  - **`pipelines/`**: Orchestrates the execution of components.
    - `Training_Pipeline.py`: Runs the full training process.
    - `Prediction_Pipeline.py`: Handles real-time predictions for the web app.
  - **`utils/`**: Helper functions for common tasks like saving/loading objects.
  - **`logger.py` & `exception.py`**: Custom logging and error handling.
- **`Artifacts/`**: Stores the raw data, processed datasets, and serialized model files (`Model.pkl`, `Preprocessor.pkl`).
- **`templates/` & `static/`**: Contains the HTML templates and CSS/JS for the Flask web application.
- **`app.py`**: The entry point for the Flask web server.
- **`setup.py`**: Configuration for installing the project as a package.

## 3. Core Workflow

### A. Data Ingestion
The process begins in `Data_ingestion.py`, where the raw dataset is loaded from a source (e.g., CSV file) and split into training and testing sets. These are saved in the `Artifacts/` folder.

### B. Data Transformation
In `Data_transformation.py`, the data undergoes several preprocessing steps:
- Handling missing values.
- Converting categorical features into numerical formats.
- Scaling numerical features.
- Creating a `Preprocessor.pkl` object that encapsulates these steps.

### C. Model Training
The `Model_trainer.py` script takes the transformed data and trains a **CatBoost Regressor** (or other models depending on configuration). The best-performing model is saved as `Model.pkl` in the `Artifacts/` folder.

### D. Prediction (Web App)
When a user submits the form on the web interface:
1. `app.py` receives the form data.
2. `Prediction_Pipeline.py` converts the input into a dataframe.
3. The `Preprocessor.pkl` is loaded to transform the input data.
4. The `Model.pkl` is loaded to predict the price.
5. The result is displayed back to the user in the browser.

## 4. How to Run
To run the application locally:
1. Install dependencies: `pip install -r requirements.txt`
2. Run the Flask app: `python app.py`
3. Access the app at `http://localhost:8080` in your browser.

## 5. Technology Stack
- **Language**: Python
- **Framework**: Flask
- **ML Libraries**: Scikit-Learn, CatBoost, XGBoost, Pandas, Numpy
- **Data Versioning**: DVC (Data Version Control)
- **Containerization**: Docker
