## THE SELECT Clause SubQueries

Find employees whose salary is greater than the average salary.


```sql
SELECT employee_name, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

Find names of all employee who have sold over 30k to a single client 

```sql
SELECT emp_id first_name, last_name 
FROM employee 
WHERE emp_id IN (SELECT emp_id 
                     FROM works_with 
                    WHERE total_sa
                    30000 );
```

Find all clients who are handled by the branch that micheal scott manages , assume you know micheal's id :

```sql
SELECT client_id, client_name 
FROM client WHERE branch_id = (  SELECT branch_id 
                                 FROM branch 
                                 WHERE mgr_id = 102 LIMIT 1);
```