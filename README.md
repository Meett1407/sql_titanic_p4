# sql_titanic_p4

## Project Overview

**Project Title**: Titanic Survival Analysis

**Level**: Beginner

This project is designed to apply SQL skills in analyzing the Titanic dataset, which includes data on passengers, their demographics, ticket classes, and survival outcomes. The project involves setting up a Titanic database, performing data cleaning, exploratory data analysis (EDA), and addressing questions related to survival rates using SQL queries. This project is ideal for beginners in data analysis who want to build a foundation in SQL with a classic dataset.

## Objectives

1. **Set Up the Titanic Database**: Create and populate a Titanic database with data on passengers, including their age, gender, ticket class, and survival status.
2. **Data Cleaning**: Identify and handle missing or null values, particularly in columns like age, cabin, and fare, to ensure data consistency for analysis.
3. **Exploratory Data Analysis (EDA)**: Perform basic EDA to understand the dataset’s characteristics, such as survival rates, distribution of passenger classes, and demographic breakdowns.
4. **Survival Analysis**: Use SQL to answer questions related to survival patterns, such as how gender, age, or ticket class influenced survival odds.

## Project Structure

### Data Analysis and Findings

The following SQL queries were developed to answer specific business questions:

**1. Select all columns for all passengers in the 
Titanic dataset.**
```sql
select * from titanic;
```

**2. Display the number of passengers in each class 
(1st, 2nd, 3rd).**
```sql
select pclass,count(passengerid) from titanic group by pclass;
```

**3. Find the number of male and female 
passengers.**
```sql
select sex,count(sex) from titanic group by sex;
```

**4. Display the names of passengers who survived.**
```sql
select name from titanic where Survived='survived';
```

**5. Find the average age of passengers.**
```sql
select avg(age) from titanic;
```

**6. List the names and ages of passengers who were younger than 18.**
```sql
select name,age from titanic where age<18;
```

**7. Display the number of passengers in each embarkation port (C, Q, S).** 
```sql
select embarked,count(passengerid) from titanic group by embarked;
```

**8. Find the highest fare paid by any passenger.** 
```sql
select max(fare) from titanic;
```

**9. List the average age of passengers for each class.**
```sql
select pclass,avg(age) from titanic group by pclass;
```

**10. Display the passenger names and ages for 
those who survived and were in 1st class.**
```sql
select name,age from titanic where Survived='survived' and Pclass=1;
```

**11. Find the number of passengers who paid more than 50 for their ticket.**
```sql
select count(*) from titanic where fare>50;
```

**12. List the names of passengers who did not 
survive and were in 3rd class.**
```sql
select name from titanic where Survived='died' and Pclass=3;
```

**13. Find the number of passengers with missing 
values in the "Age" column.**
```sql
select count(*) from titanic where age is null;
```

**14. Display the passenger names and ages for 
those who embarked at port 'S' and survived.**
```sql
select name,age from titanic where embarked='s' and survived='survived';
```

**15. Calculate the total number of passengers on board.**
```sql
select count(*) from titanic;
```

**16. List the average fare for each class.**
```sql
select pclass,avg(fare) from titanic group by pclass;
```

**17. Display the passenger names and ages for 
those with a known age and a fare greater than 
100.**
```sql
select name,age from titanic where age is not null and fare>100;
```

**18. Find the percentage of passengers who survived.**
```sql
select survived,count(survived),count(survived)/(select count(survived) from titanic)*100 as percentage
from titanic group by survived having survived='survived';
```

**19. List the names of passengers who were in 2nd 
class and had a fare less than 20.**
```sql
select name from titanic where pclass=2 and fare<20;
```

**20. Display the passenger names and ages for 
those who did not survive and were in 1st class.**
```sql
select name,age from titanic where survived='died' and pclass=1;
```

**21. Find the number of passengers for each combination of class and gender.**
```sql
select pclass,sex,count(sex) from titanic group by pclass,sex order by pclass;
```

**22. List the names of passengers who survived 
and were in 3rd class with an age less than 20.**
```sql
select name,survived,age,pclass from titanic where survived='survived' and pclass=3 and age<20;
```

**23. Display the passenger names for those with 
the name starting with 'Mr.'**
```sql
select name from titanic where name like '%Mr.%';
```

**24. Find the average age of male and female passengers.**
```sql
select sex,avg(age) from titanic group by sex;
```

**25. List the names of passengers who paid the highest fare.**
```sql
select name,fare from titanic where fare in(select max(fare) from titanic);
```

**26. Find the number of passengers for each embarkation port and class.**
```sql
select embarked,pclass,count(name) from titanic group by embarked,pclass order by embarked;
```

**27. Display the passenger names and ages for 
those who survived and paid more than 200 for 
their ticket.**
```sql
select name,age,fare from titanic where survived='survived' and fare>200;
```

**28. Find the average age of passengers who 
survived and those who did not.**
```sql
select survived,avg(age) from titanic group by survived;
```

**29. List the names of passengers who were in 1st 
class and had an age greater than 50.**
```sql
select name from titanic where pclass=1 and age>50;
```

**30. Display the passenger names for those with 
the name ending with 'sson'**
```sql
select name from titanic where name like '%sson';
```

## Findings

1. **Passenger Demographics**: Analysis of the demographics, including age, gender, and ticket class distribution, providing a profile of passengers aboard the Titanic.
2. **Survival Rates by Class and Gender**: Identification of survival rates by ticket class (1st, 2nd, 3rd) and gender, revealing how these factors impacted passengers' likelihood of survival.
3. **Family Impact on Survivale**: Analysis of the effect of family size (siblings/spouses, parents/children) on survival chances, identifying trends for passengers who traveled alone versus with family.
4. **Age and Survival**: Exploration of survival patterns by age group, providing insights into whether younger or older passengers had higher survival rates.

## Conclusion
This project provides a foundational SQL practice through data cleaning, EDA, and survival analysis of the Titanic dataset. The findings offer insights into how various demographic and socioeconomic factors impacted survival, helping build essential SQL skills while uncovering the historical and social dimensions of the Titanic tragedy.

## How to Use

1. **Clone the Repository**: Clone this project repository from GitHub.
2. **Set Up the Database**: Run the SQL scripts provided in the database_setup.sql file to create and populate the database.
3. **Run the Queries**: Use the SQL queries provided in the analysis_queries.sql file to perform your analysis.
4. **Explore and Modify**: Feel free to modify the queries to explore different aspects of the dataset or answer additional business questions.

## Author - Meet Limbani
This project is part of my portfolio, showcasing the SQL skills essential for data analyst roles. If you have any questions, feedback, or would like to collaborate, feel free to get in touch!

### Stay Updated and Join the Community
For more content on SQL, data analysis, and other data-related topics, make sure to follow me on social media and join our community:

- **LinkedIn**: [Connect with me professionally](https://www.linkedin.com/in/meet-limbani-6258bb285/)

Thank you for your support, and I look forward to connecting with you!
