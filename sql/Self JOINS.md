
## Self JOINS


How to join a table with it self .

Because some times we have table LIKE employees table , and that table has a column of manager_id and that manager is actually an emplyee so he is in the same table .

So to query the the informations of the employees and their managers informations from this table we will use the SELF JOIN .


```sql
SELECT e.employee_id as 'Emplyee ID', e.first_name AS 'Employee First Name' , 
 m.first_name AS 'Manager First Name'
FROM employees e
JOIN employees m
ON e.reports_to = m.employee_id
```