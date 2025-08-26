#### sql_repo
#### Find the total salary by department, but split it into salaries above 100,000 and below 100,000

SELECT 
		d.department_name,
		SUM(CASE WHEN e.salary >= 100000 THEN e.salary ELSE 0 END) AS high_salaries,
    	SUM(CASE WHEN e.salary < 100000 THEN e.salary ELSE 0 END) AS low_salaries
FROM employees e
JOIN departments d
ON e.department_id = d_department_id
GROUP BY d.department_name;
***Note that i am using MYSQL Workbench***
#### But i am geeting this error which say error code 1053, Unknown unknown column d.department id in on clause
#### Mean while, i have used DESCRIBE table_name to know if i mispellt any of the column name but it was correct and still getting this error
