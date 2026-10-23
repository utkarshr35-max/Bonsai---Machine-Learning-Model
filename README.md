# Feature Delivery Predictor

A machine learning project that predicts whether a software feature will be delivered on time using historical feature delivery data. The project uses a **Random Forest Classifier** to learn patterns from feature attributes and classify delivery outcomes.

## Project Overview

Accurately predicting feature delivery timelines can help software teams improve planning, identify potential delays, and make better release decisions.

This project explores historical delivery data, preprocesses categorical features, trains a machine learning model, and evaluates its predictions against actual delivery outcomes.

## Features

- Exploratory Data Analysis (EDA) of historical feature data
- Categorical feature encoding using pandas
- Binary classification of delivery outcomes
- Random Forest model training using scikit-learn
- Prediction of delivery status on test data
- Model evaluation using accuracy score

## Technologies Used

- **Python**
- **Pandas** — data manipulation and preprocessing
- **Scikit-learn** — machine learning and model evaluation
- **Jupyter Notebook** — experimentation and analysis
- **C++** — additional source file included in the project

## Project Structure

```text
featurePrediction1/
├── featureDeliveryPredictor.ipynb  # ML workflow
├── Train.csv                       # Training dataset
├── Train.xlsx                      # Excel version of the data
├── Test (1).cpp                    # C++ source file
├── convertXlsToCsv.txt             # Conversion notes
└── README.md                       # Project documentation
```

## How It Works

### 1. Data Loading

The project loads historical feature data from `Train.csv` into a pandas DataFrame.

### 2. Data Exploration

The notebook examines the dataset's dimensions, column data types, and sample records to understand the available information.

### 3. Feature Engineering

Categorical attributes are converted into numerical representations, including:

- QA author
- PO author
- Feature type
- FE/AEP
- Component information

The target variable is created from the `Status` column:

- `1` — Feature met the delivery deadline
- `0` — Feature did not meet the delivery deadline

### 4. Training and Testing

The dataset is divided into training and testing subsets based on the `SerialNumber` column.

### 5. Model Training

A Random Forest Classifier is trained using selected feature attributes.

The model configuration includes:

- Number of estimators: `100`
- Minimum samples required to split a node: `7`
- Random state: `1`

### 6. Prediction and Evaluation

The trained model predicts delivery outcomes for the test dataset. The predictions are compared with the actual target values using classification accuracy.

## Getting Started

### Prerequisites

Install Python 3 and the required libraries.

```bash
pip install pandas scikit-learn jupyter openpyxl
```

### Run the Project

1. Clone this repository:

   ```bash
   git clone <YOUR_GITHUB_REPOSITORY_URL>
   ```

2. Navigate to the project directory:

   ```bash
   cd featurePrediction1
   ```

3. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

4. Open `featureDeliveryPredictor.ipynb`.

5. Execute the notebook cells in order.

**Note:** Keep `Train.csv` in the same directory as the notebook so the dataset can be loaded correctly.

## Evaluation Metric

The model is evaluated using classification accuracy:

\[
\text{Accuracy} =
\frac{\text{Correct Predictions}}{\text{Total Predictions}}
\]

The actual accuracy depends on the dataset and the model's predictions.

## Future Improvements

- Use a dedicated, reproducible train-test split.
- Apply cross-validation and hyperparameter tuning.
- Evaluate precision, recall, F1-score, and confusion matrix.
- Improve categorical encoding and handle previously unseen categories.
- Investigate additional features that may influence delivery timelines.
- Build a simple interface for predicting delivery outcomes for new features.

## Disclaimer

This project is intended for learning and experimentation with machine learning. Predictions are estimates based on historical data and should not be treated as guaranteed delivery outcomes.

## Author

Developed as a machine learning project focused on predicting software feature delivery performance.
