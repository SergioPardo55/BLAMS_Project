# Bayesian Learning and Monte Carlo Simulations: US GDP & Inflation

## Project Overview

This project aims to model and analyze two key economic indicators of the United States: **Gross Domestic Product (GDP)** and the **Consumer Price Index (CPI)**, using Bayesian learning and Monte Carlo simulations. The project explores several time series models, including AR, ARMA, and VAR models, to fit and analyze the time series data. Additionally, model comparison and evaluation are performed using Information Criteria like BIC, DIC, and WAIC.

---

## Table of Contents

- [Project Description](#project-description)
- [Data](#data)
- [Models Implemented](#models-implemented)
- [Results](#results)
- [Installation and Usage](#installation-and-usage)
- [Contributors](#contributors)
  
---

## Project Description

In this project, we implemented various Bayesian time series models to analyze and forecast **US GDP** and **CPI** data. The following models were explored:

- **Autoregressive (AR)** models
- **Autoregressive Moving Average (ARMA)** models
- **Vector Autoregression (VAR)** models for bivariate analysis

The project objectives are as follows:

1. Fit time series models to GDP and CPI data.
2. Compare the models using **BIC**, **DIC**, and **WAIC** criteria.
3. Perform a posterior analysis of the models and interpret results.

---

## Data

The dataset used for the analysis consists of time series data on **US GDP** and **Inflation (CPI)**, obtained from the [Federal Reserve Economic Data (FRED)](https://fred.stlouisfed.org/series/HSN1F). The data represents quarterly observations of:

- **GDP**: Seasonally adjusted, measured in billions of dollars.
- **CPI**: Represents consumer inflation, seasonally adjusted, indexed to 1982-1984=100.

---

## Models Implemented

1. **AR(1), AR(2) Models**  
   Used for univariate modeling of both GDP and CPI series. These models assume that future values are based on a linear relationship of past values.

2. **ARMA(1,1) Model**  
   Combines autoregressive (AR) and moving average (MA) processes to describe time series behavior.

3. **VAR(1) Model**  
   A multivariate model used for the joint modeling of GDP and CPI series, capturing interdependencies between them.

Each model was fitted using **Bayesian inference** through **MCMC sampling** implemented in **R with JAGS**. 

---

## Results

- **Model Comparison**  
  We compared the models using **Bayesian Information Criterion (BIC)**, **Deviance Information Criterion (DIC)**, and **Watanabe-Akaike Information Criterion (WAIC)**.

  The AR(1) model showed the best performance for both GDP and CPI in terms of **BIC**, **DIC**, and **WAIC**.

- **Posterior Analysis**  
  Posterior distributions were analyzed, and 95% credible intervals were computed for key parameters such as the autoregressive coefficient, and variance of the error term.

See the **report.pdf** for detailed results, including plots of posterior distributions and trace plots.

---


## Installation and Usage

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/gdp-inflation-project.git
   cd gdp-inflation-project
   ```

2. Install the required packages:

   In **R**, install necessary packages using:

   ```R
   install.packages(c("rjags", "coda", "ggplot2"))
   ```

3. Run the scripts:

   - To fit the models:  
     Open **models.R** and run the code in **RStudio**.
   
   - To generate posterior plots:  
     Run **posterior_analysis.R**.

---

## Contributors

- Chiara Fossà  
- Sergio Pardo  
- Sara Zappia  

**Supervised by:** Prof. F. Bassetti  
