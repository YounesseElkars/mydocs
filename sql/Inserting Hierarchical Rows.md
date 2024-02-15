## Inserting Hierarchical Rows 

Inserting data in multiple tables  , having parent-child relationship 


For example of parent-child relationship , we have an orders table and order_items table .
When an order happens we insert first our order details , then when the order is created we get the id of the order to insert it , in the child table order_items that will have the id of this order and product details , amount , and unit_price .

Query :

```sql
INSERT INTO orders (customer_id , order_date , status )
VALUES ( 6 , '2023-11-19' , 1);
INSERT INTO order_items 
VALUES (LAST_INSERT_ID() , 4 , 4 , 3 ),
	   (LAST_INSERT_ID() , 2 , 1 , 6 );
```