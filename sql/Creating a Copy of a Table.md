## Creating a Copy of a Table 

When we create a table using this technique , we will have the same as the first table with the same datatypes and stuff but mysql will ignore artibutes like PRIMARY_KEY , AUTO_INCREMENT .
Query  :
```sql
CREATE TABLE orders_archived AS SELECT * FROM
    orders;
```
Second method :

We will use another method , with INSERT INTO and SELECT FROM .

Query :

```sql
INSERT INTO orders_archived
SELECT * 
FROM orders 
WHERE order_date < '2019-01-01'
```

