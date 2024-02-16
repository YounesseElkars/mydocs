## SELF OUTER JOINS

In this case we have a single table has list of employees and their managers id , the managers id are employees in the same table , and the employees that they dont have ids of manager are managers .
We want a list of all employees with their managers name or just the employees if they dont had managers 

```sql
SELECT
     e.employee_id,
     e.first_name,
     m.first_name as manager
FROM employees e
left JOIN employees m
ON e.reports_to = m.employee_id
```