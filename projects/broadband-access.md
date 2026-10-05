# Broadband Access in North Carolina

**Project:** DTSC 2301 — Data Science Modeling and Society  
**Status:** In Progress  
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

### Dataset Limitations

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

#Heatmap
<img width="945" height="790" alt="image" src="https://github.com/user-attachments/assets/3c5740ed-dd64-4944-818f-aad980e64981" />

#Histograms - [Here](insert link here)

#Boxplots - [Here](insert link here)

## Relationships Between Variables

[Discuss important relationships discovered during exploratory analysis.]


## Outliers and Unusual Observations

[Discuss any outliers or unusual county-level observations identified during exploration.]

## Feature Selection

The exploratory analysis will be used to determine which variables should be included in the final model.

[Explain which variables were ultimately selected and why.]

---

# 5. Data Preparation and Feature Selection

Before training the models, the dataset will be prepared for machine learning.

## Missing Values

There were no missing values.

## Duplicate Observations

No duplicate values were found.

## Outliers

[Explain whether outliers were identified and whether any action was taken.]

## Feature Transformation

[Describe any transformations performed.]

Examples may include:

- Scaling numerical variables
- Log transformations
- Encoding categorical variables
- Creating new features

## Feature Selection

The final features used in the model are:

| Feature | Description | Reason for Inclusion |
|---|---|---|
| [Feature 1] | [Description] | [Reason] |
| [Feature 2] | [Description] | [Reason] |
| [Feature 3] | [Description] | [Reason] |
| [Feature 4] | [Description] | [Reason] |
| [Feature 5] | [Description] | [Reason] |

## Training and Testing Data

The dataset was divided into:

- **Training data:** [X]%
- **Testing data:** [X]%

[Explain why this split was selected.]

### Preventing Data Leakage

[Explain how preprocessing and feature selection were performed without allowing information from the test data to influence model training.]

---

# 6. Baseline and Model Development

## Baseline Model

Before training more complex models, a baseline model was established to provide a point of comparison.

**Baseline:** [Insert baseline]

[Explain why this baseline is appropriate for a regression problem.]

## Machine-Learning Models

At least two machine-learning models will be developed and compared.

### Model 1: [Model Name]

[Explain why this model was selected.]

### Model 2: [Model Name]

[Explain why this model was selected.]

### Optional Model 3: [Model Name]

[Explain why this model was selected, if applicable.]

## Hyperparameter Tuning

[Describe whether model hyperparameters were tuned.]

If tuning was performed:

- Method: [Grid Search / Random Search / etc.]
- Parameters tested: [Insert]
- Validation strategy: [Insert]

## Fair Model Comparison

The models were trained and evaluated using the same training/testing strategy and evaluation metrics.

---

# 7. Model Evaluation and Selection

## Evaluation Metrics

The following metrics were used to evaluate model performance:

### Mean Absolute Error (MAE)

[Explain what MAE measures and why it is useful for this problem.]

### Root Mean Squared Error (RMSE)

[Explain what RMSE measures and why it is useful.]

### R²

[Explain what R² measures and why it is useful.]

### VIF

[Explanation] 

## Model Performance

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Baseline | [ ] | [ ] | [ ] |
| Model 1 | [ ] | [ ] | [ ] |
| Model 2 | [ ] | [ ] | [ ] |
| Model 3 | [ ] | [ ] | [ ] |

## Model Comparison

[Explain how the models performed relative to the baseline and one another.]

Rather than relying on a single metric, the models will be compared using multiple measures of prediction performance.

## Final Model

**Selected model:** [Insert model]

[Explain why this model was selected based on the evaluation results.]

---

# 8. Model Interpretation and Insights

The final model will be examined to understand which features contribute most strongly to its predictions.

## Feature Importance

[Insert feature-importance visualization or other appropriate interpretation method.]

The most influential features were:

1. [Feature]
2. [Feature]
3. [Feature]

[Explain what these results mean.]

## Model Behavior

[Discuss important patterns found by the model.]

## Prediction Errors

[Examine where the model performed well and where it made larger errors.]

Potential analyses include:

- Actual vs. predicted values
- Prediction error distribution
- Largest prediction errors
- Residual plots

## What the Model Can Tell Us

[Explain what conclusions are supported by the model.]

## What the Model Cannot Tell Us

[Explain limitations on interpretation.]

In particular, an association between a feature and broadband access should not automatically be interpreted as evidence that the feature causes differences in broadband access.

---

# 9. Limitations, Ethics, and Reflection

## Dataset Limitations

[Discuss limitations of the data.]

Potential considerations include:

- County-level data may hide differences within individual communities.
- The data may not capture every factor affecting broadband access.
- Some variables may be measured differently across geographic areas.
- The analysis represents a particular time period.

## Potential Bias

[Discuss potential sources of bias in the dataset or modeling process.]

## Consequences of Incorrect Predictions

[Explain what could happen if the model makes inaccurate predictions.]

For example, inaccurate predictions could potentially lead decision-makers to incorrectly identify areas with greater or lesser broadband needs.

## Real-World Use

[Discuss whether the model would be appropriate for actual decision-making.]

The model should be considered an analytical tool rather than a replacement for additional community-level research and human decision-making.

## Future Improvements

If additional time or data were available, I would consider:

- Adding additional socioeconomic variables
- Incorporating geographic characteristics
- Examining changes over multiple years
- Testing additional machine-learning models
- Performing additional hyperparameter tuning
- Conducting more detailed error analysis

## Reflection

[Describe what you learned from the project.]

Discuss:

- What was challenging
- What modeling decisions you made
- What surprised you
- What you would do differently
- How the project improved your understanding of machine learning

---

# 10. Code and Transparency

## Code

**GitHub Repository:** [Insert link]

**Jupyter Notebook:** [Insert link]

## Data Sources

[Provide links and citations for all datasets used.]

## References

[APA references]

## AI Usage Disclosure

Generative AI tools were used during this project for:

[Describe specifically how AI was used.]

Examples may include:

- Explaining Python concepts
- Troubleshooting code
- Brainstorming analytical approaches
- Reviewing writing
- Helping understand statistical or machine-learning concepts

All analysis, modeling decisions, interpretation, and final conclusions were reviewed and completed by the author.

---

## Project Summary

This project investigates whether socioeconomic characteristics can be used to predict broadband access across North Carolina counties. The analysis includes data exploration, preprocessing, feature selection, machine-learning model development, model comparison, evaluation, and interpretation.

**Tools:** Python · Pandas · NumPy · Matplotlib · Seaborn · Scikit-learn

**Project Status:** [In Progress / Complete]
