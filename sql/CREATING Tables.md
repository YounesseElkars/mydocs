## CREATING Tables

Query syntax for creation :
```sql
CREATE TABLE students(
     student_id INT PRIMARY KEY,
     name VARCHAR(50),
     major VARCHAR(50)
);
```

Create the same table with declaring the primary key in bottom :

```sql
CREATE TABLE students(
     student_id INT,
     name VARCHAR(50),
     major VARCHAR(50),
     PRIMARY KEY (student_id)
);
```

Adding a column after declaring the table:

```sql
ALTER TABLE students
ADD note DECIMAL(4,2);
```

Deleting the table :

```sql
DROP TABLE students;
```

Deleting a column in table :

```sql
ALTER TABLE students
DROP COLUMN note;
```

Display information about the columns in table students 

```sql
DESCRIBE students;
```






