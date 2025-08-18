- BETWEEN
``` 
SELECT * FROM campusx.smartphones WHERE price BETWEEN 10000 AND 20000
```

- AND/OR
``` 
SELECT * FROM campusx.smartphones WHERE price < 250000 AND rating >  80
```

 - IN and NOT IN
```
SELECT * FROM campusx.smartphones
WHERE processor_brand IN ('snapdragon', 'exynos', 'bionic')
```

this is a way to pass a list instead of several OR operators