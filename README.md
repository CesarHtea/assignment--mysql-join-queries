# MySQL JOIN Queries

Instructions: https://github.com/muktek/assignment--mysql-join-queries

Workplace: 45.55.135.14/phpmyadmin

##1 Write a query to get the department name and number of employees in the department.

```
SELECT E.DEPARTMENT_ID , D.DEPARTMENT_NAME , COUNT(*)
FROM Employees E
INNER JOIN Departments D
ON E.DEPARTMENT_ID = D.DEPARTMENT_ID
GROUP BY E.DEPARTMENT_ID;
```

##2 Write a query to find the employee ID, job title, number of days between ending date and starting date for all jobs in department 90 from job history.

```
SELECT E.EMPLOYEE_ID, J.JOB_TITLE , DATEDIFF(H.END_DATE, H.START_DATE) AS DAYSBETWEEN
FROM Employees E
INNER JOIN Jobs J
ON E.JOB_ID = J.JOB_ID 
INNER JOIN JobHistory H
ON J.JOB_ID = H.JOB_ID
WHERE H.DEPARTMENT_ID = 90 ;
```

##3 Write a query to display the department ID and name and first name of manager.

```
SELECT D.DEPARTMENT_ID, E.FIRST_NAME FROM Departments D
INNER JOIN Employees E
ON D.MANAGER_ID = E.EMPLOYEE_ID; 
```

##4 Write a query to display the department name, manager name, and city.

```
SELECT D.DEPARTMENT_NAME AS DEPARTMENT, E.FIRST_NAME AS MANAGER, L.CITY FROM Departments D
INNER JOIN Employees E
ON D.MANAGER_ID = E.EMPLOYEE_ID
INNER JOIN Locations L
ON D.LOCATION_ID = L.LOCATION_ID;
```

#5 Write a query to display the job title and average salary of employees.

#6 Write a query to display job title, employee name, and the difference between salary of the employee and minimum salary for the job.

#7 Write a query to display the job history that were done by any employee who is currently drawing more than 10000 of salary.

#8 Write a query to display department name, name (first_name, last_name), hire date, salary of the manager for all managers whose experience is more than 15 years.
```
