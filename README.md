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
This project uses a dataset from the World Bank's health database, available on [Kaggle](https://www.kaggle.com/datasets/bushraqurban/world-health-indicators-dataset).

![Screenshot (69)](https://github.com/user-attachments/assets/66c5321d-a752-4410-9908-4557d7fb95c5)

The dataset includes:
- country: The name of the country.
- country_code: ISO country code.
- year: Reporting year.
- health_exp: Health expenditure as a percentage of GDP.
- life_expect: Life expectancy at birth (years).
- maternal_mortality: Maternal deaths per 100,000 live births.
- infant_mortality: Infant deaths (under 1 year) per 1,000 live births.
- neonatal_mortality: Neonatal deaths (under 28 days) per 1,000 live births.
- under_5_mortality: Deaths of children under 5 years per 1,000 live births.
- prev_hiv: Percentage of the population aged 15-49 years living with HIV.

## Methodology
### 1. Data Preprocessing
- Loaded the dataset into a pandas DataFrame and dropped the country_code column.
- Filled missing values using the mode of respective columns.
- Filtered out non-country entries in the country column.
- Mapped countries to their continents by creating a new column.
- Identified and masked outliers using boxplots.

### 2. Exploratory Data Analysis (EDA)
- Visualized outliers and distributions using boxplots and histograms.

![download](https://github.com/user-attachments/assets/32f82885-2449-4b22-b745-00eed690361a)
![download](https://github.com/user-attachments/assets/b3e671ac-2f9c-4e59-bb3e-7738323b25af)

- Calculated descriptive statistics with the .describe() method.
- Created correlation heatmaps, identifying a significant correlation between life_expect and health_exp (0.24).

![download](https://github.com/user-attachments/assets/550b5666-d9dd-48c7-a821-b212aa443e9a)

- Plotted health expenditure as a percentage of GDP distribution across continents.

![download](https://github.com/user-attachments/assets/ab48415b-61fb-4fa4-91b2-617ee0f1a09d)

- Plotted health metrics and trends across continents using bar charts.

![download](https://github.com/user-attachments/assets/e2ee8a7d-da84-4e92-8a3a-174ffb956993)

- Plotted moratlity rate and trend across continents using bar charts and line plot.

![download](https://github.com/user-attachments/assets/3b2ff671-a9c6-45b4-b3b3-b82842e604d0)

![download](https://github.com/user-attachments/assets/1bc25d25-da48-4f2b-afd1-b09fe00f9cd0)

- Explored relationships between health expenditure and mortality metrics and diseases incidence via scatter plots.

![download](https://github.com/user-attachments/assets/de32b278-d884-452f-96d0-a4416a849050)

![download](https://github.com/user-attachments/assets/e0d73449-386b-4cc6-aa66-6ebd686a10a0)

- Explored relationships between HIV Prevalence and Incidence of Tuberculosis via scatter plots.

![download](https://github.com/user-attachments/assets/c8a02c84-a5da-4ff8-b213-40ea7b7c3a44)

- Explored relationships between Prevalence of Undernourishment and Incidence of Tuberculosis via scatter plots.

![download](https://github.com/user-attachments/assets/01a52aba-3912-42b9-9dc1-d0e3f9b2e966)


### 3. Customer Segmentation
- **Segmentation Approach**: Used DBSCAN clustering, achieving a silhouette score of 0.5, outperforming other methods like K-means and Agglomerative Clustering.
- **Segmentation Variables**: Clustered based on health_exp and life_expect.

#### Customer Profiles:
- **Outliers**: Countries with extreme health expenditure or life expectancy rates, such as Angola, Malawi (low expenditure), and Nauru (high expenditure).
- **Healthy & Wealthy**: Countries with similar health expenditure patterns and life expectancy rates.

![download](https://github.com/user-attachments/assets/91c9842f-e1e8-4ae2-8a91-7f31e67adb1e)

![download](https://github.com/user-attachments/assets/038fc033-dfc0-45f7-890f-41e17956cb74)

### 4. Model Training
- The dataset was split into training (80%) and testing (20%) sets.
- A baseline model was created using the mean value of the target variables and the Mean Absolute Error (MAE) was calculated to establish a performance benchmark.

### 5. Model Selection and Evaluation
Several machine learning models were trained and evaluated, including:
- Random Forest Regressor
- Linear Regression
- Decision Tree Regressor (chosen for its robustness  and lowest MAE, with a 43.6% error reduction)
- XGBoost Regressor

### How the Project Can Help
This project provides actionable insights into the relationship between healthcare resource allocation and key health outcomes such as life expectancy and mortality rates, enabling policymakers to make data-driven decisions for optimal healthcare investments. By clustering countries based on health expenditure and outcomes, it highlights disparities and identifies outliers requiring targeted interventions. The predictive models offer robust forecasts of health trends, helping organizations and researchers anticipate challenges and allocate resources effectively. Ultimately, the project serves as a vital tool for fostering equity, improving health outcomes, and supporting strategic decision-making in global healthcare initiatives.

Abdullahi Olalekan Abdulmumeen</br>
Applied Data Scientist</br>
Olalekanabdulmumeen3@gmail.com</br>
