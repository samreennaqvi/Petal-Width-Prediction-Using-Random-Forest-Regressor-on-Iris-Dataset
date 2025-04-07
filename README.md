# Petal-Width-Prediction-Using-Random-Forest-Regressor-on-Iris-Dataset
Objective:

The goal of this project is to build a machine learning model that can accurately predict the petal width of Iris flowers using the remaining features (sepal length, sepal width, and petal length).
We will use a Random Forest Regressor from the sklearn library and evaluate its performance with suitable regression metrics.
🛠️ Methodology:

    Dataset Loading:

        Load the Iris dataset from sklearn.datasets.

    Feature Selection:

        Use sepal length, sepal width, and petal length as input features (X).

        Use petal width as the target variable (y).

    Train-Test Split:

        Split the data into training and testing sets using an 80-20 ratio.

    Model Training & Hyperparameter Tuning:

        Use RandomForestRegressor and tune hyperparameters like:

            n_estimators

            max_depth

            min_samples_leaf

        Use GridSearchCV for finding the best combination of parameters.

    Model Evaluation:

        Evaluate the model using:

            R² Score

            Mean Squared Error (MSE)

            Mean Absolute Error (MAE)

📊 Results:

    ✅ Best Parameters Found:

    {'max_depth': 20, 'min_samples_leaf': 5, 'n_estimators': 15}

    ✅ Evaluation Metrics on Test Set:

        R² Score: 0.929

        Mean Squared Error (MSE): 0.036

        Mean Absolute Error (MAE): 0.142

This indicates a highly accurate model in predicting petal width from the other attributes.
🧠 Conclusion:

The Random Forest Regressor successfully learned the patterns between input features and petal width. The high R² value (≈ 0.93) suggests that the model explains most of the variability in the target. This demonstrates the effectiveness of ensemble methods for regression tasks even on small datasets like Iris.

# Role of algoparams_with_ui.json

    This JSON file was provided to us as part of the assignment or dataset.

    It contained predefined hyperparameters meant to be used for model training and optimization.

✅ What we did with it:

    Loaded the file using Python’s json module:

with open('algoparams_with_ui.json') as f:
    params = json.load(f)

The file contained keys like:

{
  "n_estimators": [10, 15, 20],
  "max_depth": [5, 10, 15, 20],
  "min_samples_leaf": [1, 2, 5]
}

We used these parameters in a GridSearchCV to tune the Random Forest Regressor:

grid = GridSearchCV(RandomForestRegressor(), param_grid=params, cv=5)
grid.fit(X_train, y_train)

This allowed us to find the best model configuration using values directly sourced from the JSON file — keeping it modular, clean, and reproducible.
