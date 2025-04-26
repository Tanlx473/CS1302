**CS1302 Introduction to Computer Programming**

**Mock Final Exam (Harder Version)**

**Time allowed**: 2 Hours
**Total marks**: 40 marks
**Part 1: Multiple Choice Questions (10 marks)**
**Part 2: Programming Questions (30 marks)**

------

**Part 1: Multiple Choice Questions** (1 mark each)

> *Note: Some questions have more than one correct answer. You must select all correct options to get full marks. No partial credit.*

1. Which of the following are **mutable** types in Python?

   A. list
   B. tuple
   C. dictionary
   D. string

2. Which of the following code snippets correctly creates an empty set?

   A. `empty_set = {}`
   B. `empty_set = set()`
   C. `empty_set = []`
   D. `empty_set = set([])`

3. What is the result of evaluating: `3 + 2 * 2**3 // 2 - 5`?

   A. 9
   B. 8
   C. 6
   D. 7

4. Which statements about functions are **true**?

   A. Every function must return a value.
   B. Functions can have no parameters.
   C. Functions can return multiple values.
   D. A function body must be indented.

5. What will `list("abcd")` produce?

   A. `["abcd"]`
   B. `["a", "b", "c", "d"]`
   C. `("a", "b", "c", "d")`
   D. `{"a", "b", "c", "d"}`

6. What happens when you use `next()` on a generator that has no more items?

   A. Raises a `StopIteration` exception.
   B. Returns `None`.
   C. Restarts the generator.
   D. Causes an infinite loop.

7. Which of the following statements about `global` and `nonlocal` are correct?

   A. `global` makes a variable available across different functions.
   B. `nonlocal` allows a nested function to modify a variable from the enclosing scope.
   C. `global` variables are safer to use than local variables.
   D. `nonlocal` can be used in the main (global) scope.

8. Which of the following will correctly **append** an item to a list?

   A. `mylist.add(3)`
   B. `mylist.append(3)`
   C. `mylist.insert(3)`
   D. `mylist.extend([3])`

9. Which operator has the **highest** precedence in Python?

   A. `*` (multiplication)
   B. `+` (addition)
   C. `**` (exponentiation)
   D. `//` (integer division)

10. Which of the following about list comprehension are true?

    A. List comprehensions can have if-else conditions.
    B. List comprehensions are generally slower than for-loops.
    C. List comprehensions create a new list.
    D. List comprehensions modify the original list.

------

**Part 2: Programming Questions** (3 marks each)

> *Answer each coding question clearly. Proper style and formatting are required.*

1. **(Generator)**

   Write a generator `even_numbers()` that produces the next even number starting from 0 each time it's called.

   **Test Code:**

   ```python
   gen = even_numbers()
   print(next(gen))  # 0
   print(next(gen))  # 2
   print(next(gen))  # 4
   print(next(gen))  # 6
   ```

2. **(String manipulation)**

   Write a function `count_vowels(s)` that counts the number of vowels ('a', 'e', 'i', 'o', 'u') in a string, regardless of case.

   **Test Code:**

   ```python
   print(count_vowels("Hello World"))  # 3
   print(count_vowels("AEIOUaeiou"))   # 10
   ```

3. **(List operation)**

   Write a function `second_largest(lst)` that returns the second largest number in a list. Assume the list contains at least two different elements.

   **Test Code:**

   ```python
   print(second_largest([3, 5, 2, 8, 7]))  # 7
   print(second_largest([10, 20, 20, 10, 30]))  # 20
   ```

4. **(Recursion)**

   Define a recursive function `sum_of_digits(n)` that returns the sum of the digits of a non-negative integer `n`.

   **Test Code:**

   ```python
   print(sum_of_digits(123))  # 6
   print(sum_of_digits(0))    # 0
   ```

5. **(File processing)**

   Write a function `read_and_sum(filename)` that reads numbers (one per line) from a file and returns their total sum.

   **Test Code:**

   ```python
   with open("test_numbers.txt", "w") as f:
       f.write("1\n2\n3\n4\n5")
   print(read_and_sum("test_numbers.txt"))  # 15
   ```

6. **(Dictionary processing)**

   Write a function `invert_dict(d)` that takes a dictionary and returns a new dictionary swapping keys and values.

   **Test Code:**

   ```python
   print(invert_dict({"a":1, "b":2}))  # {1:"a", 2:"b"}
   print(invert_dict({1:"x", 2:"y"}))  # {"x":1, "y":2}
   ```

7. **(While loop)**

   Write a function `guess_password(secret)` that keeps asking the user to input until they guess the correct password.

   **Test Code:**

   ```python
   # This test assumes manual input:
   # secret = "1234"
   guess_password("1234")
   ```

8. **(Set operations)**

   Write a function `common_elements(a, b)` that returns a set containing elements common to lists `a` and `b`.

   **Test Code:**

   ```python
   print(common_elements([1,2,3], [2,3,4]))  # {2,3}
   print(common_elements(["a","b"], ["b","c"]))  # {"b"}
   ```

9. **(Function with variable arguments)**

   Write a function `average(*args)` that returns the average value of all numeric arguments passed to it.

   **Test Code:**

   ```python
   print(average(1,2,3,4))  # 2.5
   print(average(5,5))      # 5.0
   ```

10. **(Decorator)**

    Write a decorator `timer(func)` that prints how long a function takes to execute.

    **Test Code:**

    ```python
    import time
    
    @timer
    def test_func():
        time.sleep(1)
        print("Function executed")
    
    test_func()
    ```

------

**End of Mock Final Exam**

------

**Answers:**

**Part 1:**

1. A, C
2. B, D
3. A
4. B, C, D
5. B
6. A
7. A, B
8. B, D
9. C
10. A, C

**Part 2 (Sample Solutions):**

1. 

```python
def even_numbers():
    n = 0
    while True:
        yield n
        n += 2
```

1. 

```python
def count_vowels(s):
    return sum(1 for c in s.lower() if c in 'aeiou')
```

1. 

```python
def second_largest(lst):
    lst = list(set(lst))
    lst.sort(reverse=True)
    return lst[1]
```

1. 

```python
def sum_of_digits(n):
    if n == 0:
        return 0
    else:
        return n % 10 + sum_of_digits(n // 10)
```

1. 

```python
def read_and_sum(filename):
    with open(filename) as f:
        return sum(int(line.strip()) for line in f)
```

1. 

```python
def invert_dict(d):
    return {v: k for k, v in d.items()}
```

1. 

```python
def guess_password(secret):
    while True:
        guess = input("Enter password: ")
        if guess == secret:
            print("Correct!")
            break
```

1. 

```python
def common_elements(a, b):
    return set(a) & set(b)
```

1. 

```python
def average(*args):
    return sum(args) / len(args) if args else 0
```

1. 

```python
import time

def timer(func):
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"Time taken: {end-start:.4f} seconds")
        return result
    return wrapper
```