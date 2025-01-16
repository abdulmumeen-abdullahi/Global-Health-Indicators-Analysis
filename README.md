# Global Health Indicators Analysis
## Overview of the Problem
Despite significant advancements in healthcare technologies and global initiatives, global health disparities and resource allocation challenges persist. High maternal and child mortality rates, preventable diseases, and inadequate healthcare spending remain prevalent in many countries. Socioeconomic inequalities, regional disparities, and inconsistent governmental commitment to healthcare funding exacerbate these challenges.

This project aims to address these issues by:
1.	Analyzing how countries allocate resources to health and the correlation of these investments with health outcomes such as life expectancy and mortality rates.
2.	Clustering countries based on their health resource allocation and life expectancy.
3.	Exploring trends in health spending, mortality rates, and disease prevalence across various regions.
4.	Developing predictive models to identify potential health disparities and forecast outcomes based on historical trends.
The project supports policymakers, researchers, and organizations in identifying critical areas for intervention, optimizing healthcare investments, and fostering equitable health outcomes globally.

## Data Used
This project uses a dataset from the World Bank's health database, available on [Kaggle](https://www.kaggle.com/datasets/bushraqurban/world-health-indicators-dataset). The dataset includes:
•	country: The name of the country.
•	country_code: ISO country code.
•	year: Reporting year.
•	health_exp: Health expenditure as a percentage of GDP.
•	life_expect: Life expectancy at birth (years).
•	maternal_mortality: Maternal deaths per 100,000 live births.
•	infant_mortality: Infant deaths (under 1 year) per 1,000 live births.
•	neonatal_mortality: Neonatal deaths (under 28 days) per 1,000 live births.
•	under_5_mortality: Deaths of children under 5 years per 1,000 live births.
•	prev_hiv: Percentage of the population aged 15-49 years living with HIV.

## Methodology
### 1. Data Preprocessing
•	Loaded the dataset into a pandas DataFrame and dropped the country_code column.
•	Filled missing values using the mode of respective columns.
•	Filtered out non-country entries in the country column.
•	Mapped countries to their continents by creating a new column.
•	Identified and masked outliers using boxplots.

### 2. Exploratory Data Analysis (EDA)
Visualized outliers and distributions using boxplots and histograms.
Calculated descriptive statistics with the .describe() method.
Created correlation heatmaps, identifying a significant correlation between life_expect and health_exp (0.24).
Plotted health metrics and trends across continents using bar charts and line plots.
Explored relationships between health expenditure and mortality metrics via scatter plots.

### 3. Customer Segmentation
##### • Segmentation Approach:
Used DBSCAN clustering, achieving a silhouette score of 0.5, outperforming other methods like K-means and Agglomerative Clustering.
##### • Segmentation Variables:
Clustered based on health_exp and life_expect.
#### Customer Profiles:
• **Outliers**: Countries with extreme health expenditure or life expectancy rates, such as Angola, Malawi (low expenditure), and Nauru (high expenditure).
• **Healthy & Wealthy**: Countries with similar health expenditure patterns and life expectancy rates.

### 4. Model Training
•	The dataset was split into training (80%) and testing (20%) sets.
•	A baseline model was created using the mean value of the target variables and the Mean Absolute Error (MAE) was calculated to establish a performance benchmark.

### 5. Model Selection and Evaluation
•	Several machine learning models were trained and evaluated, including:
o	Random Forest Regressor 
o	Linear Regression
o	Decision Tree Regressor (chosen for its robustness and accuracy)
o	XGBoost Regressor
•	The Decision Tree Regressor (chosen for its robustness and lowest MAE, with a 43.6% error reduction).
 How the Model Can Help
The Decision Tree Regressor offers actionable insights by predicting health outcomes like life expectancy and mortality rates based on historical trends. The model can help:
•	Policymakers: Allocate healthcare resources more effectively and identify regions with significant disparities.
•	Researchers: Target interventions that maximize health improvements for vulnerable populations.
•	Organizations: Optimize programs to address global health challenges and promote equitable access to care.
Abdullahi Olalekan Abdulmumeen
Applied Data Scientist
Olalekanabdulmumeen3@gmail.com
