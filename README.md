# Local AQI Prediction

This project trains a machine learning model to predict air quality index (AQI) from environmental sensor features.

## Project structure

- `data/environmental_data.csv` — AQI dataset
- `src/train.py` — training pipeline
- `models/` — saved trained model artifacts

## Setup

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

## Train the model

```bash
python src/train.py --data data/environmental_data.csv --output models/aqi_model.pkl
```

## Expected dataset schema

The script is built to work with a column such as `AQI` as the target and pollutant/environment fields like:

- `PM2.5`
- `PM10`
- `NO2`
- `SO2`
- `CO`
- `O3`
- `NH3`
- `temperature`
- `humidity`
- `wind_speed`
- `pressure`

It also supports other common names such as `Air_Quality_Index`, `aqi`, `city`, `date`, etc.

## Notes

- The model uses preprocessing for numeric and categorical columns.
- Missing values are handled automatically.
- The trained model is saved in `models/aqi_model.pkl`.
