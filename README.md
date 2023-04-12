# Predicting the Survival of Bone Marrow Transplantation Patients

This is a data science project that looks at the survival of pediatric patients after receiving bone marrow transplants as therapy for several hematologic diseases. The aims of the project are to first, identify the most important factors that influence the survival of patients post-transplantation and second, to build machine learning models in order to ascertain the ability of these factors to predict survival. 

## Dataset Description

This dataset is taken from the UCI Machine Learning Repository, and can be found here: https://archive.ics.uci.edu/ml/datasets/Bone+marrow+transplant%3A+children. 

This data was collected by researchers studying the long-term survival of children after receiving hematopoietic stem cell transplantation. There were two main focuses of the study: 1. compare the results of transplantation from peripheral blood stem cells and bone marrow, 2. analyze the impact of CD34+ and CD3+ cell doses in the grafts. 

The data comprises data from 187 pediatric patients, with 37 attributes overall. These attributes contain information relating to the transplant donor and patient's ages, the type of disease that the patient has, the characteristics of the match between donor and patient, the CD34+ and CD3+ cell doses, recovery statistics, and whether the patient survived.

Below is an overview of the variables included in the dataset:

- **donor_age:** age of the donor at the time of donation
- **donor_age_below_35:** whether the donor is younger than 35 years (yes, no)
- **donor_ABO:** blood type of the donor (O, A, B, AB)
- **donor_CMV:** whether cytomegalovirus infection is present in donated stem cells (present, absent)
- **recipient_age:** age of recipient at the time of transplantation
- **recipient_age_below_10:** whether the recipient is younger than 10 years (yes, no)
- **recipient_age_int:** age of the recipient discretized into intervals (0,5], (5, 10], (10, 20]
- **recipient_gender:** gender of the recipient (female, male)
- **recipient_body_mass:** body mass of the recipient at the time of the transplantation
- **recipient_ABO:** blood type of the recipient (O, A, B, AB)
- **recipient_rh:** recipient's Rh status (plus, minus)
- **recipient_CMV:** whether cytomegalovirus infection is present in donated stem cells (present, absent)
- **disease:** type of disease (ALL, AML, chronic, nonmalignant, lymphoma)
- **disease_group:** nature of disease (malignant, nonmalignant)
- **gender_match:** - compatibility of the donor and recipient according to their gender (female to male, other)
- **ABO_match:** compatibility of blood types of donor and recipient (matched, mismatched)
- **CMV_status:** serological compatibility of donor and recipient according to cytomegalovirus infection status
- **HLA_match:** compatibility of donor and recipient antigens (10/10, 9/10, 8/10, 7/10)
- **HLA_mismatch:** HLA matched or mismatched
- **antigen:** number of differences of antigens between donor and recipient (0-3)
- **allel:** number of differences in alleles between donor and recipient (0-4)
- **HLA_group_1:** the difference type between the donor and the recipient (HLA matched, one antigen, one allel, DRB1 cell, two allele or allel+antigen, two antigenes+allel, mismatched)
- **risk_group:** risk group (high, low)
- **stem_cell_source:** source of hematopoietic stem cells (peripheral blood, bone marrow)
- **tx_post_relapse:** whether this is the second bone marrow transplantation after relapse (yes ,no)
- **CD34_x1e6_per_kg:** CD34+ cell dose per kg of recipient body weight (10^6/kg)
- **CD3_x1e8_per_kg:** CD3+ cell dose per kg of recipient body weight (10^8/kg)
- **CD3_to_CD34_ratio:** CD3+ cell to CD34+ cell ratio
- **ANC_recovery:** time in days to neutrophils recovery, defined as neutrophils count >0.5 x 10^9/L
- **PLT_recovery:** time in days to platelet recovery, defined as platelet count >50000/mm3
- **acute_GvHD_II_III_IV:** development of acute graft versus host disease stage II or III or IV (yes, no)
- **acute_GvHD_III_IV:** development of acute graft versus host disease stage III or IV (yes, no)
- **time_to_acute_GvHD_III_IV:** time in days to development of acute graft versus host disease stage III or IV
- **extensive_chronic_GvHD:** development of extensive chronic graft versus host disease (yes, no)
- **relapse:** relapse of the disease (yes, no)
- **survival_time:** time of observation (if alive) or time to event (if dead) in days
- **survival_status:** survival status (0 - alive, 1 - dead)

## Included Files

**1. Prepare_Data.ipynb:** Converts data file from original format (arff) to csv. Contains simple pre-processing of data to transform it into a usable format.\
**2. EDA.ipynb:** Contains visualizations for exploratory data analysis.\
**3. Data_Pre_Processing_and_Feature_Selection.ipynb:** Performs pre-processing on data and some feature selection methods:LASSO, Tree Based Model Feature Importance, SelectKBest. Feature selection found that the most important variables were related to survival time, relapse, CD34+ & CD3+ cell doses, development of graft versus host disease (GvHD), and donor/recipient characteristics.\
**4. Predictive_Models:** Contains predictive models made from full and reduced dataset (from feature selection). Models include: Logistic Regression, Decision Tree Classifier, Random Forest Classifier, XGBoost. The employed models were generally quite successful, with models using the reduced dataset as an input often performing better, showing that the reduced set of variables are powerful enough to predict survival accurately. This demonstrates the importance of these variables in determining a patient's health.
