# FastAPI End-to-End Project

This repository contains an end-to-end Machine Learning and Patient Management system built with **FastAPI** for the backend, **Streamlit** for the frontend, and **Scikit-Learn** for machine learning tasks.

## Features

The project is divided into two main components:
1. **Patient Management API (`main.py`)**: A RESTful API built with FastAPI that acts as a simple patient management system with CRUD operations. It stores records in a local `patients.json` file and handles BMI calculations and patient sorting.
2. **Insurance Premium Predictor (`app.py` & `frontend.py`)**: A machine learning application that predicts health insurance premium categories based on various metrics like age group, lifestyle risk, city tier, and occupation. 

## Project Structure

- `main.py`: Patient Management System API endpoints.
- `app.py`: Insurance Premium Prediction API that serves an ML model (`model.pkl`).
- `frontend.py`: Streamlit frontend application that connects to the Prediction API.
- `fastapi_ml_model.ipynb`: Jupyter Notebook used for data exploration and training the ML model using `insurance.csv`.
- `patients.json`: Local JSON database for the Patient Management API.
- `requirements.txt`: Python dependencies required to run the project.

## Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd fastapi-end-to-end
   ```

2. **Create and activate a virtual environment**:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows use: .venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## Running the Application

### 1. Patient Management API
To start the Patient Management System API:
```bash
uvicorn main:app --reload
```
- Access the API at: `http://127.0.0.1:8000`
- Access interactive documentation (Swagger UI): `http://127.0.0.1:8000/docs`

### 2. Insurance Premium Prediction API
To start the ML model server:
```bash
uvicorn app:app --reload --port 8000
```
*(Make sure to train your model and generate `model.pkl` in the Jupyter notebook first if it is not present.)*

### 3. Streamlit Frontend
In a new terminal, while `app.py` is running, launch the frontend:
```bash
streamlit run frontend.py
```
This will open the web interface in your default browser where you can enter a user's details and get real-time predictions for their insurance premium category.

## Tech Stack
- **FastAPI**: Backend web framework
- **Pydantic**: Data validation and serialization
- **Streamlit**: Interactive frontend UI
- **Scikit-Learn & Pandas**: Machine learning and data manipulation
- **Jupyter Notebook**: Model training and fast prototyping
