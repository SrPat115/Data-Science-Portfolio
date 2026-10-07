# Project 1 - Commute Time in North Carolina Counties

## Research Question

What factors are associated with average commute time across North Carolina counties?

---

## 1. Problem Definition

### Background

Commute time is something nearly everyone needs to consider in their schedules. Whether it's school, work, or even just to have fun doing whatever, reliable transportation is important. Commute times are also shown to be closely linked to stress levels and productivity. 

#### Sources: #### 

1) Federal Highway Administration. (2019). Does travel time reliability matter? U.S. Department of Transportation. https://ops.fhwa.dot.gov/publications/fhwahop19062/

- The Federal Highway Administration explains that travel time affects more than transportation efficiency. Longer or unreliable travel can contribute to stress, lateness, reduced productivity, and less time available for family or other activities.

2) Centers for Disease Control and Prevention. (2026, July 16). Transportation. Environmental Public Health Tracking. https://www.cdc.gov/environmental-health-tracking/php/data-research/transportation.html

- The Centers for Disease Control and Prevention explains that transportation choices can influence air quality, traffic safety, and physical and mental health. Their Transportation Tracking Program also specifically includes average commute time as a county-level indicator.

3) North Carolina Department of Transportation. (2019). Public transportation strategic plan: Connecting North Carolinians to opportunities. https://www.ncdot.gov/divisions/integrated-mobility/public-transit-services/statewide-strategic-plan/Documents/technical-report-chapter-1.pdf

- The North Carolina Department of Transportation has specifically studied commuting patterns in North Carolina. Its statewide public transportation strategic plan found that commuting patterns are often regional, with longer-distance commuting markets occurring throughout the state. It also connects understanding commuting patterns to access to jobs, workforce development, and congestion management.

### Research Question

What factors are associated with average commute time across North Carolina counties?

### Why This Matters

Explain who might care about this question:

- Transportation planners
- Local governments
- Urban planners
- Employers
- Residents
- Policy makers

---

# 2. Data Description

## Dataset Source

- Data source:
- API:
- Year:
- Geographic area:
- Number of observations:
- Unit of analysis:

### Unit of Analysis

Each row represents one North Carolina county.

### Key Variables

| Variable | Concept | Measurement |
|---|---|---|
| Average commute time | Typical time workers spend traveling to work | Minutes |
| Population density | How concentrated the population is | People per square mile |
| Urban population | Degree of urbanization | Percentage |
| Work from home | Share of workers working remotely | Percentage |
| Public transportation | Share using public transit | Percentage |
| Driving alone | Share commuting alone by car | Percentage |

### Target Variable

**Average commute time**

This represents the average number of minutes workers spend traveling
to work.

### Missing Values

Explain:

- How many missing values existed
- Which variables had missing values
- How missing values were handled

---

# 3. Data Cleaning and Preparation

## Cleaning Steps

Describe what you did using pandas.

Examples:

1. Imported the dataset.
2. Selected relevant variables.
3. Renamed columns for readability.
4. Checked for missing values.
5. Converted variables to numeric types.
6. Removed or handled missing observations.
7. Checked for duplicate counties.
8. Created any necessary calculated variables.

### Why These Decisions Were Made

Briefly explain why you made each important cleaning decision.

For example:

> Rows with missing values for the target variable were removed because
> commute time could not be analyzed without a valid target value.

---

# 4. Exploratory Data Analysis

## Descriptive Statistics

Briefly describe:

- Mean commute time
- Minimum
- Maximum
- Standard deviation

### Visualization 1

[Insert visualization]

**Title:**

Average Commute Time by North Carolina County

**What does this show?**

[Explain the major pattern you see.]

---

### Visualization 2

[Insert visualization]

**Title:**

Average Commute Time vs. Population Density

**What does this show?**

Explain the relationship or pattern.

---

### Additional Visualization

(Optional)

You could include:

- Correlation heatmap
- Commute time vs. work-from-home percentage
- Commute time vs. public transportation
- Top/bottom 10 counties

---

# 5. Findings and Storytelling

## What Did We Find?

Summarize your major findings.

For example:

- Which counties had the longest commute times?
- Which had the shortest?
- Which variables appeared most strongly associated with commute time?
- Were there surprising counties or patterns?

### Connection to Research Question

Explain whether the analysis provides evidence that certain county
characteristics are associated with longer or shorter commute times.

### What We Cannot Conclude

Explain that:

> These relationships do not necessarily mean that one variable causes
> changes in commute time.

---

# 6. Ethics and Limitations

## Limitations

Discuss limitations such as:

- County-level data does not represent every individual.
- Average commute time hides differences between residents.
- The dataset may not capture traffic conditions.
- Remote/hybrid workers may affect commute statistics.
- Some variables may be correlated with one another.
- County-level patterns cannot necessarily be generalized to individuals.

## Potential Biases

Discuss possible:

- Sampling limitations
- Missing data
- Measurement differences
- Geographic differences
- Underrepresentation of certain populations

## Unanswered Questions

What would you investigate with more time?

Examples:

- How does commute time vary within counties?
- How has commute time changed over time?
- Does access to public transportation reduce commute times?
- How do commute times differ between rural and urban areas?

---

# 7. Code and Transparency

## Python Code

[Link to Jupyter Notebook]

[Link to GitHub repository]

The analysis was conducted using:

- Python
- pandas
- matplotlib
- seaborn

## Data Sources

Provide links to the original data source and API documentation.

## Academic Sources

Provide at least three peer-reviewed sources in APA format.

## AI Usage Disclosure

Explain whether generative AI was used.

Example:

> Generative AI tools were used as a supplemental learning resource to
> explain Python syntax, troubleshoot errors, and provide suggestions for
> organizing the analysis. All code was reviewed, tested, and modified by
> the author. AI was not used to replace interpretation of the results.

---

# 8. Conclusion

Briefly answer the research question.

Summarize:

1. What you found
2. Which factors appeared most associated with commute time
3. Important limitations
4. What could be investigated next
