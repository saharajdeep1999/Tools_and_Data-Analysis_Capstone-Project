Respiratory Virus Wastewater & Mortality Analysis
Project Overview
This project investigates the relationship between viral pathogen concentrations detected in wastewater and mortality rates from respiratory illnesses. By merging wastewater surveillance data with provisional mortality data, we employ rigorous statistical hypothesis testing to understand disease-mortality dynamics across COVID-19, Influenza, and RSV.
Objectives

Examine whether high viral concentrations in wastewater predict higher mortality rates
Identify disease-specific differences in mortality during high viral concentration periods
Determine associations between concentration levels and mortality severity categories
Provide evidence-based insights for public health surveillance and intervention planning

Data Sources
Two primary datasets are used in this analysis:

Respiratory_Virus_Wastewater_Surveillance.csv - Contains weekly average viral pathogen concentrations detected in wastewater samples, including Influenza A, Influenza B, SARS-CoV-2, RSV, and PMMOV
Provisional_Deaths_Due_to_Respiratory_Illnesses.csv - Contains provisional mortality data linked by week (MMWR) and disease type

Methodology
Data Preparation

Pathogen variants (Influenza A & B) are consolidated into single disease categories
Datasets are merged on MMWR week and disease classification
Missing or incomplete records are removed to ensure data quality
PMMOV (not linked to human mortality) is excluded from analysis

Statistical Approach
Hypothesis 1: High Viral Concentration Predicts Higher Mortality
Test: Independent samples t-test

H₀: No difference in mortality between high and low concentration weeks
H₁: High concentration weeks have significantly higher mortality
Method: Groups are created based on median concentration; mortality percentages are compared
Assumptions Verified: Normality (Shapiro-Wilk), Equal variances (Levene's test)
Effect Size: Cohen's d

Hypothesis 2: Disease-Specific Concentration-Mortality Relationship
Test: One-Way ANOVA

H₀: Mean mortality is equal across all disease types
H₁: At least one disease shows different mortality during high concentration
Method: High concentration weeks are stratified by disease (COVID-19, Influenza, RSV)
Assumptions Verified: Normality per group, Equal variances across groups

Hypothesis 3: Association Between Concentration and Mortality Severity
Test: Chi-Squared Test of Independence

H₀: Concentration level and mortality severity are independent
H₁: Concentration level and mortality severity are associated
Method: Mortality categorized as Low (≤1%), Moderate (1-3%), High (>3%)
Effect Size: Cramér's V
Cell Requirements: Minimum expected frequency ≥ 5 verified

Requirements
pandas
numpy
matplotlib
seaborn
scipy
Installation
bashpip install pandas numpy matplotlib seaborn scipy
Usage
Run the analysis script:
bashpython analysis_script.py
The script will:

Load both CSV datasets
Merge datasets on week and disease classification
Execute all three hypothesis tests with assumption verification
Display detailed statistical results and interpretations
Generate visualization outputs for each hypothesis

Output Files
The analysis produces the following outputs:

hypothesis1_results.png - Box plot and distribution histogram comparing mortality between high and low viral concentration weeks
hypothesis2_results.png - Box plot and bar chart with error bars showing disease-specific mortality differences
hypothesis3_results.png - Heatmap displaying the association between concentration and mortality severity categories

Console output includes comprehensive statistical reports with p-values, test statistics, effect sizes, and practical interpretations.
Key Findings Structure
For each hypothesis, the analysis provides:

Descriptive Statistics: Group means, standard deviations, and sample sizes
Assumption Verification: Results of normality and homogeneity tests
Statistical Test Results: Test statistics, p-values, degrees of freedom
Effect Sizes: Cohen's d (t-test), Cramér's V (chi-squared)
Statistical Decision: Whether to reject or fail to reject the null hypothesis at α = 0.05
Practical Interpretation: Real-world meaning of findings with numerical context

Significance Level
All statistical tests use α = 0.05 as the threshold for significance determination.
Author Notes
This analysis uses standard epidemiological and statistical methods to examine public health surveillance data. Results are intended to support understanding of pathogen-mortality relationships and inform evidence-based public health decision-making.
Disclaimer
This analysis is based on provisional mortality data and wastewater surveillance measurements. Interpretations should consider potential limitations in data collection, reporting delays, and the ecological nature of wastewater-based epidemiology.
