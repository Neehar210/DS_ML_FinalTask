# DS_ML_FinalTask
## Spectrum Internship Final Task


The final project of the internship was very much informative and provided me with a huge oppurtunity to apply my data analysis and machine learning knowledge on a real world data set.

## Introduction

The **primary objective** of the final task was to find the *most important* features from all the attributes of the dataset which could describe most of the variability in the dataset.

**Evaluation metric** chosen for the analysis was *R-score* metric which accounts for the variability explained by the model.

## Methodology
The following python libraries were used for the solving the problem:
- `numpy`
- `pandas`
- `matplotlib`
-  `sklearn`
-  `statsmodels`

The following procedure was followed in this project:
   1. The categorical values in the whole of the dataset were encoded in *onehot* coding using the `skelarn.preprocessing.OneHotEncoder` class.
   2. The whole dataset was split into train and test sets in the ratio *80:20* using the `sklearn.model_selection.train_test_split` function.
   3. In the modelling part, *LinearRegression* model was used from `sklearn.linear_model.LinearRegression`.
   4. Train data was used to fit the model and test data was used to test the model based on the *R-score*.
   5. The next step was to eliminate redundant features with the help of **backward elimination** and `statsmodels.api.OLS` function.

## Results

The plot between the true values and predicted values of the test set suggest that there is linear relationship between the independent vaiables and response variables.
![Regression](/images/regression_line.png)

The final model with the most important features was obtained as<br>
*final_grade* = -0.0777 - 0.2017(*age*) + 0.3572(*famrel*) + 0.0437(*absences*) + 1.1579(*G1*) + 1.9780(*G2*)

The *R-score* for the model was obtained to be *0.972* which means that *97%* of variability in the dataset could be explained by the model.

The **Error Analysis** of the model also suggested that the statistical tests performed by the `OLS` model was significant and had very little or no room for errors.

1. The errors are randomly distributed and have constant variance.![Residual Plot](/images/erorr_plot.png)
2. The errors are *heavy-tailed*, *skewed* and overally conform to <font color = "blue">*normal distribution*</font>.![qqplot](/images/qqplot_error_norm.png)
