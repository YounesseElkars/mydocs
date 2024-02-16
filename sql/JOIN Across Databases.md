## JOIN Across Databases


First we had to specify the default database with USE sql_store; 
Then  for the table from outside  we prefix it with database name LIKE :

> sql_inventory.products


```sql
USE sql_store;

SELECT  order_id , o.product_id  , name , quantity , o.unit_price
FROM order_items o
JOIN sql_inventory.products p
ON o.product_id = p.product_id
```