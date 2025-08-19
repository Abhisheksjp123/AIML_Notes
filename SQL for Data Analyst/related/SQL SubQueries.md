Subquery is a query within another query. It is a SELECT statement that is nested inside another SELECT, INSERT, UPDATE or DELETE statement. THe subquery is xecuted first and its result is then used as a parameter or condition fot the outer query.

Note - THe topic is slightly difficult and needs a lot of practice

Example: Find the movie with the highest rating. This can be done oter methods as well, but we'll focus on Subquery
```
SELECT * FROM movies
WHERE score = (SELECT MAX(score) FROM movies)
```

Order of execution,  Inner query i.e (SELECT MAX(score) FROM movies) runs first after that outer query is executed.

*We'll be using movies database for these queries, @ Github> SQL-Projects>Subqueries *
# Types of subqueries

## Based on the result it return
1. Scalar subquery
Returns single value
2. Row subquery
Returns Single row with multiple columns
Or One column and multiple rows
3. Table subquery
Returns Table

## Based on working
1. Independent subquery
Can execute independently of outer query

Example: #Independent-scalar-subquery 
Find the highest rated movie among all movies whose number of votes are greater than the dataset average votes

```
SELECT * FROM movies 
WHERE score = (SELECT MAX(SCORE) FROM movies
				WHERE votes > (SELECT AVG(votes)
								FROM movies))
```

Example : #Independent-row-subquery
Find all the movies made by top 3 directors (in terms of total gross income)
```
SELECT * FROM movies
WHERE director IN (SELECT director FROM movies
					GROUP BY director
					ORDER BY SUM(gross) DESC
					LIMIT 3)

```

Example: #Independent-Table-subquery
Find the movie with highest profit each year
```
SELECT * FROM MOVIES
WHERE (year, gross-budget) IN (SELECT year, MAX(gross-budget)
								FROM movies
								GROUP BY year )
```
2. Correlated subquery
References columns from outer query

Example1: Find all the movies that have a rating higher than the average rating of the movies in the same genre.

```
SELECT * FROM movies m1
WHERE score>(SELECT AVG(score) FROM movies m2
			WHERE m2.genre = m1.genre)
```

# Where can subqueries be used?
1. INSERT

```
INSERT INTO loyal_customers
(user_id, name)
SELECT t1.user_id, name
FROM orders t1
JOIN users t2 ON t1.user_id = t2.user_id
GROUP BY user_id
HAVING COUNT(*) > 3
```
1. SELECT
	1. With WHERE
	2. WIth SELECT
	3. With FROM
	4. With HAVING
2. UPDATE
3. DELETE


*We need to create subqueries in SQL because we cannot create variable in SQL like python, because SQL is a non procedural programming language, which makes it difficut to work with SQL*