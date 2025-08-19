CTEs (Common Table Expressions) are named temporary result sets that exist only for the duration of a single SQL statement and can be referenced within that statement.

Example: Find all the movies made by top 3 directors (in terms of total gross income)

```
WITH top_directors AS (SELECT director FROM movies
						GROUP BY director
						ORDER BY SUM(gross) DESC
						LIMIT 3)

SELECT * FROM movies
WHERE director IN (SELECT director FROM top_directors)
```