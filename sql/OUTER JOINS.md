## OUTER JOINS



This JOIN statement will return for us just the customers with orders , we will not have the rest of customers with no orders  .

```sql
SELECT o.order_id , c.customer_id , c.first_name
FROM orders o
JOIN customers c
ON o.customer_id = c.customer_id
```

If we want to have those customers with no orders also we will use the OUTER JOIN .

OUTER JOIN has two types RIGHT JOIN and LEFT JOIN 

**LEFT JOIN :** when we use it all the records from the left table wich is table orders  are returned whether the condition is true or not  .

**RIGHT JOIN :** when we use it all the records from the right table wich is table customers  are whether weither the condition is true or not  .

So to get all the customers with their orders whether they had orders or not we write this syntax :

```sql
SELECT c.customer_id , c.first_name , o.order_id 
FROM orders o
RIGHT JOIN customers c
ON o.customer_id = c.customer_id
ORDER BY c.customer_id
```

PS :  we can use this code 
RIGHT OUTER JOIN customers c 
just LIKE the INNER keyword , the OUTER Keyword is  optional