![alt text](https://github.com/marrr00/HR-Dashboard/blob/main/2023-06-07%20(2).png)

# HR-Dashboard
The project analyze employee distribution on the company using employee data from year 2000 to 2020. The dataset was cleaned and queried by SQL and visualized using google studio.

## Business case
The dashboard answering this business case
- What is the gender breakdown of employees in the company?
- How many employees work at headquarters versus remote locations?
- How does the gender distribution vary across departments?
- What is the distribution of employees across locations by state?


## Result summary
result summary 
from the analysisng of the data we found that 
- There are more male employees
- A large number of employees work at the headquarters versus remotely.
- The gender distribution across departments is fairly balanced but there are generally more male than female employees.
- A large number of employees come from the state of Ohio.


## Qyeries 
 ```mysql

                  
--- What is the gender breakdown of employees in the company?                                        
-- SELECT gender, COUNT(*) AS count
-- FROM hr
-- GROUP BY gender

-- - How many employees work at headquarters versus remote locations?
-- SELECT location, COUNT(*) as count
-- FROM hr
-- GROUP BY location;

-- - How does the gender distribution vary across departments?
select department ,sum(Male) as Male, sum(Female)as Female
 from 
(SELECT  department,COUNT(*) as Male, 0 as Female
FROM hr
where gender = 'Male'
GROUP BY department
union ALL
SELECT  department,0 as Male,COUNT(*) as Female
FROM hr
where gender = 'Female'
GROUP BY department
--ORDER BY department 
)
--where department = 'Services'
GROUP BY department 

--- What is the distribution of employees across locations by state?
-- SELECT location_state, COUNT(*) as count
-- FROM hr
-- GROUP BY location_state
-- ORDER BY count DESC;

```

## Tools
Google Data studio for visulaizing the data( an alternitive tool to Power BI)
SQLite (serverless database)
DB Browser 
