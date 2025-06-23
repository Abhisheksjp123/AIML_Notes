Classes as Abstraction

```
# Without class abstraction
car_speed = 0
car_fuel = 100

def accelerate():
    global car_speed, car_fuel
    if car_fuel > 0:
        car_speed += 10
        car_fuel -= 5

# With class abstraction - clean object interface
class Car:
    def __init__(self):
        self._speed = 0      # Hidden details
        self._fuel = 100     # Hidden details
    
    def accelerate(self):    # Simple interface
        if self._fuel > 0:
            self._speed += 10
            self._fuel -= 5
    
    def get_speed(self):     # Controlled access
        return self._speed

my_car = Car()
my_car.accelerate()  # Don't need to know internal workings
print(my_car.get_speed())


```

**What classes abstract:**

- Data representation (attributes)
- Internal state management
- Complex relationships between data and behaviour
- Object lifecycle