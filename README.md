# Sentiment Analysis Pipeline

## Project Description
This project trains a simple sentiment classifier using a TF-IDF + Logistic Regression pipeline.
It predicts whether a text is positive (1) or negative (0).

## Project Structure
- `src/` — training and prediction scripts
- `data/` — input dataset (CSV)
- `models/` — saved trained model (generated after training)

## Setup

### Option 1: Python venv
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt

### Option 2: Conda
conda create -n sentiment-env python=3.11 -y
conda activate sentiment-env
pip install -r requirements.txt

## Train
python src/train.py --data data/train.csv --out models/sentiment.joblib
**Notes**
- The CSV must contain the columns: `text` and `label`
- Labels are expected to be: `1` (positive) and `0` (negative)


## Predict
Run the predictions in the command line. 
Use any sentence you like.
python src/predict.py "I absolutely loved it" "That was awful"

# Output format: label  probability  text
# Example:
# 1    0.982    I absolutely loved it
# 0    0.015    That was awful
