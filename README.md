# Ironhack Datathon: ML Predictive Model

## Challenge

### Goal:
Given a dataset with information about stores, **build a Machine Learning Model to predict the revenue of other shops of the same brand**.

### Rules:
+ :stopwatch: Participants had **6 hours** since the dataset release to complete the full process **(EDA, Modeling, Evaluation)**.
+ :chart_with_upwards_trend: After the 6h, a new **dataset for validation** with no labels (data about revenues) was released. Participants had **30 min** to apply their models to predict the revenues of the stores in the new dataset and submit their work.
+ :outbox_tray: **Submissions** were individual, and included: 
  + Output file with the index of the stores in the validation dataset and participants' sales prediction for each store.
  + Pickled version of the **model built** and any **feature engineering** steps used. 
+ :white_check_mark: The teaching staff compared the predictions with the real data and communicated the final scores. 


## Results

Achieved a score of **0.9839 (98.4%)**. 

Used Decision Tree Regression model with **Gradient Boosting** (highest scores after evaluating multiple models).


## Tech

[![Python](https://img.shields.io/badge/Python-9146FF?style=for-the-badge&logo=python&logoColor=white&labelColor=101010)]()
[![Pandas](https://img.shields.io/badge/Pandas-5865F2?style=for-the-badge&logo=pandas&logoColor=white&labelColor=101010)]()
[![Numpy](https://img.shields.io/badge/Numpy-5865F2?style=for-the-badge&logo=numpy&logoColor=white&labelColor=101010)]()
[![Sklearn](https://img.shields.io/badge/sklearn-5865F2?style=for-the-badge&logo=scikit-learn&logoColor=white&labelColor=101010)]()
[![Matplotlib](https://img.shields.io/badge/Matplotlib-5865F2?style=for-the-badge&logo=matplotlib&logoColor=white&labelColor=101010)]()
[![Seaborn](https://img.shields.io/badge/Seaborn-5865F2?style=for-the-badge&logo=seaborn&logoColor=white&labelColor=101010)]()
[![Jupyter](https://img.shields.io/badge/Jupyter-5865F2?style=for-the-badge&logo=Jupyter&logoColor=white&labelColor=101010)]()


## Process

*(See details in the .ipynb files)*

1. Understood the **business problem** and data provided. Identified it as a **regression** problem (labels are sales, and all other attributes are features).
2. Performed **EDA**:
    - **Exloration** (shape, data types, nulls, etc.)
    - Data **cleaning**. The dataset quality was good, so this step went smoothly. Changes included dropping unnecessary columns.
    - **Feature engineering**. Converted DateTime into ordinal values, and used **one-hot-encoding** (created dummies) to convert all categorical into numerical values.
    - Analysis. Used **visualizatio**n (matplotlib, seaborn) to analyze correlations, find outliers, etc.
3. Prepared data (**feature selection, train/test splitting**).
4. **Trained and evaluated models**. Being this a regression problem, the following models were tested: **Linear Regression, Decission Tree Regressor, K-Neighbors Regressor, Ridge, Lasso**. The best results were obtained using Decission Trees (score 0.88, no overfitting).
5. Applied **ensemble methods** to optimize the Decission Tree model (**Random Forest, XGBoost, Gradient Boosting**). Best results achieved with Gradient Boosting (score 0.95, no overfitting).
6. **Tuned hyperparameters**. After analyzing and plotting the optimal max_depth hyperparameter to avoid overfitting, tested results tuning other hyperparameters (e.g. n_estimators, random_state). Achieved final **score of 0.9839 (98.4%)** with the validation dataset.
7. **Hyperparameter Optimization**. As a next step, I would've continued tuning hyperparameters (see constraints below).

## Constraints

Faced constraints due to the performance of the computer used (MackBook Pro early 2015) and limited time to train the models. 

Having more time and/or a faster machine, I would've used **Hyperparameter Optimization** (Random Search / Grid Search) to better customize the hyperparameters to the given challenge and improve the results.

## Dataset Description

| Feature               | Description |
| ------                | -----------|
| Store_ID              | Shop's unique identifier|
| Day_of_week           | Encoded from 0 to 6 |
| Date                  | day, month and year of the data point |
| Nb_customers_on_day   | customers that showed up that day |
| Open                  | binary variable (0 if closed, 1 if open)
| Promotion             | binary variable (0 if no promos that day, 1 if yes) |
| State_holiday         | encoded 0, a, b, c (0 if no holidays, and otherwise, the letter indicates which state holiday it was) |
| School_holiday        | binary variable (0 if holiday, 1 if not)

*The first dataset to build the model included also the labels (Sales of each store).* 

## Special Thanks

Thanks to all my bright and supportive bootcamp classmates! :technologist: :woman_technologist: 

Even though this was an indvidual competition, we worked collaboratively and exchanged ideas. This allowed us to complete the challenge ahead of time and obtain higher scores than previous cohorts. 
