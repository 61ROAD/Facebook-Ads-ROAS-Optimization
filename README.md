# **📈 Facebook Ad Campaign Optimization & ROAS Prediction**

## **📌 Project Overview**

In the highly competitive digital marketing landscape, allocating budget blindly can lead to severely diminished returns. Understanding the precise statistical relationship between user demographics, ad engagement, and actual revenue is critical for maximizing **Return on Ad Spend (ROAS)**.

This project is a deep-dive statistical analysis and optimization engine for a comprehensive Facebook advertising dataset. Using **R and advanced statistical modeling**, I engineered custom marketing metrics and developed multiple linear regression (MLR) models to identify the key drivers of advertising efficacy. The core objectives of this project were to:

* **Attribute & Evaluate:** Quantify the exact financial impact of user characteristics (Age, Gender, Interest) and behavioral metrics (Impressions, Clicks) on Total Conversion Value.  
* **Optimize Budget Allocation:** Identify which demographic segments yield the highest ROAS to guide data-driven budget allocation and lower Customer Acquisition Cost (CAC).  
* **Model Selection:** Rigorously test, compare, and validate various statistical models to find the most robust predictor of ad performance.

## **📁 Project Structure**

.  
├── ROAdatacleaned1.csv         \# Cleaned and engineered Facebook Ads dataset  
├── ROAS\_Statistical\_Analysis.Rmd   \# Main R Markdown file containing all code, plots, and statistical tests  
└── README.md                   \# Project documentation

## **🧠 Data Architecture & Modeling**

To ensure rigorous analysis, I implemented a complete statistical data pipeline in R:

### **1\. Data Engineering & Feature Creation**

* **Metric Formulation:** Engineered business-critical features such as tot\_conv (Total Conversions), total\_conval (Total Conversion Value), and ROAS (Return on Ad Spend) from raw enquiries and approved\_purchases data.  
* **Data Transformation:** Applied dummy encoding for categorical variables (Gender, Age brackets) to prepare them for regression modeling.

### **2\. Exploratory Data Analysis (EDA) & Inference**

* **Visual Analytics:** Utilized ggplot2 and GGally to map correlation matrices and visualize distributions of ad clicks vs. demographic segments.  
* **Hypothesis Testing:** Conducted foundational statistical inference to determine baseline significance between different ad campaigns and user engagement levels.

### **3\. Multiple Linear Regression (MLR) & Model Tuning**

* **Iterative Modeling:** Built multiple regression models targeting CPM (Cost Per Mille) and ROAS, starting from simple linear regression up to complex MLR.  
* **Best Subsets Selection:** Deployed the leaps package to automatically search through all possible combinations of predictors, identifying the optimal subset of variables that maximize the Adjusted R-squared.  
* **Model Diagnostics:** Evaluated multicollinearity using Variance Inflation Factors (VIF) via the car package to ensure feature independence.

### **4\. Model Comparison (ANOVA)**

* Conducted Analysis of Variance (ANOVA) to compare nested models (e.g., incrementally adding variables like interest, impr, Clicks, Spent).  
* Utilized F-statistics and p-values to scientifically justify the inclusion of each predictor, ensuring the final model is both parsimonious and highly predictive.

## **📈 Key Business Insights & Strategic Value**

1. **Engagement vs. Conversion:** While Impressions and Clicks are highly correlated with ad spend, their direct impact on final ROAS varies significantly across demographic segments.  
2. **Demographic Targeting:** Age and specific Interest categories serve as statistically significant modifiers for Conversion Value. Optimizing ad delivery towards these high-coefficient segments can drastically improve budget efficiency.  
3. **Model Efficacy:** The optimal model proved that combining behavioral metrics (Clicks, Spent) with demographic data provides a significantly better fit for predicting ad efficacy than behavioral data alone.

## **🛠️ Tech Stack**

* **Language:** R  
* **Data Manipulation:** tidyverse, dplyr, readxl  
* **Statistical Modeling:** stats, broom (model tidying), car (diagnostics), leaps (subset selection)  
* **Data Visualization:** ggplot2, GGally, DataExplorer

## **⚙️ Installation & Usage**

1. **Clone the repository:**  
   git clone

2. **Open in RStudio:**  
   * Open the ROAS\_Statistical\_Analysis.Rmd file in RStudio.  
   * Ensure you change the setwd() directory in the Rmd file to match your local project path.  
3. **Install Required R Packages:**  
   Run the following in your R console if you haven't installed them yet:  
   install.packages(c("tidyverse", "openintro", "broom", "GGally", "car", "leaps", "DataExplorer"))

4. **Knit or Run:**  
   * Click **Knit to HTML** in RStudio to generate the full interactive report with all EDA plots, ANOVA tables, and regression summaries.  
   * Or run chunks sequentially to explore the data interactively.
