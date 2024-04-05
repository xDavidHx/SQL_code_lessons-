**SQL_code_lesson**
Building a list of Current Skills Learned Within SQL and description of how they Work! 
Note: This is only practice with intent to learn the skill more effecively but Creating a SQL guide on Github & lesson will be un ordered


**Using DISTINCT:**
If DISTINCT is not used, then SQL will assume you're selecting ALL within your query. Here's an example of using DISTINCT with a data set
using covid_19 data. 
How to Use it: Use DISTINCT in the SELECT clause of your query that pulls the data from your database. 
Syntax: SELECT DISTINCT column FROM table

SELECT DISTINCT(Entity)
FROM dehproject24.Covid_19_Data.Covid_19_deaths_vs_Vaccination


**Using LIKE:**
Like is Used in the WHERE clause. It can use two wildcard operators '%' which searches multiple characters, or '_' to find a single character. 
Syntax: 
SELECT Column FROM Table WHERE COLUMN LIKE '%Name'
Or
SELECT Column FROM Table WHERE COLUMN LIKE 'N_am_'



Example: (Column called "Entity" from table 'dehproject24.Covid_19_Data.Covid_19_deaths_vs_Vaccination'

SELECT DISTINCT(Entity)
FROM dehproject24.Covid_19_Data.Covid_19_deaths_vs_Vaccination
WHERE Entity LIKE 'India%';

or 

SELECT DISTINCT(Entity)
FROM dehproject24.Covid_19_Data.Covid_19_deaths_vs_Vaccination
WHERE Entity LIKE 'Ind_a%';

