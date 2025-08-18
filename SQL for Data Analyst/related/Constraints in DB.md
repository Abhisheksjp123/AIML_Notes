Constraints in are rules and conditions that must be met for data to be inserted, updated, or deleted in a database table. They are used to enforce the integrity of the data stored in a database and to prevent data from becoming inconsistent or corrupted.

*Constrains are enforced with the DDL commands in Database


# 1. NOT NULL
Ensures that a column cannot have empty/null values.
```
CREATE TABLE users(
user_id INT NOT NULL,
name VARCHAR(100) NOT NULL,
email VARCHAR(150),
password VARCHAR(255)
)
```
# 2. UNIQUE(combo)
Ensures that all values in a column or combination of columns are unique across the table.
```
CREATE TABLE users(
user_id INT NOT NULL,
name VARCHAR(100) NOT NULL,
email VARCHAR(150) NOT NULL UNIQUE,
password VARCHAR(255) NOT NULL
)
```

Another way of creating constraint:
this have two benifts:
1. Instead of specifying an attribute to be unique, they can give a combination of attributes to be unique. in below case name+email should be unique
2. This also specifies a name to unique constraint, so in future you can delete this contraint without affecting the overall table.
```
CREATE TABLE users(
	user_id INT NOT NULL,
	name VARCHAR(100) NOT NULL,
	email VARCHAR(150) NOT NULL,
	password VARCHAR(255) NOT NULL,

	CONSTRAINT user_email_unique UNIQUE (name, email)
)
```

# 3. PRIMARY KEY
Uniquely identifies each record in a table. Combines NOT NULL and UNIQUE constraints.

```
CREATE TABLE users(
user_id INT NOT NULL PRIMARY KEY,
name VARCHAR(100) NOT NULL,
email VARCHAR(150) NOT NULL UNIQUE,
password VARCHAR(255) NOT NULL
)
```

Another way of creating constraint:
1. This is the way to create composite pk. in below example both user_id+name are used to create composite key
```
CREATE TABLE users(
	user_id INT NOT NULL,
	name VARCHAR(100) NOT NULL,
	email VARCHAR(150) NOT NULL,
	password VARCHAR(255) NOT NULL,

	CONSTRAINT user_name_pk PRIMARY KEY (user_id, name)
)
```
# 4. AUTO INCREMENT
Automatically generates unique sequential numbers for a column (typically primary keys).
```
CREATE TABLE users(
user_id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
name VARCHAR(100) NOT NULL,
email VARCHAR(150) NOT NULL UNIQUE,
password VARCHAR(255) NOT NULL

```
# 5. CHECK
```
CREATE TABLE users(
	user_id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
	name VARCHAR(100) NOT NULL,
	email VARCHAR(150) NOT NULL UNIQUE,
	password VARCHAR(255) NOT NULL
	age INT NOT NULL CHECK (age>6 AND age<25)
```
Another way of creating constraint:
```
CREATE TABLE users(
	user_id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
	name VARCHAR(100) NOT NULL,
	email VARCHAR(150) NOT NULL UNIQUE,
	password VARCHAR(255) NOT NULL
	age INT NOT NULL,
	CONSTRAINT age_check CHECK (age>6 AND age<25)	
```
# 6. DEFAULT
Provides a default value for a column when no value is specified during insertion.
```
CREATE ticket(
	ticket_id INT PRIMARY KEY,
	name VARCHAR(255) NOT NULL,
	travel_date DATETIME DEFAULT CURRENT_TIMESTAMP
)
```
# 7. FOREIGN KEY 
The most important constraint
Ensures referential integrity by linking records between tables.

```
-- Table 1 customer table
CREATE TABLE customers(
	c_id INT PRIMARY KEY AUTO_INCREMENT,
	name VARCHAR(255) NOT NULL,
	email VARCHAR(255) UNIQUE
)

--Table 2 Orders table
CREATE TABLE orders(
    order_id INT PRIMARY KEY,
    c_id INTEGER NOT NULL,
    order_date DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
    
    CONSTRAINT orders_fk FOREIGN KEY (c_id) REFERENCES customers(c_id)
    )
```

The benefit of using a primary key is that:
- if you want to delete customer table, it will throwgh a error, because that table is being utilized by orders table.
so by this we ensure the integrity of orders table
 - Also it creates a reference so you can only deletes a customer after deleting the orders of the customer from the orders table, these restricions are also called referential actions.

# Referential Actions 
1. RESTRICT
This is the default action, lets say if we delete a customer from customer table, it will not let us delete it if its order are present in orders table.
2. CASCADE
In cascade if you delete a customer from customer table all its related orders will also be deleted from the orders table
3. SET NULL
in set null if you delete a customer all its order will be marked to a null customer
4. SET DEFAULT
in set null if you delete a customer all its order will be marked to a default value

## How to apply referential actions?

```
CREATE TABLE orders(
    order_id INT PRIMARY KEY,
    c_id INTEGER NOT NULL,
    order_date DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
    
    CONSTRAINT orders_fk FOREIGN KEY (c_id) REFERENCES customers(c_id)
    ON DELETE CASCADE
    ON UPDATE CASCADE
    )
```