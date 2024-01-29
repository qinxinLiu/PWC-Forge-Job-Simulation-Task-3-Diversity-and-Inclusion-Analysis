# PWC Forge Job Simulation Task 3 : Diversity and Inclusion Analysis
## 1. Problem Statement

Human Resources at our telecom client is highly into diversity and inclusion. They’ve been working hard to improve gender balance at the executive management level, but they’re not seeing any progress. They’re reaching out to us for help.

Companies need a workforce of diverse talents and backgrounds to succeed in an increasingly complex and heterogeneous world. To us, diversity and inclusion are business imperatives, not just nice-to-haves

Tasks:

- Define relevant KPIs in hiring, promotion, performance and turnover, and create a visualisation

- Write what you think some root causes of their slow progress might be

## 2. Data Preprocessing and Modelling

- Removing duplicates
- Filling null values with 0
  
## 3. Create Measures (DAX)

**1.	# of men**

`- CALCULATE(COUNT('Pharma Group AG'[Gender]), 'Pharma Group AG'[Gender] = "Male")`


**2.	# of women**

`- CALCULATE(COUNT('Pharma Group AG'[Gender]), 'Pharma Group AG'[Gender] = "Female")`


**3. of leavers**

`- CALCULATE(COUNT('Pharma Group AG'[F20 Leavers]), 'Pharma Group AG'[F20 Leavers] = "Yes")`


**4. % employees promoted (FY21)**

`- DIVIDE(CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]), 'Pharma Group AG'[Promotion in FY21?] = "Yes"),500, 0)`


**5. % of women promoted**

`- DIVIDE(CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]),'Pharma Group AG'[Gender] = "Female",'Pharma Group AG'[Promotion in FY21?]="Yes"), 'Pharma Group AG'[Female Count], 0)`


**6. % of Promoters who were women**

`- DIVIDE(CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]),'Pharma Group AG'[Gender] = "Female",'Pharma Group AG'[Promotion in FY21?]="Yes"), 'Pharma Group AG'[numPromoters], 0)`


**7. % of men promoted**

`- DIVIDE(CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]),'Pharma Group AG'[Gender] = "Male",'Pharma Group AG'[Promotion in FY21?]="Yes"), 'Pharma Group AG'[Male Count], 0)`


**8. % of Promoters who were men**

`- DIVIDE(CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]),'Pharma Group AG'[Gender] = "Male",'Pharma Group AG'[Promotion in FY21?]="Yes"), 'Pharma Group AG'[numPromoters], 0)`


**9.	% of hires men**

`- numNewHires = CALCULATE(COUNT('Pharma Group AG'[New hire FY20?]),'Pharma Group AG'[New hire FY20?] = "Y")`

`- % of hires men = DIVIDE(CALCULATE(COUNT('Pharma Group AG'[New hire FY20?]), 'Pharma Group AG'[New hire FY20?]="Y", 'Pharma Group AG'[Gender]="Male"), 'Pharma Group AG'[numNewHires], 0)`


**10.	% of hires women**

`-  DIVIDE(CALCULATE(COUNT('Pharma Group AG'[New hire FY20?]), 'Pharma Group AG'[New hire FY20?]="Y", 'Pharma Group AG'[Gender]="Female"), 'Pharma Group AG'[numNewHires], 0)`


**11.	% turnover rate**

`- DIVIDE(CALCULATE(COUNT('Pharma Group AG'[In base group for turnover FY20]),'Pharma Group AG'[In base group for turnover FY20]="N"), 500, 0)`


**12. % men turnover**

`- = DIVIDE(CALCULATE(COUNT('Pharma Group AG'[In base group for turnover FY20]),'Pharma Group AG'[In base group for turnover FY20]="N", 'Pharma Group AG'[Gender]="Male"), 'Pharma Group AG'[Male Count], 0)`


**13. % women turnover**

`- DIVIDE(CALCULATE(COUNT('Pharma Group AG'[In base group for turnover FY20]),'Pharma Group AG'[In base group for turnover FY20]="N", 'Pharma Group AG'[Gender]="Female"), 'Pharma Group AG'[Female Count], 0)`



**14.	Average performance rating: men**

o	F19

`- avgMen_PR_FY19 = DIVIDE(CALCULATE(SUM('Pharma Group AG'[FY19 Performance Rating]), 'Pharma Group AG'[Gender]="Male"), 'Pharma Group AG'[Male Count],0)`

o	F20

`- avgMen_PR_FY20 = DIVIDE(CALCULATE(SUM('Pharma Group AG'[FY20 Performance Rating]), 'Pharma Group AG'[Gender]="Male"), SUM('Pharma Group AG'[FY20 Performance Rating]),0)`


**15.	Average Performance rating: women**

o	F19

`- avgWomen_PR_FY19 = DIVIDE(CALCULATE(SUM('Pharma Group AG'[FY19 Performance Rating]), 'Pharma Group AG'[Gender]="Female"), SUM('Pharma Group AG'[FY19 Performance Rating]),0)`

o	F20

`- avgWomen_PR_FY20 = DIVIDE(CALCULATE(SUM('Pharma Group AG'[FY20 Performance Rating]), 'Pharma Group AG'[Gender]="Female"), SUM('Pharma Group AG'[FY20 Performance Rating]),0)`

`- avgMen_PR_FY20 = DIVIDE(CALCULATE(SUM('Pharma Group AG'[FY20 Performance Rating]), 'Pharma Group AG'[Gender]="Male"), SUM('Pharma Group AG'[FY20 Performance Rating]),0)`


**16.	# of Executive**

`- numExecutive20 = CALCULATE(COUNT('Pharma Group AG'[Job Level after FY20 promotions]), 'Pharma Group AG'[Job Level after FY20 promotions]= "1 - Executive")`

`- numExecutive20 = CALCULATE(COUNT('Pharma Group AG'[Job Level after FY20 promotions]), 'Pharma Group AG'[Job Level after FY21 promotions]= "1 - Executive")`



## 4. Power BI Dashboard

<img width="1153" alt="截屏2024-01-29 17 39 38" src="https://github.com/qinxinLiu/PWC-Forge-Job-Simulation-Task-3-Diversity-and-Inclusion-Analysis/assets/67852322/2e3a6e5b-14ce-4034-9a4a-47be111b70d8">

<img width="1159" alt="截屏2024-01-29 17 39 49" src="https://github.com/qinxinLiu/PWC-Forge-Job-Simulation-Task-3-Diversity-and-Inclusion-Analysis/assets/67852322/b69c0af8-bd06-4864-bfd5-2a86b3ee3320">

<img width="1174" alt="截屏2024-01-29 17 40 11" src="https://github.com/qinxinLiu/PWC-Forge-Job-Simulation-Task-3-Diversity-and-Inclusion-Analysis/assets/67852322/305afe3c-ed32-4cfc-beb4-fc666aad3840">

## 5. Insights
