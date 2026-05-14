# Heart Attack Detection Project

Machine learning web application that predicts heart disease risk from clinical patient data.

## Features

- Predicts heart disease likelihood using a trained Random Forest classifier (~78.7% accuracy)
- Compares Decision Tree and Random Forest models during the research/training phase
- Accepts 13 clinical input features: age, sex, chest pain type, resting blood pressure, cholesterol, fasting blood sugar, resting ECG results, maximum heart rate, exercise-induced angina, ST depression (oldpeak), slope, number of major vessels, and thalassemia
- Returns a plain-English prediction indicating whether the patient is likely or not likely to have heart disease
- Flask web interface with an HTML form for entering patient values
- Pre-trained model serialized as `model.pkl` — no retraining required to run the app
- Deployable to Heroku via the included `Procfile` and `gunicorn` setup

## Tech Stack

- Python 3
- scikit-learn (RandomForestClassifier, DecisionTreeClassifier)
- pandas, NumPy
- Flask 1.1
- Gunicorn
- Jinja2 (HTML templating)
- Jupyter Notebook (model training and exploration)

## Getting Started

### Prerequisites

- Python 3.7 or higher
- pip

### Installation / Setup

1. Clone the repository and navigate into the project folder.

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Flask development server:
   ```bash
   python app.py
   ```

4. Open `http://127.0.0.1:5000` in your browser, fill in the patient details, and click **Predict**.

To retrain the model, open `heart_disease_git.ipynb` in Jupyter Notebook and run all cells. The notebook reads `heart.csv`, trains both a Decision Tree and a Random Forest, and saves the Random Forest model to `heart_disease.pkl`.

## Project Structure

```
heart-attack-detection-project/
├── app.py                  # Flask application — routes and prediction logic
├── model.pkl               # Serialized Random Forest model (production)
├── heart.csv               # Cleveland Heart Disease dataset (303 records, 14 columns)
├── heart_disease_git.ipynb # Jupyter Notebook — EDA, model training, evaluation
├── requirements.txt        # Python dependencies
├── Procfile                # Heroku process file
└── templates/
    └── index.html          # Input form and results page
```

## License

MIT
