# Python 3.13 Cheatsheet 🚀

Python 3.13 introduces **new features** for f-strings, making them even more powerful and flexible. Below is a **comprehensive cheatsheet** covering all aspects of f-strings in Python 3.13.

---

## 🔹 1. Basic f-String Syntax

```python
name = "Alice"
age = 30
print(f"My name is {name} and I am {age} years old.")
# Output: My name is Alice and I am 30 years old.
```

---

## 🔹 2. Expressions Inside f-Strings

You can evaluate expressions inside `{}`.

```python
a = 10
b = 5
print(f"Sum: {a + b}, Product: {a * b}")
# Output: Sum: 15, Product: 50
```

---

## 🔹 3. String Formatting

### 📌 Width & Alignment

```python
text = "Hello"
print(f"[{text:>10}]")  # Right align
print(f"[{text:<10}]")  # Left align
print(f"[{text:^10}]")  # Center align
# Output:
# [     Hello]
# [Hello     ]
# [  Hello   ]
```

### 📌 Padding with Characters

```python
print(f"[{text:_>10}]")  # Fill empty space with "_"
# Output: [_____Hello]
```

### 📌 Truncating Strings

```python
print(f"{text:.3}")  # Only first 3 characters
# Output: Hel
```

---

## 🔹 4. Number Formatting

### 📌 Decimal Places

```python
pi = 3.1415926535
print(f"{pi:.2f}")  # 2 decimal places
# Output: 3.14
```

### 📌 Thousands Separator

```python
num = 1000000
print(f"{num:,}")  # Add commas
# Output: 1,000,000
```

### 📌 Percentage Format

```python
percent = 0.8543
print(f"{percent:.1%}")  # Convert to percentage
# Output: 85.4%
```

### 📌 Binary, Hex, and Octal

```python
num = 255
print(f"Binary: {num:b}, Hex: {num:x}, Octal: {num:o}")
# Output: Binary: 11111111, Hex: ff, Octal: 377
```

---

## 🔹 5. Nested f-Strings (New in Python 3.13)

You can now **nest** f-strings inside f-strings!

```python
name = "Alice"
style = "upper"
print(f"My name is {f'{name}'.upper() if style == 'upper' else name}")
# Output: My name is ALICE
```

---

## 🔹 6. Debugging with `=`

Using `=` inside an f-string shows both the variable name and its value.

```python
x = 42
print(f"{x=}")
# Output: x=42
```

You can combine it with expressions:

```python
print(f"{x + 5=}")
# Output: x + 5=47
```

---

## 🔹 7. Using `!r`, `!s`, and `!a`

### 📌 `!r` (repr) → Shows raw representation

```python
text = "Hello\nWorld"
print(f"{text!r}")
# Output: 'Hello\nWorld'
```

### 📌 `!s` (str) → Default string conversion (same as `str()`)

```python
print(f"{text!s}")
# Output: Hello
#         World
```

### 📌 `!a` (ascii) → ASCII representation

```python
print(f"{text!a}")
# Output: 'Hello\nWorld'
```

---

## 🔹 8. Multiline f-Strings

```python
name = "Alice"
age = 30
message = (
    f"My name is {name}.\n"
    f"I am {age} years old."
)
print(message)
# Output:
# My name is Alice.
# I am 30 years old.
```

---

## 🔹 9. Lambda Functions Inside f-Strings (New in Python 3.13)

Python 3.13 allows **inline lambdas** inside f-strings.

```python
print(f"{(lambda x: x * 2)(10)}")
# Output: 20
```

---

## 🔹 10. Assigning f-Strings to Variables (New in Python 3.13)

Python 3.13 lets you **assign** f-strings directly without using `str.format()`.

```python
x = 10
y = 20
formatted_string = f"{x} + {y} = {x + y}"
print(formatted_string)
# Output: 10 + 20 = 30
```

---

## 🔹 11. Lazy Evaluation with `=` Debugging (New in Python 3.13)

```python
import random
print(f"{random.randint(1, 100)=}")
# Output: random.randint(1, 100)=42 (for example)
```

---

## 🔹 12. Using `locals()` and `globals()`

```python
name = "Alice"
age = 30
print(f"Locals: {locals()}")
```

Outputs all local variables as a dictionary.

---

## 🔹 13. Performance Considerations

f-strings are **faster** than `.format()` and `%` formatting.

```python
import timeit
print(timeit.timeit("""f'Hello {42}'""", number=1000000))
```

---

## 🔹 14. Escaping `{` and `}`

If you need literal `{}` inside an f-string:

```python
print(f"{{This is inside curly braces}}")
# Output: {This is inside curly braces}
```

---

## 🔹 15. Combining f-Strings with JSON (New in Python 3.13)

```python
import json
data = {"name": "Alice", "age": 30}
print(f"{json.dumps(data, indent=2)}")
```

---

### 🎯 Summary of New Features in Python 3.13:

✅ **Nested f-strings** (`f"{f'{x}'}"`)  
✅ **Lambda functions in f-strings**  
✅ **Lazy evaluation in `=` debugging**  
✅ **Better variable assignments with f-strings**  
✅ **More consistent and readable string interpolation**

---

# 🚀 **Python 3.13 f-Strings Ultimate Guide** 🐍

In **Python 3.13**, f-strings have become **more powerful and flexible**, bringing **performance optimizations**, **new debugging features**, **nesting**, **lambdas**, and more. Let's dive deep into everything you can do with f-strings! 💡

---

## 📌 **1. Advanced Expressions in f-Strings**

You can use any **valid Python expression** inside `{}`.

### 🟢 Arithmetic Operations

```python
a, b = 5, 3
print(f"Sum: {a + b}, Difference: {a - b}, Product: {a * b}, Division: {a / b:.2f}")
# Output: Sum: 8, Difference: 2, Product: 15, Division: 1.67
```

### 🟢 Logical and Comparison Expressions

```python
x, y = 10, 20
print(f"x > y: {x > y}, x == y: {x == y}")
# Output: x > y: False, x == y: False
```

### 🟢 Using `if-else` inside f-Strings

```python
score = 85
print(f"Grade: {'Pass' if score >= 50 else 'Fail'}")
# Output: Grade: Pass
```

---

## 📌 **2. Advanced String Formatting**

f-strings can handle **complex string formatting**, similar to `.format()`.

### 🟢 Uppercase / Lowercase Formatting

```python
name = "alice"
print(f"Upper: {name.upper()}, Lower: {name.lower()}")
# Output: Upper: ALICE, Lower: alice
```

### 🟢 Title Case

```python
sentence = "hello world"
print(f"Title Case: {sentence.title()}")
# Output: Title Case: Hello World
```

### 🟢 Reversing Strings

```python
word = "Python"
print(f"Reversed: {word[::-1]}")
# Output: Reversed: nohtyP
```

---

## 📌 **3. Working with Lists and Tuples**

### 🟢 Accessing List Elements

```python
fruits = ["Apple", "Banana", "Cherry"]
print(f"First fruit: {fruits[0]}, Last fruit: {fruits[-1]}")
# Output: First fruit: Apple, Last fruit: Cherry
```

### 🟢 Joining Lists

```python
colors = ["red", "blue", "green"]
print(f"Colors: {', '.join(colors)}")
# Output: Colors: red, blue, green
```

### 🟢 f-Strings in List Comprehensions

```python
numbers = [1, 2, 3, 4, 5]
print(f"Squares: {[x**2 for x in numbers]}")
# Output: Squares: [1, 4, 9, 16, 25]
```

---

## 📌 **4. Working with Dictionaries**

### 🟢 Accessing Dictionary Values

```python
user = {"name": "Alice", "age": 25}
print(f"Name: {user['name']}, Age: {user['age']}")
# Output: Name: Alice, Age: 25
```

### 🟢 Formatting JSON with `json.dumps()`

```python
import json
data = {"name": "Alice", "age": 30}
print(f"Formatted JSON:\n{json.dumps(data, indent=2)}")
```

**Output:**

```
Formatted JSON:
{
  "name": "Alice",
  "age": 30
}
```

---

## 📌 **5. f-Strings with Functions**

### 🟢 Calling Functions Inside f-Strings

```python
def greet(name):
    return f"Hello, {name}!"

print(f"{greet('Alice')}")
# Output: Hello, Alice!
```

### 🟢 Using Lambda Functions (New in Python 3.13)

```python
print(f"{(lambda x: x**2)(5)}")
# Output: 25
```

---

## 📌 **6. Formatting Numbers**

### 🟢 Rounding Floating-Point Numbers

```python
pi = 3.1415926535
print(f"Rounded Pi: {pi:.3f}")
# Output: Rounded Pi: 3.142
```

### 🟢 Adding Thousands Separator

```python
salary = 1500000
print(f"Salary: ${salary:,}")
# Output: Salary: $1,500,000
```

### 🟢 Scientific Notation

```python
big_number = 123456789
print(f"Scientific Notation: {big_number:.2e}")
# Output: Scientific Notation: 1.23e+08
```

---

## 📌 **7. f-Strings and Date Formatting**

```python
from datetime import datetime

now = datetime.now()
print(f"Today: {now:%Y-%m-%d}, Time: {now:%H:%M:%S}")
# Output: Today: 2025-01-18, Time: 14:30:15
```

---

## 📌 **8. Nested f-Strings (New in Python 3.13)**

```python
name = "Alice"
print(f"{f'Hello, {name}!'}")
# Output: Hello, Alice!
```

---

## 📌 **9. Debugging with `=` (Python 3.8+)**

### 🟢 Print Variable Names and Values

```python
x = 10
print(f"{x=}")
# Output: x=10
```

### 🟢 Works with Expressions Too!

```python
a, b = 5, 3
print(f"{a + b=}, {a * b=}")
# Output: a + b=8, a * b=15
```

---

## 📌 **10. Handling Escape Characters**

### 🟢 Printing `{}` Inside an f-String

```python
print(f"{{This is inside curly braces}}")
# Output: {This is inside curly braces}
```

### 🟢 Escaping Quotes

```python
print(f"He said, \"Hello!\"")
# Output: He said, "Hello!"
```

---

## 📌 **11. Performance of f-Strings**

✅ **f-Strings are the fastest way to format strings in Python!** 🚀  
Compare performance:

```python
import timeit

print(timeit.timeit("""f'Hello {42}'""", number=1000000))  # Fastest
print(timeit.timeit("""'Hello {}'.format(42)""", number=1000000))  # Slower
print(timeit.timeit("""'Hello ' + str(42)""", number=1000000))  # Slowest
```

---

## 📌 **12. Real-World Use Cases**

### 🟢 Logging with f-Strings

```python
error = "File not found"
print(f"[ERROR] {error.upper()}")
# Output: [ERROR] FILE NOT FOUND
```

### 🟢 Generating SQL Queries

```python
table = "users"
column = "email"
print(f"SELECT {column} FROM {table} WHERE active=1;")
# Output: SELECT email FROM users WHERE active=1;
```

### 🟢 Creating Dynamic HTML

```python
name = "Alice"
print(f"<h1>Welcome, {name}!</h1>")
# Output: <h1>Welcome, Alice!</h1>
```

---

## 🎯 **Final Thoughts**

Python 3.13 makes f-strings even more **powerful** with:
✅ **Nested f-strings**  
✅ **Lambda functions**  
✅ **Lazy evaluation in `=` debugging**  
✅ **Performance improvements**

🔹 Mastering f-strings will **save time, improve readability, and enhance performance** in your Python projects! 🚀
