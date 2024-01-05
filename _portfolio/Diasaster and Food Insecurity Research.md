---
title: "Disaster and Food Insecurity (DataScience Foundations Project)"
excerpt: "The primary objective is to explore the relationship between the magnitude of disasters and the prevalence of food insecurity, as defined by the Food and Agriculture Organization (FAO). The research utilizes datasets from the EM-DAT Centre for Research on Epidemiology of Disasters and FAO's FAOSTAT. This repository contains the code and data for a research project investigating the impacts of natural disasters on food security."
---

Link to my GitHub Repository [Github Code](https://github.com/Likhitha-Veganti/data-science-projects/tree/main/Disaster%20and%20Food%20Insecurity).

## Introduction

Hunger is a global issue affecting millions of people. Food insecurity, defined by the FAO, is the lack of consistent access to adequate food supplies. Climate change, leading to increased natural disasters, can exacerbate food insecurity. This research aims to analyze the impact of disasters on food security, specifically the percentage of malnourishment, to anticipate and prepare for the consequences of disasters on affected populations.

## Dataset

The research relies on two main datasets:
1. **EMDAT Dataset:** Contains information on natural disasters worldwide, recorded by the EM-DAT Centre from 1900 to the present day.
2. **FAOSTAT Dataset:** Provided by the Food and Agriculture Organization, it includes global hunger metadata and indicators such as prevalence of undernourishment.

## Modeling

1. **Data Preprocessing:** The FAOSTAT dataset was transformed and merged with the EM-DAT dataset. Null values, especially in the disaster magnitude column, were imputed using MICE imputation, and the data was normalized using MinMaxScaler.
2. **Analytic Approach:** The research involved training various models, including CNN, random forest, linear regression, and multiple linear regression, to predict the impact of disasters on food insecurity.
3. **Results:** The models were evaluated using mean squared error, with CNN and random forest showing the best fit. Further analysis on specific disaster types (flood, storm, earthquake) revealed flood and storm to have a more significant impact on food insecurity.

## Conclusion

The research concludes that flood and storm disasters have a more substantial impact on food insecurity compared to earthquakes. The best-fitting models were found to be Random Forest and CNN, with mean squared errors of 0.00109 and 0.00430 for flood and storm, respectively.

## Repository Contents

1. **Datasets:**
   - `FOASTAT_data.csv`: Food insecurity dataset
   - `emdat.csv`: Disasters dataset
   - `final_normalized_data.csv`: Final dataset with normalized values of magnitude

2. **Code:**
   - `final_project.ipynb`: Colab notebook containing the analysis, modeling, and visualizations

3. **Visualizations:**
   - `visualizations.twb`: Tableau file with visualizations

4. **References:**
   - `references.txt`: Document containing all references and data sources

5. **Presentation:**
   - `Data_5100_Analysis_Project_Presentation.pdf`: Presentation slides summarizing the research findings

## Limitations

The research acknowledges limitations, including the influence of variables like war, COVID-19, and poverty on malnutrition. Additionally, recovery from food insecurity post-disaster depends on a country's resources.

## Resources

Useful links and resources for further understanding and context are provided in the references section.
