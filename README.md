# 0-to-hero-sql-practice

Question 1: Write an SQL query to select all columns from a table named "employees".
```
select * from employees;
```

Question 2: Write an SQL query to select the "name" and "salary" columns from the "employees" table where the salary is greater than 50000.

```
select name, salary
from employees
where salary > 50000;
```

Question 3: Write an SQL query to count the total number of employees in the "employees" table.
```
SELECT count(*) 
FROM employees;
```

Question 4: Write an SQL query to find the highest salary among all employees in the "employees" table.
```
select max(salary)
from employees;
```
Question 5: Write an SQL query to select distinct job titles from the "employees" table.
```
SELECT DISTINCT(title) 
FROM employees;
```
Question 6: Write an SQL query to find the average salary of employees in the "employees" table.
```
SELECT AVG(salary)
FROM employees;
```
Question 7: Write an SQL query to select the top 5 highest paid employees from the "employees" table, ordered by salary in descending order.
```
SELECT salary 
FROM employees 
ORDER BY salary DESC 
LIMIT 5;
```
Question 8: Write an SQL query to find the second highest salary in the "employees" table.
```
SELECT salary
FROM employees
ORDER BY salary DESC
OFFSET 1
LIMIT1;
```
> OFFSET 1: Skips the first row, i.e., the highest salary.

Question 9: Write an SQL query to find the employees whose salary is within the range of $40,000 and $60,000.
```
SELECT employee, salary
FROM employees
where salary >= 40000 AND salary <= 60000;
```
Question 10: Write an SQL query to find the employees who joined the company in the year 2023.
```
SELECT SUM(salary)
from employees;
```
question 11: Write an SQL query to find the employees who joined the company in the year 2023.
```
SELECT employee
FROM employees
WHERE YEAR(join_date) = 2023;
```
Question 12: Write an SQL query to find the employees who have a salary greater than the average salary of all employees.
```
SELECT employee, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
Question 13 : Write an SQL query to find the department with the highest average salary.
```
SELECT department, AVG(salary) as avg_salary
FROM employees
GROUP BY department
ORDER BY avg_salary DESC
LIMIT 1;
```
Question 14: Write an SQL query to find the employees who have the same salary as the highest-paid employee.
```
SELECT employee
FROM employees
where salary = (SELECT MAX(salary) from employees);
```
Question 15: Write an SQL query to find the employees who have been with the company for more than 5 years. Assume there's a column named "join_date" in the "employees" table representing the date when each employee joined the company.
```
SELECT employee
FROM employees
WHERE DATEDIFF(CURRENT_DATE(), join_date) / 365 > 5;
```
