

# Bayesian Learning and Monte Carlo Simulations (BLAMS) Project

## Project Title: GDP and Inflation Time Series Analysis

### Repository URL: [BLAMS_Project](https://github.com/SergioPardo55/BLAMS_Project)

## Authors:
- **Chiara Zappia** - ID: 10724941
- **Sergio Pardo Gutierrez** - ID: 10985243
- **Sara Fossà** - ID: 11016799

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data Description](#data-description)
3. [Model Specifications](#model-specifications)
4. [Methodology](#methodology)
5. [Model Comparison](#model-comparison)
6. [Posterior Analysis](#posterior-analysis)
7. [How to Run the Code](#how-to-run-the-code)
8. [References](#references)

## 1. Project Overview

This project focuses on the Bayesian analysis of time series data from the **Gross Domestic Product (GDP)** and **Consumer Price Index (CPI)** of the United States. Our objective is to:

- Analyze and model the two time series separately using different statistical models such as AR(1), ARMA(1,1), and AR(2).
- Compare the models' performance using information criteria (BIC, DIC, and WAIC).
- Perform a joint analysis using a bivariate **Vector Autoregression (VAR)** model.

### Goals:
- Fit individual time series models for GDP and CPI.
- Compare models using information criteria.
- Conduct joint modeling using VAR for bivariate analysis.
- Provide insights through Bayesian posterior analysis and model diagnostics.

## 2. Data Description

The data used in this project consists of two time series:
1. **Gross Domestic Product (GDP)**: Measures the market value of goods and services produced in the United States.
   - Frequency: Quarterly
   - Source: [U.S. Bureau of Economic Analysis](https://fred.stlouisfed.org/series/HSN1F)
2. **Consumer Price Index (CPI)**: Measures the average change over time in the prices paid by urban consumers for a basket of goods and services.
   - Frequency: Quarterly
   - Source: [U.S. Bureau of Labor Statistics](https://fred.stlouisfed.org/series/CPIAUCSL)

The dataset covers the period from **1948-01-01 to 2024-01-01** and has been pre-processed to calculate the percent change from the previous year.

## 3. Model Specifications

We implement the following models:

1. **Autoregressive (AR) Models**:
   - **AR(1)**: Predicts future values based on the immediate past observation.
   - **AR(2)**: Incorporates two lagged values to predict future observations.

2. **Autoregressive Moving Average (ARMA)**:
   - **ARMA(1,1)**: Combines AR and MA components to describe the time series behavior.

3. **Vector Autoregression (VAR)**:
   - **VAR(1)**: Models GDP and CPI jointly, capturing the linear interdependencies between the two variables.

### Priors and Likelihoods:
- Each model includes carefully chosen prior distributions (Uniform, Normal, Gamma) to reflect minimal prior information.
- The likelihoods for each model are based on standard assumptions of normality for errors.

For more details, refer to the [Report](./Report.pdf) and the R code files in the repository.

## 4. Methodology

The models were implemented using **JAGS** (Just Another Gibbs Sampler) through **R** for Bayesian inference. MCMC methods were used to sample from posterior distributions, with the following parameters:
- `n.adapt = 1000`, `n.iter = 10000`, `n.burnin = 2000`, and `n.chains = 1`.

### Tools:
- **R**: Main language for model implementation.
- **JAGS**: Used for Bayesian inference and MCMC simulations.
- **ggplot2**: For visualization of posterior distributions.

## 5. Model Comparison

We compared the models using three main criteria:
- **BIC** (Bayesian Information Criterion)
- **DIC** (Deviance Information Criterion)
- **WAIC** (Watanabe-Akaike Information Criterion)

The **AR(1)** model was found to be the best for **GDP** data based on all criteria, while the **AR(2)** model was preferred for **CPI** data.

## 6. Posterior Analysis

Posterior distributions were analyzed and plotted to evaluate the uncertainty and variability in the model's estimates. Confidence intervals and trace plots for model parameters (e.g., autoregressive coefficients) were included in the analysis.

Example of posterior analysis for AR(1) GDP and CPI models:
- **Posterior Mean**: Estimation of central tendency.
- **95% Credible Interval**: Range of plausible values for model parameters.

Visualizations of the posterior analysis can be found in the `Posterior_Analysis` folder.

## 7. How to Run the Code

### Prerequisites
- **R** (version ≥ 4.0)
- **JAGS** (version ≥ 4.3.0)
- R packages: `rjags`, `coda`, `ggplot2`, `bayesplot`

### Steps:
1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/SergioPardo55/BLAMS_Project.git
   ```
2. Install the required R packages:
   ```R
   install.packages(c("rjags", "coda", "ggplot2", "bayesplot"))
   ```
3. Open the R scripts in the `Code/` directory and run the files in the following order:
   - `AR_Model.R`
   - `ARMA_Model.R`
   - `VAR_Model.R`

4. The models will automatically perform MCMC sampling and generate posterior distributions. Plots and results will be saved in the `Results/` directory.

## 8. References

1. Kotu, Vijay, and Bala Deshpande. *Data Science (Second Edition)*, 2019.
2. Bobbitt, Z. (2021). *Time Series Analysis with Bayesian Methods*. 

For more detailed information on the models and methodology, refer to the [Report](./Report).


