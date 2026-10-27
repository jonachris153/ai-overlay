# AI-Powered Semiconductor Overlay Error Prediction and Optimization

An AI-driven platform designed to predict semiconductor wafer overlay errors using machine learning, automate model training, and visualize prediction results through an interactive web dashboard.

## Project Overview

In semiconductor manufacturing, overlay accuracy is essential for aligning successive lithography layers on a wafer. Even small alignment errors can affect device performance, manufacturing yield, and production costs.

This project aims to develop an intelligent platform that analyzes semiconductor process parameters and historical overlay measurements to predict overlay errors, support process analysis, and assist manufacturing engineers in making data-driven decisions.

The platform combines a web-based interface with an AI-driven prediction pipeline for dataset management, model training, evaluation, prediction, and visualization.

## Objectives

- Predict semiconductor overlay errors in the X and Y directions.
- Automate dataset preprocessing and machine learning model training.
- Compare model performance using standard evaluation metrics.
- Select the best-performing model based on validation results.
- Provide an interactive dashboard for predictions and analytics.
- Maintain prediction history and model performance information.
- Support process optimization and potential improvements in wafer yield.

## Key Features

- **Dataset Upload:** Upload overlay measurement and process parameter datasets.
- **Data Preprocessing:** Handle missing values, outliers, categorical features, and feature scaling as appropriate.
- **Automated Model Training:** Train and compare supported machine learning models.
- **Model Evaluation:** Evaluate models using MAE, RMSE, and R², with MAPE where appropriate.
- **Overlay Prediction:** Predict overlay error values using new process parameters.
- **Interactive Dashboard:** Display predictions, performance metrics, and analytical visualizations.
- **Model Management:** Save trained models and track model versions.
- **Prediction History:** Maintain records of previous predictions and results.
- **Process Decision Support:** Help identify potential overlay issues for further engineering investigation.

## System Architecture

The platform follows a modular architecture:

1. **Data Acquisition** – Collect overlay measurements, wafer information, and relevant process parameters.
2. **Data Ingestion** – Accept datasets through file uploads or supported data sources.
3. **Data Preprocessing** – Clean and transform data into a suitable format for training.
4. **AI Model Training** – Train supported machine learning algorithms.
5. **Model Evaluation and Selection** – Compare model performance and select the best model using validation metrics.
6. **Model Repository** – Store trained models and associated metadata.
7. **Prediction Engine** – Generate overlay predictions for new inputs.
8. **Decision Support** – Present potential issues and insights for engineering review.
9. **Visualization Dashboard** – Display predictions, model metrics, and historical trends.
10. **Feedback and Improvement** – Use subsequently measured overlay results to evaluate and improve future predictions.

## Machine Learning Approach

The platform can support the following models, depending on implementation:

- Random Forest
- XGBoost
- LightGBM
- CatBoost
- Neural Networks (optional)

The model training pipeline preprocesses the available data, trains candidate models, evaluates their performance, and selects a suitable model based on validation results.

The prediction target may include overlay displacement in the X and Y directions, depending on the dataset and trained model.

## Evaluation Metrics

| Metric | Purpose |
|---|---|
| MAE | Measures the average absolute prediction error. |
| RMSE | Penalizes larger prediction errors more heavily. |
| R² Score | Measures how well the model explains variation in the target values. |
| MAPE | Measures percentage error when the target values make it meaningful to do so. |

Actual performance should be reported using experimental results from the trained models and an appropriate held-out test dataset.

## Technology Stack

**Frontend**
- React.js
- JavaScript
- HTML and CSS

**Backend**
- Python
- Flask REST API

**Data Processing and Machine Learning**
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- LightGBM
- CatBoost

**Model Storage**
- Joblib or Pickle

**Database**
- PostgreSQL or MySQL, depending on the configured implementation

**Visualization**
- Chart.js, Plotly, or another dashboard visualization library, depending on the implementation

## Project Structure

The following is a suggested structure. Update it to match the actual files in your repository.

```text
ai-overlay/
├── frontend/
│   ├── public/
│   ├── src/
│   └── package.json
├── backend/
│   ├── app.py
│   ├── requirements.txt
│   ├── data_preprocessing.py
│   ├── model_training.py
│   ├── prediction.py
│   └── models/
├── datasets/
│   └── README.md
├── docs/
│   └── architecture.png
├── .gitignore
└── README.md
```

## Getting Started

### Prerequisites

Install the following software before running the application:

- Python 3.10 or a compatible version
- Node.js and npm
- Git
- A supported database, if required by the implementation

### 1. Clone the Repository

```bash
git clone https://github.com/jonachris153/ai-overlay.git
cd ai-overlay
```

### 2. Set Up the Backend

Navigate to the backend directory:

```bash
cd backend
```

Create and activate a virtual environment.

**Windows:**

```bash
python -m venv venv
venv\Scripts\activate
```

**Linux/macOS:**

```bash
python -m venv venv
source venv/bin/activate
```

Install the dependencies listed in the project requirements file:

```bash
pip install -r requirements.txt
```

Start the Flask application using the entry point configured in the project. For example:

```bash
python app.py
```

### 3. Set Up the Frontend

Open a separate terminal and navigate to the frontend directory:

```bash
cd frontend
npm install
npm run dev
```

Use the local URL printed by the frontend development server to access the application.

> Note: These commands and directory names are examples. Adjust them to match your actual backend entry point, frontend framework configuration, and project structure.

## Dataset Requirements

The dataset should contain relevant semiconductor process information and measured overlay values.

Possible features include:

- Wafer ID
- Layer ID
- Tool ID
- Exposure and focus settings
- Dose
- Temperature and pressure
- Other available process parameters
- Measured overlay X and Y values

The required columns depend on the model's training configuration. Use appropriately authorized datasets and remove confidential manufacturing information before sharing data publicly.

## Workflow

```text
Dataset Upload
      ↓
Data Validation
      ↓
Preprocessing and Feature Engineering
      ↓
Automated Model Training
      ↓
Model Evaluation and Selection
      ↓
Save the Selected Model
      ↓
Enter New Process Parameters
      ↓
Predict Overlay Error (X, Y)
      ↓
Visualize Results and Historical Trends
      ↓
Review Insights for Process Improvement
```

## Applications

- Semiconductor wafer manufacturing
- Lithography overlay analysis
- Virtual metrology research
- Process monitoring and quality analysis
- Machine learning-assisted manufacturing
- Data-driven semiconductor process optimization

## Future Enhancements

- Integration with live metrology and manufacturing data.
- Advanced drift detection and model retraining.
- Explainable AI and feature importance analysis.
- Model versioning and experiment tracking.
- Deployment using Docker or cloud infrastructure.
- Integration with manufacturing process-control systems.
- Validation of recommendations using measured production results.

## Limitations

The accuracy of overlay prediction depends on the quality, volume, and representativeness of the training data. Predictions and suggested process adjustments must be validated against actual metrology measurements and reviewed by qualified process engineers.

Automated process corrections and closed-loop control require additional integration, safety checks, and validation; they should not be assumed to be implemented merely because prediction capabilities are available.

## Contributors

Add the names of the project contributors and their responsibilities here.

## License

This project can be distributed under the MIT License if the repository owner chooses to apply that license. Add a `LICENSE` file containing the appropriate license text before claiming that the project is MIT-licensed.

## Acknowledgements

This project explores the application of machine learning and web technologies to semiconductor overlay prediction, process analysis, and manufacturing decision support.
