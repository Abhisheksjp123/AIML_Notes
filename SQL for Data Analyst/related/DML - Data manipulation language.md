**DML (Data Manipulation Language)** is a subset of SQL used to manipulate and retrieve data stored in database tables. to do CRUD operation create,retrieve, update and delete

For this we'll be using Oracle MySQL workbench DBMS
Database name: campusx

tables:
CREATE TABLE users(
	user_id INTEGER PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
    )
# INSERT
Adds new records to database tables.
```
INSERT INTO campusx.users (user_id, name,email, password)
VALUES (NULL, 'nitish', 'nitish@gmail.com', '1234')

-- This also works, you don't alwasys need to specify column name but make sure 
-- all the values are entered and in correct sequence
INSERT INTO campusx.users
VALUES (NULL, 'nitish', 'nitish@gmail.com', '1234')

-- First format can also be used to input values in specific columns, given rest have default value set or are ok with nulls
INSERT INTO campusx.users (name,email)
VALUES ('nitish', 'nitish@gmail.com')
```
 Similarly you can also include multiple values, by adding VALUES() as per your requirement.


*You can also insert a table with insert statement with subqueries, example will come in RETRIEVE>SUBQUERIES*


# ==RETRIEVE - V.IMP==
The most commonly used DML command for querying and retrieving data from tables.

We'll be using smartphone data in this example, present in Github>SQL-Projects>CRUD_DML_operations

1. To fetch all the data from the table
```
SELECT * FROM campusx.smartphones
```

2. Filter selected columns
```
SELECT model, price,rating FROM campusx.smartphones
```

3. ALIAS or renaming columns
```
SELECT model, price AS 'price(INR)',rating FROM campusx.smartphones
```

4. mathematical expressions or calculations or feature/attribute creation

lets create PPI - pixel per inch which is 
$$
PPI = √(W² + H²) / diagonal\_size\_in\_inches
$$
```
SELECT model, SQRT(resolution_width*resolution_width + resolution_height*resolution_height)/screen_size 
FROM campusx.smartphones
```

5. Contant value column
```
SELECT model, 'smartphone' as 'type' FROM campusx.smartphones
```

this will create a new column type with constant value smartphone

6. DISTINCT or unique values in a column
```
SELECT DISTINCT(brand_names) as 'all_brands' FROM campusx.smartphones
```

Distinct combinations

```
SELECT DISTINCT brand_name , processor_brand FROM campusx.smartphones
```

7. Filtering rows based on WHERE clause
```
SELECT * FROM FROM campusx.smartphones WHERE brand_name = 'samsung'

also
SELECT * FROM FROM campusx.smartphones WHERE price > 50000
```

these =, > are known as operators, some other popular SQL specific operators
[[SQL operators]]

8. Sorting values with ==ORDER BY==

Ex. find top 5 smart phones by samsung with the highest price
```
SELECT model, price
FROM campusx.smartphones
WHERE brand = 'samsung'
ORDER BY price DESC LIMIT 5
```

==LIMIT== is used to display top n rows just like head function in pandas
a very good question on limit [[SQL Practice Question bank]] Q1

We can also Sort by multiple columns as
```
SELECT model, brand, price
FROM campusx.smartphones
ORDER BY brand ASC, price DESC
```

9. ==GROUP BY==
ex. Group smartphones by brand and get count, average price, max rating, avg screen_size and 
```
SELECT count(*) AS 'count', avg(price) AS 'average_price',
max(ratings) AS 'max_rating', avg(screen_size) AS 'average_screen_size'
FROM campusx.smartphones
GROUP BY brand_name
```

Groupby with multiple columns
```
SELECT count(*) AS 'count', avg(price) AS 'average_price',
max(ratings) AS 'max_rating', avg(screen_size) AS 'average_screen_size'
FROM campusx.smartphones
GROUP BY brand_name, processor_brand
```

10. HAVING
What WHERE is for SELECT, HAVING is the same for GROUP BY 
ex. find out average ratings of brands which have more than 20 phones
```
SELECT brand_name, count(*) AS 'count', AVG(rating) AS 'ratings'
FROM campusx.smartphones
GROUP BY brand_name
HAVING count>=20
```

11. [[SQL Joins]]
12. [[SQL SubQueries]]
13. [[SQL Common table expressions - CTEs]]
14. [[SQL Window Funtion]]
# UPDATE
Modifies existing records in database tables.

```
UPDATE campusx.smartphones
SET processor_brand = 'dimensity'
WHERE processor_brand = 'mediatek'

-- Multiple values can also be updated

UPDATE campusx.smartphones
SET brand = 'samsung korea', has_5g = 'False'
WHERE brand = 'samsung'
```


# DELETE
Removes records from database tables.

```
DELETE FROM campusx.smartphones
WHERE price>200000
```