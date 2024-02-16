## JOINING Multiple Tables

We have the table orders that have orders list with customer id from customer table
And status id from status table .

So we will join this two tables with order table and get order_id , order_date , first and last name of customer , and staus name .

```sql
SELECT o.order_id , o.order_date , c.first_name , c.last_name , os.name as 'status'
FROM orders o
JOIN customers c
ON o.customer_id = c.customer_id
JOIN order_statuses os
ON o.status = os.order_status_id
ORDER BY status , order_id
```