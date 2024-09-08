# README: Titanic Survival Prediction

## Author: Arush Biswas

## Batch: August

## Domain: Data Science

## Aim

The aim of this project is to build a model that predicts whether a passenger on the Titanic survived or not based on given features.

## Dataset

The dataset for this project is imported from a CSV file, "archive.zip". The dataset contains information about passengers on the Titanic, including their survival status, class (Pclass), sex (Gender), and age (Age).

## Libraries Used

The following important libraries were used for this project:

- numpy
- pandas
- matplotlib.pyplot
- seaborn
- sklearn.preprocessing.LabelEncoder
- sklearn.model_selection.train_test_split
- sklearn.linear_model.LogisticRegression

## Data Exploration and Preprocessing

1. The dataset was loaded using pandas as a DataFrame, and its shape and a glimpse of the first 10 rows were displayed using `df.shape` and `df.head(10)`.
2. Descriptive statistics for the numerical columns were displayed using `df.describe()` to get an overview of the data, including missing values.
3. The count of passengers who survived and those who did not was visualized using `sns.countplot(x=df['Survived'])`.
4. The count of survivals was visualized with respect to the Pclass using `sns.countplot(x=df['Survived'], hue=df['Pclass'])`.
5. The count of survivals was visualized with respect to the gender using `sns.countplot(x=df['Sex'], hue=df['Survived'])`.
6. The survival rate by gender was calculated and displayed using `df.groupby('Sex')[['Survived']].mean()`.
7. The 'Sex' column was converted from categorical to numerical values using LabelEncoder from `sklearn.preprocessing`.
8. After encoding the 'Sex' column, non-required columns like 'Age' were dropped from the DataFrame.

## Model Training

1. The feature matrix `X` and target vector `Y` were created using relevant columns from the DataFrame.
2. The dataset was split into training and testing sets using `train_test_split` from `sklearn.model_selection`.
3. A logistic regression model was initialized and trained on the training data using `LogisticRegression` from `sklearn.linear_model`.

## Model Prediction

1. The model was used to predict the survival status of passengers in the test set.
2. The predicted results were printed using `log.predict(X_test)`.
3. The actual target values in the test set were printed using `Y_test`.
4. A sample prediction was made using `log.predict([[2, 1]])` with Pclass=2 and Sex=Male (1).
