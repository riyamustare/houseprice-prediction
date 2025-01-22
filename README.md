# House Price Prediction

This is a Flask-based web application that predicts house prices based on user inputs. The application uses a pre-trained regression model and a scaling model to provide predictions. The user can input various features of a house, and the application will return the predicted price.

## Features
- Predict house prices via a web interface.
- Supports API-based predictions through JSON input.
- Simple and user-friendly design.

## Technologies Used
- **Flask**: For creating the web application.
- **Pickle**: For loading the pre-trained regression and scaling models.
- **HTML & CSS**: For creating the front-end interface.
- **NumPy & Pandas**: For data processing.

## Setup Instructions

1. Clone the repository:
    ```bash
    git clone https://github.com/riyamustare/houseprice-prediction.git
    cd houseprice-prediction
    ```

2. Install required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Run the Flask application:
    ```bash
    python app.py
    ```

4. Open your web browser and visit:
    ```
    http://127.0.0.1:5000/
    ```

## How It Works
- **Homepage**: Provides an interface to input features of a house (e.g., CRIM, ZN, RM, etc.).
- **Prediction API**: Accepts JSON input via `/predict_api` endpoint for automated predictions. Example:
    ```json
    {
        "data": {
            "CRIM": 0.2,
            "ZN": 18.0,
            "INDUS": 2.31,
            "CHAS": 0,
            "NOX": 0.538,
            "RM": 6.575,
            "Age": 65.2,
            "DIS": 4.09,
            "RAD": 1,
            "TAX": 296,
            "PTRATIO": 15.3,
            "B": 396.9,
            "LSTAT": 4.98
        }
    }
    ```

## Model Details
- **Regression Model**: A machine learning model trained to predict house prices based on features such as crime rate, residential land zoning, number of rooms, and more.
- **Scaler Model**: Used to normalize input data for consistent predictions.

### API Prediction
Example of using `/predict_api` endpoint:
```bash
curl -X POST http://127.0.0.1:5000/predict_api \
    -H "Content-Type: application/json" \
    -d '{"data": {"CRIM": 0.2, "ZN": 18.0, "INDUS": 2.31, "CHAS": 0, "NOX": 0.538, "RM": 6.575, "Age": 65.2, "DIS": 4.09, "RAD": 1, "TAX": 296, "PTRATIO": 15.3, "B": 396.9, "LSTAT": 4.98}}'
```
