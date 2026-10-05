# Project 2: Broadband Access in North Carolina

**Project:** DTSC 2301 — Data Science Modeling and Society  
**Status:** Complete
**Author:** Patricio Martinez

---

## 1. Problem Definition

### Research Question

To what extent can socioeconomic characteristics explain differences in broadband access between urban and rural North Carolina counties?

### Prediction Problem

This project aims to predict **broadband access** across North Carolina counties using socioeconomic characteristics.

For this project, broadband access is defined as:

> **The percentage of households with a broadband internet subscription.**

The target variable for the model will be **broadband access percentage**.

**Problem type:** Regression

The model will attempt to predict a continuous percentage rather than assign counties to discrete categories.

### Who Could Benefit?

Understanding differences in broadband access may be useful for policymakers, community organizations, educators, and other groups interested in identifying areas where internet access may be limited.

### Why Does This Matter?

Reliable internet access can affect how easily people participate in education, employment, communication, healthcare, and other activities that increasingly depend on online services.

This project investigates whether measurable socioeconomic characteristics can help explain or predict differences in broadband access between North Carolina counties.

---

# 2. Background and Context

Broadband internet access has become increasingly important for participation in education, employment, healthcare, government services, and other aspects of daily life.

However, broadband access is not distributed equally across all communities. Differences in income, education, population characteristics, and other socioeconomic conditions may be associated with differences in household internet access.

### Supporting Research

**Source 1:**  
Board of Governors of the Federal Reserve System. (2024). Consumer & community context: Who lacks access to broadband? Federal Reserve. [Link](https://www.federalreserve.gov/publications/2024-july-consumer-community-context.htm) 

 - A peer-reviewed analysis of American Community Survey (ACS) data from 2014-2018 found strong associations between poverty rate and broadband access, and between educational attainment and broadband access. 

**Source 2:**  
Zahnd, W. E., Crouch, E., & White, D. (2022). Geographic, racial/ethnic, and socioeconomic inequities in broadband access. The Journal of Rural Health, 38(3), 519–526. [Link](https://onlinelibrary.wiley.com/doi/abs/10.1111/jrh.12635) 

- The Federal Reserve analyzed 2022 ACS data and found that 74% of households in nonmetro areas had a broadband subscription compared with 85% in metro areas. It also reports that higher-income households had higher rates of broadband access and that communities with higher poverty levels had lower rates of device ownership.

**Source 3:**  
Pew Research Center. (2024, January 31). Americans’ use of mobile technology and home broadband. Pew Research Center. [Link](https://www.pewresearch.org/internet/2024/01/31/americans-use-of-mobile-technology-and-home-broadband) 

- Pew Research Center conducted a 2023 survey that found that 57% of adults in households earning less than $30,000 subscribed to high-speed internet at home, compared with 95% among households earning $100,000 or more. They also found differences by education. Rural adults had a 73% home broadband subscription rate, compared with 77% among urban adults and 86% among suburban adults.

**What The Previous Research Suggests:**
The literature suggests broadband access is strongly associated with socioeconomic properties such as income, poverty rates, and educational attainment, as well as geographical location. Based on this literature, the project examines whether county-level differences in income, poverty, educational attainment, housing costs, unemployment, and rural population can help explain differences in broadband access.

---

# 3. Data Description

## Data Source

The data for this project will be obtained from:

**Source:** [censuss.gov](census.gov)
**Links:** 
#**2024 American Community Survey (ACS) 5-Year data:** [https://www.census.gov/programs-surveys/acs/data/data-via-api.html](https://www.census.gov/programs-surveys/acs/data/data-via-api.html)

#**2020 Decennial Census Demographic and Housing Characteristics File (DHC):** [https://www.census.gov/data/developers/data-sets/decennial-census/2020.html](https://www.census.gov/data/developers/data-sets/decennial-census/2020.html)

These sources were selected for their **credibility** and **major past contribution** to this research topic. 

## Unit of Analysis

Each observation (row) in the dataset represents **one county in North Carolina**. The dataset contains all 100 North Carolina counties, with each county described by its broadband access rate and selected socioeconomic characteristics.

The unit of analysis is the **county**, rather than an individual person or household. The socioeconomic and broadband measures represent aggregate estimates for each county obtained primarily from the U.S. Census Bureau's 2024 American Community Survey (ACS) 5-Year data.

> **One North Carolina county**

The analysis will therefore compare broadband access and socioeconomic characteristics across North Carolina counties.

## Dataset Size

- Number of observations: 100
- Number of variables: 7
- Geographic area: North Carolina counties
- Time period: 2019-2024

## Target Variable

**Broadband Access**

Definition:

> Percentage of households with a broadband internet subscription.

## Potential Features

The initial features considered for the model are:

1. **Median household income**
2. **Median gross rent**
3. **Poverty rate**
4. **Bachelor's degree or higher**
5. **Unemployment rate**
6. **Rural population** 

## Why Each Variable Were Chosen

| Variable                        | Why it was chosen                                                                                                                             |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **Broadband Access**            | Serves as the target variable, measuring differences in the percentage of households with a broadband subscription across counties.           |
| **Median Household Income**     | Measures economic resources that may influence a household's ability to afford internet service.                                              |
| **Median Gross Rent**           | Represents local housing costs and overall cost-of-living pressures that may affect how much income households can devote to internet access. |
| **Poverty Rate**                | Captures economic disadvantage that may be associated with lower ability to afford broadband service.                                         |
| **Bachelor's Degree or Higher** | Represents educational attainment, which may be associated with greater technology use and demand for broadband access.                       |
| **Unemployment Rate**           | Measures local labor-market conditions and economic disadvantage that may be related to broadband access.                                     |
| **Rural Percentage**            | Measures the degree of rurality in each county, allowing the model to examine whether broadband access differs as counties become more rural. |


## Data Limitations

* **Geographic coverage:** The dataset only includes the 100 counties in North Carolina, so the results may not apply to other states or the entire United States.
* **Different time periods:** Most variables come from the 2024 ACS 5-Year Estimates (2019–2023), while rural percentage comes from the 2020 Census. This means the variables do not all represent exactly the same period.
* **Missing information:** The dataset had no missing values after data preparation. However, Census estimates may not capture every factor that influences broadband access.
* **County-level data:** The data represents entire counties rather than individual households. This means the analysis cannot explain why a specific household does or does not have broadband.
* **Measurement limitations:** Broadband access is measured as the percentage of households with a broadband subscription. This does not measure the quality, speed, reliability, or affordability of the service.
* **Limited predictors:** The model only includes a small number of socioeconomic characteristics. Other factors, such as broadband infrastructure, geographic terrain, age, or internet availability, could also affect broadband access.
* **Association, not causation:** The analysis can identify relationships between socioeconomic characteristics and broadband access, but it cannot prove that one variable directly causes changes in another.

---

# 4. Data Understanding and Exploration

Before developing the machine-learning models, the dataset will be explored to understand the distributions, relationships, and potential problems within the data.


## Summary Statistics

<img width="977" height="193" alt="Screenshot 2026-10-04 at 8 01 11 PM" src="https://github.com/user-attachments/assets/5bb54583-ed85-477c-a5b0-fe599a6a6176" />

The summary statistics show that broadband access varies across North Carolina counties, ranging from **71.6% to 95.3%**, with an average of **86.2%**. Median household income also varies considerably, from **$41,685 to $105,768**. The counties differ in education, poverty, unemployment, and rurality as well, with rural population ranging from less than **1% to 100%**. Overall, the statistics show meaningful variation between counties, giving the model differences in socioeconomic characteristics to examine.

## Target Variable Distribution

<img width="576" height="453" alt="image" src="https://github.com/user-attachments/assets/5107ff32-e1cd-4ea6-8ef2-f83d78834416" />

This visualization will be used to determine whether broadband access is relatively evenly distributed across counties or whether certain counties have substantially higher or lower access.

## Feature Distributions

### Heatmap
<img width="945" height="790" alt="image" src="https://github.com/user-attachments/assets/3c5740ed-dd64-4944-818f-aad980e64981" />

### Histograms - [Here](https://raw.githubusercontent.com/SrPat115/Data-Science-Portfolio/main/projects/assets/project2/broadband-access-histograms.pdf)

### Boxplots - [Here](https://raw.githubusercontent.com/SrPat115/Data-Science-Portfolio/main/projects/assets/project2/broadband-access-boxplots.pdf)

### Scatterplots - [Here](https://raw.githubusercontent.com/SrPat115/Data-Science-Portfolio/main/projects/assets/project2/broadband-access-scatterplots.pdf)

## Relationships Between Variables

* Median gross rent had a very strong positive relationship with broadband access (r ≈ 0.96). Counties with higher median rents generally had higher broadband access.
* Rural population percentage had a strong negative relationship (r ≈ -0.86). Counties with larger rural populations generally had lower broadband access.
* Unemployment rate had a moderately strong positive relationship (r ≈ 0.71), while median household income was also very similar (r ≈ 0.70).

The strongest relationships suggest that housing/economic conditions and rurality are closely associated with differences in county-level broadband access.

The correlation between unemployment and broadband is positive, which may seem surprising; however, it does not mean higher unemployment causes higher broadband access.

## Outliers and Unusual Observations

The distributions show some potentially unusual observations. Broadband access ranged from approximately 71.6% to 95.3%, while rural population percentage ranged from less than 1% to 100%. Unemployment also had a relatively high maximum of approximately 13.0%, compared with a mean of about 5.2%.

---

# 5. Data Preparation and Feature Selection

Before training the models, the dataset will be prepared for machine learning.

## Missing Values

<img width="405" height="545" alt="Screenshot 2026-10-04 at 8 21 05 PM" src="https://github.com/user-attachments/assets/a3ca00a4-44a5-42ab-b490-4c87dce5a880" />

There were no missing values.

## Duplicate Observations

<img width="614" height="106" alt="Screenshot 2026-10-04 at 8 22 17 PM" src="https://github.com/user-attachments/assets/6ea4dd3c-8233-4425-8474-aebd914ed221" />

No duplicate values were found.

## Outliers

These counties represent real geographic and socioeconomic conditions, so removing them simply because they are unusual could remove meaningful information from the analysis.

Examples may include:

- Scaling numerical variables
- Log transformations
- Encoding categorical variables
- Creating new features

## Training and Testing Data

The dataset was divided into:

- **Training data:** 80%
- **Testing data:** 20%

---

# 6. Baseline and Model Development

## Baseline Model

**Baseline:** broadband_access ~ median_household_income + median_gross_rent + poverty_rate + bachelors_or_higher + unemployment_rate + rural_percent

OLS regression is appropriate here because it is a simple way to estimate how each socioeconomic characteristic is associated with broadband access and examine the direction and strength of those relationships. It also helps
measure how much variation in broadband access the predictors explain using R², and
make predictions of broadband access based on county characteristics.

## Machine-Learning Models

At least two machine-learning models will be developed and compared.

### Model 1: base_model (OLS Regression)

### Model 2: tree_model (Decision Tree)

The models were trained and evaluated using the same training/testing strategy and evaluation metrics.

---

# 7. Model Evaluation and Selection

## Evaluation Metrics

The following metrics were used to evaluate model performance:

| Metric                              | What it tells us                                                                                | Why it's useful                                                                                                                                                                                       |
| ----------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **MAE (Mean Absolute Error)**       | On average, how far the model's predictions are from the actual broadband access value.         | Easy to understand because it's in **percentage points**. For example, an MAE of 2 means the model is off by about 2 percentage points on average. **Lower is better.**                               |
| **RMSE (Root Mean Squared Error)**  | Similar to MAE, but it gives **extra weight to large prediction errors**.                       | Helps us see whether the model occasionally makes particularly bad predictions. **Lower is better.**                                                                                                  |
| **R² (R-squared)**                  | Shows how much of the variation in broadband access the model can explain using the predictors. | Helps us judge how well the model explains differences between counties. For example, an R² of 0.80 means the model explains about **80% of the observed variation**. **Higher is generally better.** |

## Model Performance

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| OLS Base Model | 1.51 | 1.84 | 0.80 |
| OLS New Model | 1.51 | 1.86 | 0.79 |
| OLS New Model 2 | 1.51 | 1.90 | 0.78 |
| Decision Tree | 4.69 | 6.07 | -1.22 |

## Model Comparison

The base_model performed the best, with favorable MAE, RMSE, and R^2. 
Some experimentation was done by dropping some variables. "New Model" dropped unemployment_rate and showed nearly no change in performance metrics. "New Model 2" drops poverty_rate in addition to unemployment_rate. This model shows slightly less desirable performance metrics.

Then there's the decision tree model. The reason the Decision Tree didn't do as well is because this is a regression problem. Its performance was so poor that it predicted worse than simply using the average broadband access for every county. 

## Final Model

**Selected model:** base_model: broadband_access ~ median_household_income + median_gross_rent + poverty_rate + bachelors_or_higher + unemployment_rate + rural_percent

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| OLS Base Model | 1.51 | 1.84 | 0.80 |

This model was selected based on the performance metrics and actual vs. predicted plot. Together, the relatively low MAE and RMSE and the high R² suggest that the OLS Base Model makes reasonably accurate predictions and captures much of the variation in broadband access across North Carolina counties. 

<img width="563" height="453" alt="image" src="https://github.com/user-attachments/assets/7fd2eb07-f2b7-4560-a0e6-9525a55d2e3b" />

The Actual vs. Predicted plot indicates a good model as well. Most of the points are close to the red diagonal line, which suggests the model gives good predictions. 

---

# 9. Limitations, Ethics, and Reflection

## Dataset Limitations

- County-level data may hide differences within individual communities.
- The data may not capture every factor affecting broadband access.
- Some variables may be measured differently across geographic areas.
- The analysis represents a particular time period.

## Potential Bias

The dataset only includes North Carolina counties and uses a limited number of socioeconomic variables. It may leave out important factors such as internet infrastructure, service availability, geographic barriers, and differences between households within the same county.

## Consequences of Incorrect Predictions

Incorrect predictions could affect rural communities, lower-income households, internet service providers, and government organizations when making decisions about broadband access and resources.

For example, inaccurate predictions could potentially lead decision-makers to incorrectly identify areas with greater or lesser broadband needs.

## Real-World Use

The model could be useful as a supporting tool for identifying patterns and areas that may need further attention, but it should not be used by itself to make major decisions about funding or resource allocation.

## Future Improvements

If additional time or data were available, I would consider:

- Adding additional socioeconomic variables
- Incorporating geographic characteristics
- Examining changes over multiple years
- Testing additional machine-learning models
- Performing additional hyperparameter tuning
- Conducting more detailed error analysis

## Reflection

I've learned how to compare two different models using performance metrics. I have also learned how to modify my GitHub so that my information can be presented in a neat and organized way. 

Discuss:

- What was challenging
- What modeling decisions you made
- What surprised you
- What you would do differently
- How the project improved your understanding of machine learning

---

# 10. Code and Transparency

## Code

**GitHub Repository:** [Link](https://github.com/SrPat115/Data-Science-Portfolio.git)

**Jupyter Notebook:** [pdf](https://srpat115.github.io/Data-Science-Portfolio/projects/assets/project2/Broadband-Access.html.pdf), [html](https://raw.githubusercontent.com/SrPat115/Data-Science-Portfolio/main/projects/assets/project2/Broadband-Access.html)

## Data Sources

**Source:** [censuss.gov](census.gov)
**Links:** 
#**2024 American Community Survey (ACS) 5-Year data:** [https://www.census.gov/programs-surveys/acs/data/data-via-api.html](https://www.census.gov/programs-surveys/acs/data/data-via-api.html)

#**2020 Decennial Census Demographic and Housing Characteristics File (DHC):** [https://www.census.gov/data/developers/data-sets/decennial-census/2020.html](https://www.census.gov/data/developers/data-sets/decennial-census/2020.html)

## References

Zahnd, W. E., Bell, N., & Larson, A. E. (2022). Geographic, racial/ethnic, and socioeconomic inequities in broadband access. The Journal of Rural Health, 38(3), 519–526. https://doi.org/10.1111/jrh.12635

Board of Governors of the Federal Reserve System. (2024, July 15). Expanding America's bandwidth: Gaps in rural and underserved communities. https://www.federalreserve.gov/publications/2024-july-consumer-community-context.htm

Gelles-Watnick, R. (2024, January 31). Americans' use of mobile technology and home broadband. Pew Research Center. https://www.pewresearch.org/internet/2024/01/31/americans-use-of-mobile-technology-and-home-broadband/

## AI Usage Disclosure

Generative AI tools were used during this project for:

AI was used for formatting tables from Jupyter Notebook to GitHub, creating plots, and summarizing and formatting sources. 

---

## Project Summary

This project investigates whether socioeconomic characteristics can be used to predict broadband access across North Carolina counties. The analysis includes data exploration, preprocessing, feature selection, machine-learning model development, model comparison, evaluation, and interpretation.

**Tools:** Python · Pandas · NumPy · Matplotlib · Seaborn · Scikit-learn

**Project Status:** [Complete]
