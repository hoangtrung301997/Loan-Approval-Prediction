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
9. loan_status (int64) 0 -> Yes, 1-> No
10. loan_percent_income (float64)
11. cb_person_default_on_file (object)
12. cb_person_cred_hist_length (int64)

### Data correlation 

![Heat map](image.png)

**Strong Positive Correlations:** *person_age* and *cb_person_cred_hist_length* (older people generally have longer credit history)

**Moderate Positive Correlation:** *loan_amnt* and *loan_percent_income* (People requesting larger loans to have a higher percentage of their income allocated to loan repayments)

**Weak Positive Correlation:** Most of them are weak

**Loan Status Correlation:** *loan_int_rate* and *loan_percent_income* have the strongest correlations with *loan_status*

### Missing Data

    *person_emp_length*: 895

    *loan_int_rate*: 3116

#### Possible reasons why it is missing

##### *person_emp_length*: Currently unemloyed, self-employed, irregular employment history, or mistake

Based on this discovery, I am going to set the person_emp_length that has a null value to 0, and the income came somewhere else other than working.

Here are some screenshots of person_emp_length and income

![alt text](image-1.png)

![alt text](image-2.png)


##### *loan_int_rate*: Loan not finalized, variable interest rates, data entry issues

This is a bit tricky so I wont be using any simple impution such as mean/median since loans with missing interest rates have a higher approval rate, filling in missing values with the average or median interest rate could underestimate the actual rates for those loans. For filling these missing data I am going to try and use KNN Imputer because it considers the values of similioar loans to estimate the missing interest rates.

Here are some screenshots of some of the findings that could have some correlation but maybe not 

![alt text](image-3.png)

![alt text](image-4.png)
