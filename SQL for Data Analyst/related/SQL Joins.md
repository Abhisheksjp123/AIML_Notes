A join is a way to combine data from 2 or more sql tables based on  a related column between them.
Joins are used when we want to query information that is distributed across multiple tables in a database, and the information we need is not contained in a single table. By joining these tables we create a virtual table that contains all the information we need for our query.


But why do we need multiple tables? So that we are not repeating data, i.e data redundancy.
And this process is called [[Normalization in SQL]].

# Types of joins
![[Pasted image 20250818093528.png]]

and also 
## CROSS JOIN : 
which is cartisian product of left and right table, just like matrix
table 1 - n rows, table 2 - m rows -> Cross join table n\*m rows
```
SELECT * FROM users t1
CROSS JOIN groups t2
```


## INNER JOIN
```
SELECT * FROM users t1
INNER JOIN groups t2
ON t1.user_id = t2.user_id
```
* here t1 will be left table and t2 will be right table*
* also INNER JOIN is default JOIN, do even if you just mention JOIN, it will do INNER JOIN*

## LEFT/RIGHT JOIN
```
SELECT * FROM users t1
LEFT/RIGHT JOIN groups t2
ON t1.user_id = t2.user_id
```

## FULL OUTER JOIN

SQL does not allow FULL OUTER JOIN directly, but we can do it with set operations explained below.
we can do union b/w left join and right join SELECT statements.

### Multi columns join
```
SELECT * FROM students t1
JOIN class t2
ON t1.class_id = t2.class_id
AND t1.enrollment_year = t2.class_year 
```



# SQL Set operations
1. UNION: this opertor is used to combine the results of 2 or more SELECT statements in to a single result set. The UNION operator removes duplicate rows between the various SELECT statements.
2. UNION ALL: similar to UNION operator, but it does not remove duplicate rows
3. INTERSECT: returns only the rows taht appear in both result set of two SELECT statements
4. EXCEPT: the EXCEPT or MINUS operator returns only the distinct rows that appear in the first result set but not in the second result set of the two SELECT statements
```
SELECT * FROM person1
UNION
SELECT * FROM person2
```