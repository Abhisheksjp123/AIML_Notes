Functions are a level of [[Abstraction]] in [[Object Oriented Programming - OOPs]]
```
# Without abstraction - messy details exposed
radius = 5
area = 3.14159 * radius * radius
print(f"Area: {area}")

# With function abstraction - clean interface
def calculate_circle_area(radius):
    pi = 3.14159
    return pi * radius * radius

area = calculate_circle_area(5)  # Hide the math details
print(f"Area: {area}")
```


**What functions abstract:**

- Implementation details (how the calculation works)
- Complex logic behind a simple interface
- Reusable behaviour
