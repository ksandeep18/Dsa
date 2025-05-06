
# 🧠 Master the Basics to Code Like a Pro in Python

This guide covers all the **essential Python concepts** you need to confidently write code from scratch — whether for DSA, interviews, or projects.

---

## 1. ✅ Python Syntax & Semantics

- Python uses **indentation** to define blocks.
- No curly braces `{}` or semicolons `;` needed.

```python
def greet(name):
    print("Hello", name)
```

---

## 2. 🔤 Data Types

| Type   | Example           | Conversion     |
|--------|-------------------|----------------|
| `int`  | `5`               | `int("5")`     |
| `float`| `5.7`             | `float("5.7")` |
| `str`  | `"hello"`         | `str(123)`     |
| `bool` | `True`, `False`   | `bool(1)`      |
| `list` | `[1, 2, 3]`       | `list("abc")`  |
| `tuple`| `(1, 2)`          | `tuple([1,2])` |
| `dict` | `{"a": 1}`        | `dict()`       |
| `set`  | `{1, 2, 3}`       | `set([1,2,2])` |

---

## 3. 🔁 Loops & Control Flow

```python
# If-Else
if x > 0:
    print("Positive")
elif x == 0:
    print("Zero")
else:
    print("Negative")

# For Loop
for i in range(5):
    print(i)

# While Loop
while x > 0:
    print(x)
    x -= 1
```

---

## 4. ⚙️ Functions

```python
def add(a: int, b: int) -> int:
    return a + b
```

- Use `return` to get output.
- Functions help reuse code.

---

## 5. 🔄 Type Casting (Conversions)

```python
int("10")        # string to int
float("3.14")    # string to float
str(100)         # int to string
list("abc")      # string to list ['a', 'b', 'c']
```

---

## 6. 🎯 Important Built-in Functions

```python
len(), sum(), max(), min(), sorted()
input(), print()
range(), zip(), enumerate()
type(), isinstance()
abs(), pow(), round()
```

---

## 7. 🧮 Math Module (DSA Useful)

```python
import math

math.sqrt(25)
math.gcd(12, 18)
math.factorial(5)
math.ceil(2.3)
math.floor(2.7)
math.log(100, 10)
```

---

## 8. 📥 Input/Output Tricks

```python
x = int(input())
a, b = map(int, input().split())
arr = list(map(int, input().split()))
print("Result is:", a + b)
```

---

## 9. 🎒 Data Structures Essentials

```python
# List
arr = [1, 2, 3]
arr.append(4)
arr.sort()

# Dictionary
d = {"name": "Alex"}
d["age"] = 25

# Set
s = set()
s.add(1)

# Tuple
t = (1, 2)
```

---

## 10. 🧠 Useful Patterns in DSA

- Two Pointers
- Sliding Window
- Hash Maps
- Binary Search
- Recursion
- Prefix Sum
- Stack / Queue
- Graph Traversal (DFS, BFS)

---

## 11. 🧪 Typing (Type Hints)

```python
from typing import List, Tuple, Dict, Union

def process(data: Union[int, str]) -> None:
    print(data)
```

---

## 12. 🧹 Clean Code Practices

- Use meaningful variable/function names.
- Write small, modular functions.
- Comment complex logic.
- Avoid global variables.
- Keep code DRY (Don't Repeat Yourself).

---

## 13. 🛠️ Debugging Tips

- Use `print()` to trace variable values.
- Check for off-by-one errors in loops.
- Dry run the logic with pen-paper.

---

