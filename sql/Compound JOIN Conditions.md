## Compound JOIN Conditions


In table order_item we have the items ordered with order_id and product_id

In table order_item_notes we have order_id and product_id with the note message

So this join with have two conditions .

```sql
SELECT * 
FROM order_items oi
JOIN order_item_notes oin
ON
oi.order_id = oin.order_id 
AND
oi.product_id = oin.product_id 
```

Implicit JOIN Syntax


The following syntax :

```sql
SELECT * 
FROM orders o
JOIN customers c
ON o.customer_id = c.customer_id
```

We can write it same as this syntax :

```sql
SELECT * 
FROM orders o , customers c
WHERE o.customer_id = c.customer_id
```