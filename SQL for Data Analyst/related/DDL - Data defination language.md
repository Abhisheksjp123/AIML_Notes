Data defination language
CREATE | ALTER | DROP | TRUNCATE
# CREATE
Creates databases, tables, indexes, views, etc.

1. Creating a Database
```
CREATE DATABASE campusx

'more optimal way to do this would be

CREATE DATABASE IF NOT EXISTS campusx
```

2. Creating a Table
   To create a table you should always have a structure in your mind
   what columns will there be in table, their contrains and type etc
   Example: users(userid-int, name-varchar, email-varchar, password-varchar)
```
CREATE TABLE users(
	user_id INTEGER,
	name VARCHAR(255),
	email VARCHAR(255),
	password VARCHAR(255)
)
```

# DROP
Completely removes database objects and their data.

1. DROP database
```
DROP DATABASE campusx

'more optimal way to do this would be

DROP DATABASE IF EXISTS campusx

```

2. DROP table
```
DROP TABLE IF EXISTS campusx
```
# TRUNCATE
Removes all rows from a table while preserving its structure.
```
TRUNCATE TABLE userid
```


# ALTER
The ALTER TABLE statement in SQL is used to modify the structure of an existing table. Some of the things that can be done using the ALTER TABLE statement include.

1. ADD COLUMN
```
ALTER TABLE customers ADD COLUMN password VARCHAR(255) NOT NULL
```

*You can also add a column AFTER/BEFORE a certain column*
```
ALTER TABLE customers ADD COLUMN surname VARCHAR(255) NOT NULL AFTER name
```

2. DROP COLUMN
```
ALTER TABLE customers 
DROP COLUMN surname,
DROP COLUMN password
```
3. MODIFY COLUMN
```
ALTER TABLE customers MODIFY COLUMN surname INT NOT NULL AUTO_INCREMENT AFTER name
```

## One more benifit of using ALTER TABLE you can edit/delete existing constraints

4. ADD/MODIFY CONSTRAINT
```
ALTER TABLE customers ADD CONSTRAINT cust_age_check CHECK(age>18)

-- modify constraints
-- MySQL does not allows to modify constraint, you first need to delete and add ----- new constraints

ALTER TABLE customers DROP CONSTRAINT cust_age_check CHECK
```