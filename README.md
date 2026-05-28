# Infrared Thermography Temperature Dataset Analysis

An in-depth multivariate statistical analysis of the **Infrared Thermography Temperature Dataset**. This project explores the underlying structure of thermal image features and environmental conditions to understand their relationship with human body temperature.

## Project Overview
The main goal of this study is to model and understand how thermal image features (extracted from various facial regions) and environmental conditions (such as ambient temperature and humidity) relate to human body temperature. 

Since the dataset contains 33 mixed-type features, direct interpretation is highly complex. This project applies advanced multivariate statistical techniques to reduce dimensionality, identify hidden patterns, and explore relationships between variable sets.

##  Objectives
* **Dimensionality Reduction:** Simplify the dataset's complexity while retaining the majority of its variation.
* **Latent Structure Identification:** Discover hidden patterns among the thermal features.
* **Relationship Exploration:** Determine how well environmental conditions and facial thermal readings can collectively explain variations in oral temperature.

##  Dataset Description
* **Source:** [UCI Machine Learning Repository (ID: 925)](https://archive.ics.uci.edu/dataset/925/infrared+thermography+temperature+dataset)
* **Instances:** 1020 (Reduced to 969 after outlier removal)
* **Features:** 33 (Continuous and Categorical)
* **Target Variable:** Oral Temperature
* **Subject Area:** Health and Medicine

##  Methodology & Tech Stack

### Tools & Libraries
* **Language:** Python
* **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `factor_analyzer`, `ucimlrepo`

### Analytical Pipeline
1.  **Data Preprocessing:** * Imputed missing values (mean imputation for distance).
    * Encoded categorical variables (Gender, Age, Ethnicity) using Label Encoding.
    * Detected and removed outliers using the **Isolation Forest** algorithm (5% contamination).
    * Standardized features using `StandardScaler`.
2.  **Principal Component Analysis (PCA):** Applied to reduce the 33 dimensions down to a smaller set of principal components that explain over 80% of the variance.
3.  **Factor Analysis (FA):** Executed using Varimax rotation to identify underlying latent structures grouping the facial temperature and environmental variables. 
4.  **Canonical Correlation Analysis (CCA):** Used to evaluate the strength of the relationship between two specific sets of variables: Environmental/Demographic factors vs. Thermal measurements.

##  Key Findings
* **PCA:** The dataset can be effectively represented using a small number of components (4-6 components capture the vast majority of the variability). Thermal, environmental, and demographic features naturally separate into distinct components.
* **Factor Analysis:** Revealed three primary latent factors driving the data:
    * *Factor 1:* Overall facial thermal intensity (eyes and cheeks).
    * *Factor 2:* Forehead temperature variation.
    * *Factor 3:* Mouth temperature characteristics.
* **CCA:** Showed a moderate but meaningful correlation ($~0.58$) between environmental/demographic variables and thermal features, indicating that ambient conditions do influence thermal readings, but other physiological factors are also at play.

## Author
**Sachethana Abeyrathne** *Undergraduate in Statistics and Operations Research*
