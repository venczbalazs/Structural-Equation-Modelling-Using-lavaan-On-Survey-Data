# Structural Equation Modelling with lavaan and Survey Data

This repository contains R scripts for analysing institutional trust in Germany, Hungary, and Poland using European Social Survey (ESS) Round 11 data. The workflow covers data preparation, model fitting, and the export of tables and figures.

## How the scripts are organised

1. **Data cleaning.** The first script imports the ESS data, selects the three countries, converts survey-specific missing-response codes to missing values, and reverses selected scales. It also prepares the survey weights and recodes the control variables used later in the analysis.

2. **Confirmatory factor analysis.** The second section of the same script uses the cleaned data to fit country-specific models of institutional trust. It reports model summaries and checks whether the models converged.

3. **Structural equation models without controls.** A separate script uses the prepared data to fit and compare models across the three countries. Each model is saved under a distinct name so its results can be inspected alongside earlier fits.

4. **Structural equation models with controls.** The final modelling script combines the country-specific education variables and standardises age, education, and political interest within each country. It extracts regression estimates from the fitted models and uses them to create two coefficient plots.

An optional descriptive statistics script summarises the variables used in the analysis. It applies the same weighted summary to each country and exports the results to an Excel workbook with one worksheet per country.

## Input and outputs

The input is the ESS Round 11 CSV, available from the [ESS Data Portal](https://ess.sikt.no/en/). The cleaning script needs to point to the local copy of that file. The analysis uses dplyr for data preparation, lavaan for model fitting, ggplot2 for figures, and writexl for Excel export.

The main outputs are model summaries in R, two PNG figures comparing regression estimates across countries, and the optional Excel workbook.
