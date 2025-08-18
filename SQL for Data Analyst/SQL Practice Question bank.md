#SQL-limit
Q1. Write a SQL query to find the phone model with the second largest battery capacity from the phones table

```
-- Assumed table structure
CREATE TABLE phones (
    phone_id INT PRIMARY KEY,
    model_name VARCHAR(100) NOT NULL,
    brand VARCHAR(50) NOT NULL,
    battery_capacity INT NOT NULL,  -- in mAh
    price DECIMAL(10,2),
    release_date DATE,
    screen_size DECIMAL(3,1),
    storage_gb INT
);
```

>[!Solution]-
>```
>SELECT model_name, battery_capacity
>FROM phones
>OREDER BY DESC
>LIMIT 1,1
>```
>LIMIT a,b offsets the output rows by a and returns b rows
>here as indexing starts from 0 it offsets by 1 and gives 1 value

