# U.S. Cancer Regression Data Analysis
This project investigates cancer incidence and mortality across U.S. regions using public datasets. The analysis involves data cleaning, exploratory analysis, hypothesis testing, and visualizations—all conducted in a Jupyter Notebook (Google Colab).
---
## Overview

### Objective:

Explore how various factors—including demographics, income, poverty, and race—relate to cancer cases and mortality across U.S. counties and census areas.

### Key Questions Addressed:

Which regions report the highest average number of cancer cases and deaths?

How are clinical trials, insurance coverage, income, and poverty linked to cancer statistics?

What correlations exist between racial composition and cancer outcomes?

Can a statistically significant correlation be established between racial percentages and cancer death rates?

## Data Sources

### Cancer Data (cancer_reg.csv):

Contains information such as average annual cancer cases, deaths, incidence rates, median income, poverty percentage, and several demographic indicators for 3047 regions.

### Household Data (avg-household-size.csv):
Includes household size and location identifiers for 3220 regions (used to merge with the cancer dataset).

Both datasets are sourced from reputable platforms (e.g., Kaggle and census data) and span information from 2010–2016.

---
# Team and Tools
Team Members:

Patrick Erickson, Zack Ranjan, Joshua Santiago

---
# Technologies Used:

Python (Jupyter Notebook, Google Colab)

Libraries: Pandas, NumPy, Matplotlib, Seaborn

Setup:

The notebook starts by mounting Google Drive, loading CSV files, and installing the required libraries for analysis and visualization.

---
# Data Preparation
Loading and Merging

Data Import:

Both CSV files are loaded into pandas DataFrames.


---
# Merging Datasets:
The datasets are merged on a common geographical column (initially geography, later renamed to location) for combined analysis.

---
# Data Cleaning
#### Missing Values:

Missing data in critical columns (e.g., employment and insurance coverage) is filled with placeholder text ("Data not available").

#### Duplicates:
Duplicate rows are removed to ensure data integrity.

#### Renaming Columns:

Columns are renamed for clarity (e.g., avganncount → avgcasecount, medincome → medianincome).
# Exploratory Data Analysis (EDA)
## Research Question 1: Highest Cancer Case Counts
#### Method:
Group data by location and calculate the mean number of cancer cases.
#### Visualization:
Bar chart of the top 10 locations (Los Angeles County, CA leads).
## Research Question 2: Clinical Trials and Insurance Coverage
#### Method:
Determine the majority insurance type (Public vs. Private) per region and compare average clinical trials per capita.
#### Result:
Regions with predominantly private insurance tend to have higher clinical trial participation.
## Research Question 3: Regions with Highest Cancer Deaths
#### Method:
Calculate and sort the average number of deaths per year by region.
#### Visualization:
Horizontal bar chart displaying the top 20 regions.
#### Key Regions:
Los Angeles County (CA), Cook County (IL), Maricopa County (AZ), Harris County (TX), San Diego County (CA).
## Research Question 4: Income & Age in High-Death Regions
#### Method:
Analyze median income and median age for regions with high death rates.
#### Visualization:
Scatter plot showing the relationship between median age and median income.
## Research Question 5: Poverty and Incident Rate
#### Method:
Categorize poverty percentage into bins and assess their relationship with cancer incident rates.
#### Visualization:
Box plots reveal that median incident rates remain relatively stable across poverty categories, with several outliers.
## Research Question 6: Deaths, Income, and Poverty
#### Method:
**Create scatter plots to examine correlations:**

Median Income vs. Average Deaths: Weak positive correlation (r ≈ 0.223).

Poverty Percentage vs. Average Deaths: Very weak negative correlation (r ≈ -0.067).

## Research Question 7: Minority Composition and Cancer Metrics
#### Method:
Evaluate correlations between percentages of Black, Asian, and Other races and both incident rates and death counts.
#### Findings:
Asian Population: Nearly zero correlation with incident rates but a moderate positive correlation (r ≈ 0.443) with deaths.
Black and Other Races: Weak correlations observed with both metrics.
## Research Question 8: White Population Analysis
#### Method:
Assess the correlation between the percentage of the white population and cancer outcomes.
#### Findings:
Very weak negative correlations for both incident rate (r ≈ -0.015) and deaths (r ≈ -0.187).

---
# Hypothesis Testing
## Objective
### Hypothesis:
There is a correlation between racial composition (percentages of White, Black, Asian, and Other) and the average number of cancer deaths per year.
#### Null Hypothesis (H₀):
No correlation exists.
## Methodology
#### Randomization Test:
A randomization (or permutation) test is conducted by shuffling the race labels 10,000 times.
The correlation coefficients are recalculated for each shuffle to build a distribution of correlations.
#### Visualization:
Histograms display the distribution of randomized correlations, with observed correlation coefficients and confidence intervals annotated.
#### Statistical Inference:
P-values and Bonferroni corrections are computed to determine significance.

---
# Results
## Key Outcomes:
Statistically significant correlations are found:
Positive correlations for minority groups (Black, Asian, Other) with cancer death rates.
A weak negative correlation for the white population.
## Conclusion:
The null hypothesis is rejected, indicating that racial composition is indeed correlated with cancer mortality.

---
# Conclusion
## Insights:

There is a clear disparity in cancer outcomes across different racial groups.
Higher percentages of minority populations are associated with increased cancer deaths, whereas a higher percentage of white populations tends to correlate with slightly lower death rates.
Socioeconomic and demographic factors play complex roles in influencing these outcomes.
Implications:
The findings suggest a need for targeted healthcare interventions and further research into the underlying causes of these disparities, potentially addressing systemic inequities.

#### Next Steps:
Further analysis could incorporate additional variables (e.g., environmental factors, access to healthcare) to better understand and address the observed disparities.

---
# Additional Notes
The entire analysis was performed in a Jupyter Notebook, and the final report was exported to an HTML file using nbconvert.
The project demonstrates a comprehensive approach combining data manipulation, visualization, statistical testing, and hypothesis-driven inquiry.
