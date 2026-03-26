# Full research summary

### Research Rationale
Caused by fat buildups in blood vessels, CAD is naturally assumed to be closely correlated with the blood cholesterol level. Specifically, one cholesterol named low-density lipoprotein (LDL) is often considered “bad” and the main cause of CAD due to its large volume. In contrast, another cholesterol named high-density lipoprotein (HDL) is usually assumed “good” as it takes up less space in blood vessels. However, is this assumption the truth?

### Research Question
Do HDL and other cholesterols influence the risk of coronary artery disease?

### Hypothesis
A lower HDL level in blood vessels is associated with a higher risk of developing CAD.

### Data Source
National Health and Nutrition Examination Survey (NHANES): https://www.cdc.gov/nchs/nhanes/index.html
I analyzed 9 datasets spanning 2021 to 2023, specifically: "Cholesterol - High-Density Lipoprotein," "Medical Conditions," and "Demographics Data." The original data were obtained from a longitudinal survey of over 10,000 participants.

### Data Cleaning
The datasets were then merged into a new dataset based on the shared column “Respondent Sequence Number (SEQN).” In the new dataset, each row corresponded to a participant, and the columns included “SEQN,” “gender (RIAGENDR),” “age in years at screening (RIDAGEYR),” “direct HDL-cholesterol in mg/dL (LBDHDD),” “total cholesterol in mg/dL (LBXTC),” “ever told you had coronary heart disease (MCQ160C),” and “taking meds to lower blood cholesterol? (BPQ101D).” 

### Methods
3 mutiple logistic regression tests: 
1) MCQ160C ~ RIAGENDR + RIDAGEYR + LBDHDD + BPQ101D (HDL on CAD)
2) MCQ160C ~ RIAGENDR + RIDAGEYR + LBXTC + BPQ101D (all types of cholesterol on CAD)
3) MCQ160C ~ RIAGENDR + RIDAGEYR + LBDHDD + LBXTC + BPQ101D (CAD & all types of cholesterol on CAD)

The purpose of 3) is to adjust for the correlation between HDL and total cholesterol.
