# Complete Notes on Python `map()` Function

The `map()` function is one of Python's built-in **higher-order functions**. It applies a given function to every item of one or more iterables and returns a **map object (iterator)**.

---

# 1. Definition

**Syntax:**

```python
map(function, iterable)
```

or

```python
map(function, iterable1, iterable2, ...)
```

---

# 2. Parameters

| Parameter | Description                                                   |
| --------- | ------------------------------------------------------------- |
| function  | The function to apply to every item.                          |
| iterable  | One or more iterable objects (list, tuple, set, string, etc.) |

---

# 3. Return Value

Returns a **map object**, which is an iterator.

To see the results, convert it into:

* list()
* tuple()
* set()

Example:

```python
numbers = [1, 2, 3]

result = map(str, numbers)

print(result)
```

Output:

```
<map object at 0x...>
```

Convert to list:

```python
print(list(result))
```

Output

```
['1', '2', '3']
```

---

# 4. Basic Example

```python
def square(x):
    return x * x

numbers = [1,2,3,4,5]

result = map(square, numbers)

print(list(result))
```

Output

```
[1, 4, 9, 16, 25]
```

---

# 5. Using Lambda Function

Most programmers use `map()` with lambda.

```python
numbers = [1,2,3,4]

result = map(lambda x: x*x, numbers)

print(list(result))
```

Output

```
[1,4,9,16]
```

---

# 6. Convert Data Types

Convert strings to integers.

```python
numbers = ['10', '20', '30']

result = map(int, numbers)

print(list(result))
```

Output

```
[10,20,30]
```

Convert integers to strings

```python
numbers = [1,2,3]

print(list(map(str, numbers)))
```

Output

```
['1','2','3']
```

---

# 7. Convert Strings to Float

```python
prices = ['99.5','200.5','500']

result = map(float, prices)

print(list(result))
```

Output

```
[99.5,200.5,500.0]
```

---

# 8. Convert to Boolean

```python
values = [0,1,'',5]

print(list(map(bool, values)))
```

Output

```
[False, True, False, True]
```

---

# 9. Using Multiple Iterables

`map()` can take multiple iterables.

```python
a = [1,2,3]
b = [4,5,6]

result = map(lambda x,y: x+y, a, b)

print(list(result))
```

Output

```
[5,7,9]
```

---

Another example:

```python
name = ["A","B","C"]
marks = [80,90,95]

result = map(lambda x,y:(x,y), name, marks)

print(list(result))
```

Output

```
[('A',80),('B',90),('C',95)]
```

---

# 10. Different Length Iterables

`map()` stops at the shortest iterable.

```python
a = [1,2,3]
b = [10,20]

print(list(map(lambda x,y:x+y,a,b)))
```

Output

```
[11,22]
```

The third value of `a` is ignored.

---

# 11. Map with String

```python
text = "hello"

result = map(str.upper, text)

print(list(result))
```

Output

```
['H','E','L','L','O']
```

---

# 12. Map with Tuple

```python
numbers = (1,2,3)

print(list(map(lambda x:x*10,numbers)))
```

Output

```
[10,20,30]
```

---

# 13. Map with Set

```python
numbers = {1,2,3}

print(list(map(lambda x:x+5,numbers)))
```

Possible Output

```
[6,7,8]
```

*(Sets are unordered.)*

---

# 14. Map with Dictionary

By default, dictionary iteration returns keys.

```python
student = {
    "A":80,
    "B":90
}

print(list(map(str.upper, student)))
```

Output

```
['A','B']
```

Mapping over values

```python
student = {
    "A":80,
    "B":90
}

result = map(lambda x:x+5, student.values())

print(list(result))
```

Output

```
[85,95]
```

---

# 15. Map with User-defined Function

```python
def cube(x):
    return x**3

numbers = [1,2,3,4]

print(list(map(cube, numbers)))
```

Output

```
[1,8,27,64]
```

---

# 16. Map with Built-in Functions

```python
words = ['apple','banana','cat']

print(list(map(len, words)))
```

Output

```
[5,6,3]
```

---

```python
words = ['python','java']

print(list(map(str.upper, words)))
```

Output

```
['PYTHON','JAVA']
```

---

# 17. Reading Input Using map()

Very common in coding interviews.

```python
numbers = list(map(int, input().split()))
```

Input

```
10 20 30 40
```

Output

```
[10,20,30,40]
```

---

Read float input

```python
prices = list(map(float, input().split()))
```

---

# 18. Nested map()

```python
matrix = [
    ['1','2'],
    ['3','4']
]

result = list(map(lambda row:list(map(int,row)), matrix))

print(result)
```

Output

```
[[1,2],[3,4]]
```

---

# 19. Map Object is an Iterator

```python
numbers = [1,2,3]

result = map(lambda x:x*x,numbers)

print(next(result))
print(next(result))
print(next(result))
```

Output

```
1
4
9
```

---

After iterator is exhausted:

```python
print(list(result))
```

Output

```
[]
```

---

# 20. List Comprehension vs map()

Using map

```python
numbers = [1,2,3]

result = list(map(lambda x:x*x,numbers))
```

Using list comprehension

```python
numbers = [1,2,3]

result = [x*x for x in numbers]
```

Both produce

```
[1,4,9]
```

### Which is better?

Use `map()` when:

* Applying an existing function (e.g., `str`, `int`, `len`).
* Working in a functional programming style.

Use list comprehensions when:

* The transformation is complex.
* You need conditions (`if`).
* Readability is more important.

---

# 21. Advantages

* Faster than explicit loops in many simple cases.
* Less code.
* Memory efficient (returns an iterator).
* Can process multiple iterables.
* Useful with lambda functions.
* Common in competitive programming.

---

# 22. Disadvantages

* Can reduce readability if overused with complex lambdas.
* Returns an iterator, so it can only be consumed once.
* For complex logic, list comprehensions are usually easier to read.

---

# 23. Time Complexity

If there are **n** elements:

* Time Complexity: **O(n)**
* Space Complexity:

  * **O(1)** for the `map` object itself.
  * **O(n)** if you convert it to a list.

---

# 24. Common Mistakes

### Mistake 1: Forgetting to convert to a list

```python
result = map(int, ['1','2'])

print(result)
```

Output

```
<map object at ...>
```

Correct:

```python
print(list(result))
```

---

### Mistake 2: Function call instead of function reference

Wrong

```python
map(square(), numbers)
```

Correct

```python
map(square, numbers)
```

---

### Mistake 3: Different number of arguments

Wrong

```python
map(lambda x,y:x+y,[1,2,3])
```

Need two iterables.

Correct

```python
map(lambda x,y:x+y,[1,2],[3,4])
```

---

# 25. Real-world Examples

### Increase Salary

```python
salary = [25000,30000,40000]

new_salary = list(map(lambda x:x+5000,salary))

print(new_salary)
```

Output

```
[30000,35000,45000]
```

---

### Capitalize Names

```python
names = ['john','alice','bob']

print(list(map(str.title,names)))
```

Output

```
['John','Alice','Bob']
```

---

### Find Length of Words

```python
words = ['Python','Java','C++']

print(list(map(len,words)))
```

Output

```
[6,4,3]
```

---

### Celsius to Fahrenheit

```python
temps = [0,20,30,40]

fahrenheit = list(map(lambda c:(c*9/5)+32,temps))

print(fahrenheit)
```

Output

```
[32.0,68.0,86.0,104.0]
```

---

# 26. Interview Questions

**Q1. Does `map()` modify the original list?**

**Answer:** No.

---

**Q2. Is `map()` lazy?**

**Answer:** Yes. It returns an iterator and computes values only when needed.

---

**Q3. Can `map()` accept multiple iterables?**

**Answer:** Yes.

```python
map(function, list1, list2)
```

---

**Q4. What happens if iterables have different lengths?**

**Answer:** It stops at the shortest iterable.

---

**Q5. Which is faster: `map()` or a `for` loop?**

**Answer:** For simple function applications, `map()` is often slightly faster because its core implementation is in C. For more complex transformations, performance differences are usually negligible, and readability should guide your choice.

---

# 27. Quick Revision (Cheat Sheet)

| Feature                    | Description                                   |
| -------------------------- | --------------------------------------------- |
| Function                   | Applies a function to each element            |
| Returns                    | `map` object (iterator)                       |
| Syntax                     | `map(func, iterable)`                         |
| Multiple iterables         | Yes                                           |
| Stops at                   | Shortest iterable                             |
| Lazy evaluation            | Yes                                           |
| Original iterable modified | No                                            |
| Convert output             | `list()`, `tuple()`, `set()`                  |
| Time Complexity            | **O(n)**                                      |
| Space Complexity           | **O(1)** (iterator), **O(n)** if materialized |

## Key Takeaways

* `map()` transforms every element of one or more iterables using a function.
* It returns a **lazy iterator**, making it memory efficient.
* It is commonly used with **`lambda` functions** and built-in functions like `int`, `str`, `float`, and `len`.
* When you need the actual values, convert the result using `list()`, `tuple()`, or another collection type.
* For simple transformations, `map()` is concise and efficient; for more complex logic, list comprehensions are often more readable.
