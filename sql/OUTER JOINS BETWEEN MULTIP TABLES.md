## OUTER JOINS BETWEEN MULTIP TABLES

In this example we are seeking 
Firstname and id from customer table
Order id from orders table
And shipper name from shippers table
With all customers even if they dont have orders


```sql
SELECT c.customer_id , c.first_name , o.order_id  , s.name as 'shipper'
FROM customers c
LEFT JOIN orders o
ON o.customer_id = c.customer_id
LEFT JOIN shippers s
ON o.shipper_id = s.shipper_id
ORDER BY c.customer_id
```