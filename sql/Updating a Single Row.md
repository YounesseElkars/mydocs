## Updating a Single Row 

**Query for updating single row**

```sql
UPDATE invoices 
SET 
    payment_total = 10,
    payment_date = '2023-01-01'
WHERE
    invoice_id = 1
```

**Updating Multiple Rows**

```sql
UPDATE invoices 
SET 
    payment_total = 10,
    payment_date = '2023-01-01'
WHERE
    client_id IN (3, 5)
```