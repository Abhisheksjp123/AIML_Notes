SQL has 3 types of functions

| **Type**                          | **Definition**                                                                                                                     | **Examples**                                  | **Return Value**                                                           |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------- | -------------------------------------------------------------------------- |
| **Scalar Functions**              | Operate on a **single value** and return a **single value**.                                                                       | `ABS()`, `UPPER()`, `ROUND()`, `GETDATE()`    | One value per input row                                                    |
| **Aggregate Functions**           | Operate on a **set of rows** and return a **single summary value**.                                                                | `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()` | One value per group (or entire table if no `GROUP BY`)                     |
| **User-Defined Functions (UDFs)** | Functions written by users to extend SQL’s functionality. Can be **scalar** (return one value) or **table-valued** (return a set). | `dbo.CalcTax()`, `GetAge(birthdate)`          | Depends on function type (scalar → one value, table-valued → rows/columns) |

# Aggregate functions
1. MAX/MIN
2. AVG
3. SUM
4. COUNT
5. COUNT(DISTINCT())
6. STD / VARIENCE

ex:

```
SELECT COUNT(phones) FROM campusx.smartphones
```
# Scalar functions
1. ABS()
2. ROUND(col, 2)
3. CEIL/FLOOR
4. 
