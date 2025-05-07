# new-york-taxi-fare

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

New York taxi fare prediction based on location and time.

## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         new-york-taxi-fare and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── new-york-taxi-fare   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes new-york-taxi-fare a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

## Notebook Overview

The project includes a Jupyter notebook, [`new-york-taxi-fare.ipynb`](notebooks/new-york-taxi-fare.ipynb), which performs the following tasks:

1. **Data Loading and Cleaning**:
   - Loads a subset of the dataset for analysis.
   - Cleans the data by removing invalid or outlier records (e.g., negative fares, unrealistic coordinates).

2. **Exploratory Data Analysis (EDA)**:
   - Analyzes the distribution of fares and other features.
   - Visualizes pickup and dropoff locations on maps.
   - Examines correlations between fare amount and features like distance, time, and passenger count.

3. **Feature Engineering**:
   - Calculates the Haversine distance between pickup and dropoff points.
   - Extracts temporal features such as pickup hour and year.

4. **Modeling**:
   - Implements a baseline linear regression model using features like distance, pickup hour, and year.
   - Evaluates the model using metrics such as RMSE and MAPE.

5. **Findings**:
   - Strong correlation between fare amount and distance.
   - Inflation effects observed over the years.
   - Limited correlation between fare and passenger count.

## Key Findings

- **Distance**: The most significant predictor of fare amount.
- **Inflation**: Fares have increased over the years, likely due to inflation.
- **Time**: Pickup hour shows some correlation with fare amount.
- **Passenger Count**: No significant impact on fare amount.

## Future Work

- Improve data cleaning by addressing false data points (e.g., trips in water).
- Engineer additional features for better model performance.
- Experiment with advanced machine learning models for prediction.
- Enhance visualizations for deeper insights.