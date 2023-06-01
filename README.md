# HR-Dashboard
The project analyze employee distribution on the company using employee data from year 2000 to 2020. The dataset was cleaned and queried by SQL and visualized using google studio.

## Business case
the dashboard answering this business case
- What is the gender breakdown of employees in the company?
- How many employees work at headquarters versus remote locations?
- How does the gender distribution vary across departments and job titles?
- What is the distribution of job titles across the company?
- What is the distribution of employees across locations by state?


## Result summary
result summary 
from the analysisng of the data we found that 
1-There are more male employees
2-White race is the most dominant while Native Hawaiian and American Indian are the least dominant.
5-A large number of employees work at the headquarters versus remotely.
6-The average length of employment for terminated employees is around 7 years.
7-The gender distribution across departments is fairly balanced but there are generally more male than female employees.
9-A large number of employees come from the state of Ohio.
10The net change in employees has increased over the years.
11-The average tenure for each department is about 8 years with Legal and Auditing having the highest and Services, Sales and Marketing having the lowest.


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

-- - How does the gender distribution vary across departments and job titles?
-- SELECT department, gender, COUNT(*) as count
-- FROM hr
-- GROUP BY department, gender
-- ORDER BY department;

--- How does the gender distribution vary across departments and job titles?
select jobtitle, max(count) Max_jobtitle
-- , min(count) min_jobtitle
from(
SELECT jobtitle, COUNT(*) as count
FROM hr
GROUP BY jobtitle
ORDER BY jobtitle DESC);

--- What is the distribution of employees across locations by state?
-- SELECT location_state, COUNT(*) as count
-- FROM hr
-- GROUP BY location_state
-- ORDER BY count DESC;

```
