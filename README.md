# Model Optimization Assisting Efficient COVID-19 Vaccine Distribution

This project aims to propose a recommendation of the best model to predict county-level COVID-19 deaths in order to optimize the distribution of a future vaccine to the places in the US that are most in need (i.e., which counties will be the most hard-hit when the vaccine is ready).

To achieve this goal, we first gathered data from 1) New York Times' daily data on COVID-19 cases and deaths at the county level, 2) Opportunity Insights' county characteristics including baseline health measures, 3) PM COVID's annual, county-level data on air pollution (PM2.5) and weather (average winter/summer temperature and relative humidity), and baseline mortality (averaged across annual averages from 2000-2016). We also cleaned data and created dummy variables for each state.

Then, we developed OLS, Ridge, and LASSO regression models to predict COVID-19 deaths per capita using the above socio-economic, health, and weather/pollution data. We optimized our Ridge and LASSO regression models within the training dataset by uncovering parameter values that give us the lowest 10-fold Cross Validation error rate. 

The LASSO regression model with lambda = 0.00443 turned out to be the model that most accurately predicts COVID-19 deaths. Predictions based on this model could help shape public health authorities' recommendations about how to best deploy limited vaccines.

## Repo Organization

* [vardes.csv](vardes.csv) contains a list of variables that we used for our analyses. Note that this is not a full list of all the variables in the dataset, although it’s close (we ignored a few perfectly co-linear predictors)

* [Covid002.csv](Covid002.csv): the dataset we used 

* [covid_vax_dist.ipynb](covid_vax_dist.ipynb) contains the code used to clean the data and to develop and evaluate the model

* [covid_vax_dist.html](covid_vax_dist.html): html version of the analyses

* [covid_vax_dist.pdf](covid_vax_dist.pdf): pdf version of the analyses
