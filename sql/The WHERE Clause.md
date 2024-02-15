## The WHERE Clause


**Comparison operators**

```sql
SELECT * FROM customers  WHERE customer_id > 3
```

```sql
SELECT * FROM customers  WHERE customer_id  < 3

```

```sql

SELECT * FROM customers  WHERE customer_id = 3
```

```sql

SELECT * FROM customers  WHERE customer_id != 3
```

```sql
SELECT * FROM customers WHERE birth_date > '1991-04-14'
```




**Logical Operators AND**

```sql
SELECT * FROM orders  WHERE order_date >= '2018-01-01'  AND order_date <= ‘2018-12-31'
```
**Logical Operators OR**

```sql
SELECT * FROM orders  WHERE order_date >= '2018-01-01'  OR points > 3000
```

**IN Operator**

```sql
SELECT * FROM customers WHERE state IN ('VA', 'FL' , ‘GA’)
```
**NOT IN Operator**

```sql
SELECT * FROM customers WHERE state NOT IN ('VA', 'FL' , ‘GA’)
```

**BETWEEN Operator**


> Its LIKE ( SELECT * FROM customers WHERE points >= 1000 AND points <= 3000 )

```sql
SELECT * FROM customers WHERE points BETWEEN 1000 AND 3000
```

Or between for dates LIKE that : 
```sql
SELECT * FROM customers WHERE birth_date BETWEEN '1990-01-01' AND '2000-01-01'
```

**REGEXP Operator**


>Returns customers whose first name starts with 'a'

```sql
SELECT * FROM customers  WHERE first_name REGEXP ‘^a’ 
```

>**^** beginning of a string

>**$** end of a string

>**|** logical OR

>**[abc]** match any single characters 

>**[a-d]** any characters from a to d

**More Examples**

—- Returns customers whose first name ends with EY or ON 

```sql
WHERE first_name REGEXP ‘ey$|on$’
```

—- Returns customers whose first name starts with MY   —- or contains SE

```sql
WHERE first_name REGEXP ‘^my|se’ 
```

—- Returns customers whose first name contains B followed by   —- R or U

```sql
WHERE first_name REGEXP ‘b[ru]’ 
```

**IS NULL Operator**

Returns customers who don’t have a phone number 

```sql
SELECT * FROM customers  WHERE phone IS NULL 
```

```sql
SELECT * FROM customers  WHERE phone IS NOT NULL
```