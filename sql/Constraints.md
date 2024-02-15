

## Constraints


Constraints are rules defined for the data in a database to maintain the integrity and accuracy of the data .

**1. Primary Key Constraint**
Purpose: Ensures that each record in a table is uniquely identified.

```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50)
);
```

**2. Foreign Key Constraint**
Purpose: Enforces referential integrity between two tables.

CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(50)
);

```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(department_id),
    first_name VARCHAR(50),
    last_name VARCHAR(50)
);
```

Sometimes we will create the table employees before the table departments , so we had to add the foreign key after the creation of the departments table , we will use ALTER , Query :

```sql
ALTER TABLE employees
ADD FOREIGN KEY(department_id)
REFERENCES departments(department_id)
ON DELETE SET NULL;
```

**3. Unique Constraint**
Purpose: Ensures that all values in a column are unique.

```sql
CREATE TABLE students (
    student_id INT UNIQUE,
    first_name VARCHAR(50),
    last_name VARCHAR(50)
);
```

**4. Check Constraint**

Purpose: Ensures that values in a column meet a specified condition.

```sql
CREATE TABLE orders (
    order_id INT,
    order_amount DECIMAL CHECK (order_amount > 0),
    order_date DATE
);
```

**5. Not Null Constraint**
Purpose: Ensures that a column cannot have a NULL value.

```sql
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(50) NOT NULL,
    price DECIMAL
);
```

**6. Default Constraint**
Purpose: Provides a default value for a column when no value is specified.

```sql
CREATE TABLE tasks (
    task_id INT PRIMARY KEY,
    task_name VARCHAR(50),
    status VARCHAR(20) DEFAULT 'Pending'
);
```

**7. Auto increment**
Purpose: it will increment our INT id by one in case of inserting 

```sql
CREATE TABLE students(
     student_id INT PRIMARY KEY AUTO_INCREMENT,
     name VARCHAR(50) NOT NULL UNIQUE,
     major VARCHAR(50)
);
```