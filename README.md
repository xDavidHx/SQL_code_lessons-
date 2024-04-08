**Intermediate_SQL_code_lessons**
Building a list of Current Skills Learned Within SQL and description of how they Work! 
Note: This is only practice with intent to learn the skill more effecively but Creating a SQL guide on Github & lesson will be unordered. All names, tables, and columns were used from opensourced origins like Kaggle, and Data.world. 
---------------------


**Using DISTINCT:**
If DISTINCT is not used, then SQL will assume you're selecting ALL within your query. Here's an example of using DISTINCT with a data set
using covid_19 data. 

How to Use it: Use DISTINCT in the SELECT clause of your query that pulls the data from your database. 
Syntax: SELECT DISTINCT column FROM table

**Example** 
```
SELECT
	 DISTINCT(Entity)
FROM
	dehproject24.Covid_19_Data.Covid_19_deaths_vs_Vaccination
```
---------------------

***Using COUNT & DISTINCT***   
Using the same Dataset and table from the previous example, you can use SELECT and DISTINCT to find all unique identifyers in your table without getting duplicates. The COUNT clause is placed into the query to provide a count of how many times the table attribute is listed withi the table. 

**Example** 
```
Select
	COUNT(DISTINCT(Entity)) AS distinct_entities, Entity, 
FROM
	dehproject24.Covid_19_Data.Covid_19_deaths_vs_Vaccinations
Group by entity 
ORDER BY entity DESC
```
---------------------


**Using COUNT**
In a table called "Student_stud_data" we have the columns GRADE(A,B, C,D,F) and SCHOOL_LEVEL (K-8 School, Middle_school, High_school. 
**Example**
If we wanted to find the number of each letter grade received in the High_school column, we would type out this SQL query: 

```
SELECT
	SCHOOL_LEVEL_, GRADE, COUNT(GRADE) AS num_of_grades
FROM
	dehproject24.student_study_data.student_study_data
WHERE
	SCHOOL_LEVEL_ = "High School"
		GROUP BY SCHOOL_LEVEL_, GRADE
		ORDER BY GRADE
```


---------------------
**Using LIKE:**
Like is Used in the WHERE clause. It can use two wildcard operators '%' which searches multiple characters, or '_' to find a single character. 

Syntax: 

```
SELECT
	Column
FROM
	Table
WHERE
	COLUMN LIKE '%Name' (To search for terms that end in the desired "Name")
```
Or
```
SELECT
	Column
FROM
	Table
WHERE COLUMN LIKE 'N_m_' (To search for names with more distinct spelling conventions where you already know some of the spelling of the name) 
```
**Example: (Column called "Entity" from table 'dehproject24.Covid_19_Data.Covid_19_deaths_vs_Vaccination'**

```
SELECT 
	DISTINCT(Entity)
FROM
	dehproject24.Covid_19_Data.Covid_19_deaths_vs_Vaccination
WHERE
	Entity LIKE 'India%';
```
or
```
SELECT 
	DISTINCT(Entity)
FROM 
	dehproject24.Covid_19_Data.Covid_19_deaths_vs_Vaccination
WHERE 
	Entity LIKE 'Ind_a%';
```
---------------------
**Using ORDER BY**
"GROUP BY does NOT sort data, but ORDER BY DOES"
You can order by your aliased names/have your aliased names in your ORDER BY statement. 

---------------------
**Using 'AND' & 'NOT' operators**
```
Select
	Entity, code, continent
FROM
	dehproject24.Covid_19_Data.Covid_19_deaths_vs_Vaccinations**
WHERE
	NOT Entity = 'United States' AND NOT Entity = 'Japan' AND NOT Entity = 'Afghanistan' AND NOT code IS NULL
```

---------------------
**Using nested Statements within the "WHERE" clause**
Using a table named 'students' with the columns (name, dept and score) 

```
SELECT 
	dept
FROM 
	students	
WHERE 
	score > (

	SELECT MAX(score) 
	FROM students
	WHERE dept = ‘ECE’
               )
```
