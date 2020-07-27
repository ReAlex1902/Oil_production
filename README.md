# Oil production analysis 

This repository includes 2 folders:
data - includes csv files
scripts - includes scripts for plotting, feature extraction and neural network (LSTM)

## Data
- production.csv - given data about production of each oil well (each one has an API)
- wells_info.csv - given data about each oil well (each one has an API)
- wells_info_2.0.csv - new csv with calculated total_all_time and total_first_year features (they are calculated in script feature_preprocessing.ipynb)
- wells_info_train.csv - csv to train csv for models. Created and used in feature_preprocessing.ipynb
- wells_info_test.csv - csv to test csv for models. Created and used in feature_preprocessing.ipynb

## Scripts
- Plotting.ipynb - the script includes the code to create the plots of productions over the time. Includes the Moving average lines with window == 3 and window == 5. Also there                    are highlits of those months of production when production has increased by more than 10% compared to the previous month

- Feature_preprocessing.ipynb - counts the total liquid production for each oil well over all time and the first year (12 months). In the script the correlations between features                               are shown. The feature extraction is done with Principal Component Analysis (PCA). The data is splitted to train and test data, scaled. After the                                 analysis 3 models (XGBoost, Random Forest and SVM) are created, Mean Absolute Error and Mean Absolute Percentage Error are shown.

- Neural_Networks.ipynb - the data preprocessing is done to create labels and train data (y(i) -> y(i+1)). LSTM is created and predicts the liquid production one month ahead. Given 12 months LSTM predicts 12 months ahead in this script. All predictions for each API is plotted
