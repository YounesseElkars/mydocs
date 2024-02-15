## Inserting a Single Row 

**Query 1 :**
We can skip the deafult and null values by typing DEFAULT and NULL
```sql
INSERT INTO customers
VALUES ( DEFAULT , 'john', 'doe', '1990-01-01', NULL, 'address', 'city', 'BA',DEFAULT )
```

**Query 2 :**
we can optionaly insert list of columns names  , and we dont have to specify default and null values

```sql
INSERT INTO customers 
(first_name , last_name , birth_date , address , city , state ) 
VALUES ( 'mark', 'marlous', '1990-01-01', 'address', 'city', 'BA' )
```