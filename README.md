# Delivery Time Prediction API

A machine learning project that predicts food delivery time based on delivery distance, preparation time, traffic level, and weather conditions. The trained Linear Regression model is deployed using **FastAPI**, allowing users to make predictions through REST API endpoints.

## Features

* **Delivery Time Prediction:** Predicts estimated delivery time using a trained machine learning model.
* **Input Validation:** Validates order details using Pydantic and rejects invalid inputs.
* **Health Check:** Provides an endpoint to check whether the API and model are running.
* **Model Information:** Returns the model's feature names, model type, and version.
* **Distance Validation:** Rejects delivery orders beyond the maximum allowed distance of 25 km.
* **Interactive API Documentation:** Allows users to test endpoints directly through Swagger UI.

## Technologies Used

* Python
* Pandas and NumPy
* Scikit-learn
* FastAPI
* Pydantic
* Uvicorn
* Joblib

## Input Features

| Feature         | Description                                      |
| --------------- | ------------------------------------------------ |
| `distance_km`   | Delivery distance in kilometres                  |
| `prep_time_min` | Food preparation time in minutes                 |
| `traffic_level` | Traffic level from 1 to 3                        |
| `rain`          | Weather indicator: 0 for dry weather, 1 for rain |

## API Endpoints

| Method | Endpoint      | Description                 |
| ------ | ------------- | --------------------------- |
| GET    | `/health`     | Checks API and model status |
| POST   | `/predict`    | Predicts delivery time      |
| GET    | `/model-info` | Returns model information   |

## Getting Started

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd delivery-time-repo
```

### 2. Install dependencies

```bash
pip install numpy pandas scikit-learn fastapi uvicorn joblib httpx2
```

### 3. Run the API

Navigate to the directory containing `app.py` and run:

```bash
python -m uvicorn app:app --reload --port 8000
```

### 4. Open API documentation

Visit:

http://127.0.0.1:8000/docs

Use the interactive Swagger interface to test the available endpoints.

## Example Prediction Request

```json
{
  "distance_km": 5,
  "prep_time_min": 20,
  "traffic_level": 2,
  "rain": 0
}
```

The API returns the predicted delivery time and model version.

## Learning Outcomes

* Training and saving a machine learning model.
* Building REST APIs using FastAPI.
* Validating input data using Pydantic.
* Testing API endpoints and handling invalid requests.
* Documenting APIs using OpenAPI and Swagger UI.
* Applying input constraints to enforce business rules.

## Project Objective

The objective is to demonstrate how a trained machine learning model can be deployed as an API, validated through automated tests, and made accessible through an interactive documentation interface.
