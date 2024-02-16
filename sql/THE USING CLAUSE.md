## THE USING CLAUSE

Using clause for one condition

In this query we get all customers with their orders date .
```sql
SELECT 
    c.first_name, o.order_date
FROM
    customers c
        LEFT JOIN
    orders o ON c.customer_id = o.customer_id

If we have the same field name LIKE ‘customer_id’ we can use keyword USING instead .
SELECT 
    c.first_name, o.order_date
FROM
    customers c
        LEFT JOIN
    orders o USING (customer_id)
```

**Using clause for two conditions**

In this example we will select the notes for our order items , each order item in the table has two primary keys , one for the order_id and second one for the product_id , wich make every cell unique with this two primary keys .
Well to pick our notes from order_item_notes table we will need to make two conditions to check if the order_id and product_id match .
Query :

SELECT 
    *
FROM
    order_items oi
		JOIN
    order_item_notes oin ON oi.order_id = oin.order_id
        AND oi.product_id = oin.product_id

Using the USING keyword instead , will be like :

SELECT 
    *
FROM
    order_items oi
        JOIN
    order_item_notes oin USING (order_id , product_id)