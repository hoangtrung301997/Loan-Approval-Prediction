# Loan Approval Prediction

## Understanding the Dataset

### Features 

1. person_age (int64)
2. person_income (int64)
3. person_home_ownership (object)
4. person_emp_length (float64)
5. loan_intent (object)
6. loan_grade (object)
7. loan_amnt (int64)
8. loan_int_rate (object)
9. loan_status (int64)
10. loan_percent_income (float64)
11. cb_person_default_on_file (object)
12. cb_person_cred_hist_length (int64)

### Data correlation 

![Heat map](image.png)

**Strong Positive Correlations:** *person_age* and *cb_person_cred_hist_length* (older people generally have longer credit history)

**Moderate Positive Correlation:** *loan_amnt* and *loan_percent_income* (People requesting larger loans to have a higher percentage of their income allocated to loan repayments)

**Weak Positive Correlation:** Most of them are weak

**Loan Status Correlation:** *loan_int_rate* and *loan_percent_income* have the strongest correlations with *loan_status*