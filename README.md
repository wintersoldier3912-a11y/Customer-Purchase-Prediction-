# Customer Purchase Prediction Project

This project predicts whether a customer will make a purchase based on their profile and behavior.

## Project Structure
- `notebook.ipynb`: End-to-end data science workflow.
- `src/`: Modular Python package.
  - `data.py`: Ingestion & splitting.
  - `preprocess.py`: Preprocessing & Feature Engineering.
  - `models.py`: Training & Tuning.
  - `evaluate.py`: Metrics & SHAP explanations.
  - `predict_api.py`: FastAPI implementation.

## How to Run
1. **Install dependencies**: `pip install -r requirements.txt`
2. **Train model**: Open `notebook.ipynb` and run all cells. This generates `model.joblib`.
3. **Start the API**: `python src/predict_api.py`

## API Usage Example
Test the API using `curl` with the enhanced feature set:

```bash
curl -X 'POST' \
  'http://localhost:8000/predict' \
  -H 'Content-Type: application/json' \
  -d '{
  "Age": 30,
  "Gender": "Female",
  "AnnualIncome": 75000,
  "SpendingScore": 85,
  "PreviousPurchaseCount": 2,
  "EngagementScore": 9,
  "LastVisitDays": 3,
  "Country": "USA",
  "AveragePurchaseValue": 150.50,
  "DeviceType": "Mobile",
  "MarketingChannel": "Social"
}'
```

## Dataset Schema
- `CustomerID`: Unique ID
- `Age`: Customer age
- `Gender`: Male/Female
- `AnnualIncome`: Annual income in USD
- `SpendingScore`: Normalized score (1-100)
- `PreviousPurchaseCount`: Total past purchases
- `EngagementScore`: (1-10)
- `LastVisitDays`: Days since last visit
- `Country`: Categorical
- `AveragePurchaseValue`: Mean spend per transaction
- `DeviceType`: Mobile, Desktop, or Tablet
- `MarketingChannel`: Social, Email, Search, or Direct
- `purchase`: Target variable (0 or 1)
