🏠 California Housing Price Prediction

Machine Learning pipeline using Scikit-Learn to predict median_house_value from housing data.

📌 Features

Stratified train-test split

Data preprocessing pipeline

RandomForestRegressor model

Model + Pipeline saved using joblib

Inference on new input data

## 📂 Project Structure

```text
.
├── housing2.csv      # Training dataset
├── input.csv         # New data for prediction
├── output.csv        # Predictions saved here
├── model.pkl         # Saved trained model
├── pipeline.pkl      # Saved preprocessing pipeline
├── main.py           # Main script
└── README.md         # Project documentation
```


⚙️ How It Works
1️⃣ Training Phase

(Runs only if model.pkl does NOT exist)

Loads dataset from housing2.csv

Creates income categories using median_income

Performs Stratified Shuffle Split

Separates features and labels

Builds preprocessing pipeline

Trains RandomForestRegressor

Saves:

model.pkl

pipeline.pkl

2️⃣ Inference Phase

(Runs if model.pkl exists)

Loads saved model and pipeline

Reads new data from input.csv

Transforms input using pipeline

Generates predictions

Saves results to output.csv

## 🧠 Machine Learning Details
```text
Model Used
RandomForestRegressor

Preprocessing Pipeline
Feature Type	Processing
Numerical	Median Imputation + StandardScaler
Categorical	OneHotEncoder (handle_unknown="ignore")
```

📦 Requirements

Install dependencies:

pip install pandas numpy scikit-learn joblib

▶️ How To Run
🔹 Step 1: Training

Make sure housing2.csv exists.

python main.py


This creates:

model.pkl
pipeline.pkl

🔹 Step 2: Prediction

Create input.csv (same columns except target)

Run:

python main.py


Predictions will be saved to:

output.csv

## 🔁 Pipeline Flow
```text
Raw Data
   ↓
ColumnTransformer
   ├── Numerical Pipeline
   │     ├── Median Imputer
   │     └── StandardScaler
   │
   └── Categorical Pipeline
         └── OneHotEncoder
   ↓
RandomForestRegressor
   ↓
Prediction

```

## 🚀 Future Improvements
```text
Hyperparameter tuning (GridSearchCV)
Add evaluation metrics (RMSE, MAE)
Add logging system
Convert to REST API (Flask / FastAPI)
Docker support
```
👨‍💻 Author
Prathmesh Nirmal