The SELECT Clause

**Selecting All Columns**

```sql
SELECT 
    *
FROM
    customers
```

**Selecting specified columns**

```sql
SELECT 
    first_name, last_name
FROM
    customers
```
 
> We can use arithmetic expression to calculate a discount for example


```sql
SELECT 
    first_name,
    (points - points * 50 / 100) AS discounted_points
FROM
    customers
Distinct retreive only unique results with no deuplicates  

SELECT DISTINCT
    state
FROM
    customers
```