## Using Subqueries to update rows 

In this query we update a record based on client_id that we will get based on the name of the client .

```sql
UPDATE invoices 
SET 
    payment_total = 10,
    payment_date = '2023-01-01'
WHERE
    client_id = (SELECT 
            client_id
        FROM
            clients
        WHERE
            name = 'Myworks')

```

We can also get many IDS from table client and update table invoices like this :


```sql
UPDATE invoices 
SET 
    payment_total = 10,
    payment_date = '2023-01-01'
WHERE
    client_id IN (SELECT 
            client_id
        FROM
            clients
        WHERE
            state IN ('CA' , ' NY'))
```