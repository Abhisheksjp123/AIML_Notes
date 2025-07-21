An object is **hashable** if:

1. It has a **fixed (unchanging)** value over its lifetime
    
2. It can be used as a **key in a dictionary** or stored in a **set**
    
3. It implements the __hash__() method and is **immutable

### **Examples of Hashable Types:**

- **Integers**: 1, 42
    
- **Strings**: 'apple', '123'
    
- **Tuples** _(only if they contain only hashable elements)_: (1, 2)

### **Examples of Non-Hashable Types:**

- **Lists**: [1, 2, 3] (mutable)
    
- **Dictionaries**: {'a': 1} (mutable)
    
- **Sets**: {1, 2} (mutable)