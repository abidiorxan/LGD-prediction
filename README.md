# LGD-prediction
LGD prediction model built as part of a full Expected Credit Loss (ECL) modeling pipeline (PD–LGD–EAD framework).
Project Overview
This repository presents a Loss Given Default (LGD) prediction model developed using Linear Regression within a structured credit risk modeling workflow.

LGD is one of the three key components required for Expected Credit Loss (ECL) estimation under IFRS 9. The three core parameters of ECL are:
Probability of Default (PD)
Loss Given Default (LGD)
Exposure at Default (EAD)

This project focuses specifically on the LGD component. It is designed as part of a broader roadmap aimed at building a complete ECL modeling framework.
Business Context:
Loss Given Default measures the proportion of exposure that is not recovered once a borrower defaults. Accurate LGD estimation is essential for:
IFRS 9 Expected Credit Loss calculations
Regulatory capital assessment under Basel frameworks
Credit risk pricing and portfolio analytics
Stress testing and risk forecasting

The modeling approach in this project reflects a simplified but structured version of practices commonly used in banking risk environments.
Methodology:
The model development process follows a disciplined analytical pipeline.
Data Preprocessing.
Data loading and validation.
Missing value assessment.
Outlier detection using the IQR method.
Outlier capping to reduce distortion.
Feature Engineering.

Group-based aggregation features such as:
Mean income by region
Mean previous defaults by credit score group

Statistical Analysis:
Kolmogorov–Smirnov normality testing
Spearman correlation analysis
Target correlation filtering (minimum 10 percent threshold)
Intercorrelation filtering (60 percent threshold)
Variance Inflation Factor (VIF) analysis to control multicollinearity

Feature Selection:
Highly collinear and statistically weak variables were removed to improve model stability and interpretability.
Encoding and Scaling
One-hot encoding for categorical variables (drop-first approach)
Standardization using StandardScaler

Model Development:
80/20 train-test split
Linear Regression model estimation
Comparison of training and test performance to monitor overfitting

Model Evaluation:
Mean Absolute Error (MAE)
Mean Squared Error (MSE)
Root Mean Squared Error (RMSE)
R-squared (R²)

Additionally, each independent variable was tested individually using univariate regression to assess standalone explanatory power and reduce overfitting risk.

Final Model Features
The refined LGD model includes the following predictors:

Income
Loan Term
Debt-to-Income Ratio
Previous Defaults
Employment History
Exposure Amount
Deployment

The trained model is applied to a new dataset using the same preprocessing, feature engineering, and scaling steps. The final output is a predicted LGD percentage for each observation.

Project Roadmap
This repository represents the LGD component of a broader ECL modeling initiative. The next stages include:
Development of a Probability of Default (PD) model

Estimation of Exposure at Default (EAD)

Integration of PD, LGD, and EAD into a full ECL calculation framework
