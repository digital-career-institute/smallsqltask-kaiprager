# use existing employee table
Write a SQL query to find the average salary for each department and also include the total number of employees in each department. Display the results in descending order of the average salary.




SELECT d.department_id, d.department_name, COUNT(e.employee_id) AS total_employees,
		ROUND(AVG(e.salary), 2) AS average_salary FROM departments d
	LEFT JOIN employees e ON d.department_id = e.department_id
	GROUP BY d.department_id, d.department_name
	ORDER BY average_salary DESC;
