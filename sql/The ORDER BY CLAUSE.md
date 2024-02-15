## The ORDER BY CLAUSE


**Sorting**

##### Sorting result in ascending order .
```sql
SELECT * FROM customers ORDER BY first_name asc
```

##### Or

```sql
SELECT * FROM customers ORDER BY first_name asc
```

##### Sorting result in descending order .

```sql
SELECT * FROM customers ORDER BY first_name desc
```

##### Sorting result in ascending order by state , then if a two states contains same first letter , it sort by firsname
```sql
SELECT * FROM customers ORDER BY state , first_name
```