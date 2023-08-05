![](https://www.google.com/url?sa=i&url=https%3A%2F%2Ftowardsdatascience.com%2Fpredicting-click-through-rate-for-a-website-7cd2a892d26e&psig=AOvVaw0fRwN5wYiUTZiE7S6NCCnb&ust=1691355484840000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCLCouau0xoADFQAAAAAdAAAAABA3)

Users_active_time_prediction
==============================

Predicting of nutime using the app in hours by different users

Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>


## Overview:

This project aims to develop a predictive model to forecast user online activity, allowing companies to proactively respond to user demands and provide personalized experiences. By accurately predicting user online hours, businesses can efficiently allocate resources and improve overall customer satisfaction.

## Datasets:

**customers.csv**: Contains customer information, including age, gender, and number of kids.
**pings.csv**: Includes user activity data, such as timestamps and online hours.

## Preprocessing Steps:

### 1. Data Cleaning:

Remove duplicates and handle missing values in the datasets.

### 2. Timestamp Conversion:

Convert timestamps to datetime objects for analysis.

### 3. Online Hours Calculation:

Calculate the online hours for each user on each day based on timestamps.

## Baseline Model:

The baseline model predicts online hours for the next day based on the user's online hours on the previous day.

## Machine Learning Model: LightGBM

LightGBM, a gradient boosting framework, is used to build the predictive model. Hyperparameter tuning with Optuna is performed to optimize the model's performance.

## Key Features:

- Age
- Gender
- Number of Kids
- Month, Day of Month, Day of Year, Week of Year, Day of Week
- Is Weekend, Quarter, Month Start/End, Quarter Start/End, Year Start/End
- Rolling Window Mean of Online Hours (over a period of 1 to 21 days)
- Lag Features of Online Hours (previous day's online hours for lags from 1 to 21)

## Model Evaluation:

The model's performance is evaluated using Root Mean Squared Error (RMSE) between the predicted and actual online hours.

## Results and Impact:

The optimized LightGBM model outperforms the baseline, achieving accurate predictions of user online hours. The model's impact on business outcomes includes:

- Improved Customer Satisfaction
- Enhanced User Engagement
- Proactive Resource Allocation
- Data-Driven Decision Making
- Competitive Advantage

## Deployment:

The model can be deployed for real-time predictions, allowing businesses to provide timely and personalized user experiences. LightGBM's scalability and efficiency make it suitable for high-traffic scenarios. The model can be integrated into existing systems seamlessly.

## Recommendations:

- Proactive Resource Allocation
- Personalized User Experiences
- Customer Retention Strategies

## Next Steps:

- Explore additional features to improve model performance.
- Incorporate external data sources to enhance predictions.
- Monitor model performance and retrain periodically.

## Conclusion:

The Online Activity Prediction Model holds the potential to revolutionize how businesses interact with users, driving improved customer satisfaction, resource optimization, and overall business success.

**Note:** The datasets and code are organized into separate directories for raw, interim, and processed data, ensuring reproducibility and clarity in the project structure. Additionally, the requirements.txt file lists all necessary Python packages for setting up the project environment.
