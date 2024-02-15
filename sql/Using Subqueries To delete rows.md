
## Using Subqueries To delete rows 

Using subquery to delete a record :

```sql
DELETE FROM invoices 
WHERE
    client_id = (SELECT 
        client_id
    FROM
        clients
    WHERE
        name = 'Myworks')
```