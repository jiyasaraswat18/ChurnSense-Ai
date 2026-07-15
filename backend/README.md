# ChurnSense-Ai Backend

This is the Express backend for the churn prediction system. It receives customer assessment data from the frontend, runs the trained Python machine learning model, and returns the churn probability, risk level, and recommendations.

## What this backend does

The backend is responsible for:
- exposing REST API routes for the frontend
- validating incoming prediction payloads
- calling the Python churn model using joblib
- returning prediction results and recommendation data
- serving health and schema information for the client app

## Tech stack

- Node.js
- Express.js
- Zod for payload validation
- CORS, Helmet, and Morgan for API security and logging
- Python joblib model integration

## Prerequisites

Before running the backend, install the Python dependencies from the project root:

```bash
pip install -r requirements.txt
```

This is important because the backend uses Python packages such as pandas, scikit-learn, joblib, and xgboost.

## Local setup

1. Go to the backend folder:
   ```bash
   cd backend
   ```

2. Install Node dependencies:
   ```bash
   npm install
   ```

3. Create a local environment file:
   ```bash
   copy .env.example .env
   ```
   If there is no .env.example file, create a `.env` file manually with the values you need.

4. Start the backend:
   ```bash
   npm run dev
   ```

The API will run at:
- http://localhost:5000

## Environment variables

Useful variables include:

```env
PORT=5000
FRONTEND_ORIGIN=http://localhost:3000
MODEL_PATH=../Model/churn_model.pkl
PYTHON_BIN=python
ML_TIMEOUT_MS=30000
```

## Available API routes

- `GET /api/health` - checks that the backend is running
- `GET /api/model/schema` - returns the feature schema expected by the model
- `POST /api/predict` - sends customer data and receives churn prediction results

## Example prediction request

```json
{
  "customerName": "Aarav Sharma",
  "inputData": {
    "gender": "Male",
    "maritalStatus": "Married",
    "cityTier": 1,
    "tenure": 18,
    "preferredLoginDevice": "Mobile Phone",
    "preferredPaymentMode": "UPI",
    "hoursSpent": 4,
    "registeredDevices": 3,
    "noOfAddresses": 2,
    "preferredOrderCategory": "Laptop & Accessories",
    "orderCount": 8,
    "couponUsed": 2,
    "cashbackAmount": 75,
    "daysSinceLastOrder": 5,
    "orderAmountHike": 12,
    "warehouseToHome": 15,
    "customerSatisfaction": 4,
    "complaint": false
  }
}
```

## Project structure

- `src/server.js` - Express app entry point
- `src/routes/` - API route handlers
- `src/services/` - model integration and recommendation logic
- `src/schemas/` - request validation schemas
- `scripts/predict.py` - Python script that loads the model and returns predictions

## Notes

The backend depends on the trained model file located in the Model folder. If the model file is missing or the Python environment is not configured correctly, prediction requests will fail.
