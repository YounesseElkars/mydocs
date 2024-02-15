## The LIMIT CLAUSE



Get just 3 results
```sql
SELECT * FROM customers LIMIT 0, 3;
```

Get 3 results for the first page .
-- Page 1 , result from 1,2,3

```sql
SELECT * FROM customers LIMIT 0, 3;
```

Get 3 results for the second page .
-- Page 2 , result from 4,5,6
```sql
 SELECT * FROM customers LIMIT 3, 3;
```