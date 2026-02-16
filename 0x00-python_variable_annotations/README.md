# 0x00. Python — Variable Annotations

This project practices **type hints** in Python: annotating function parameters and return types so code is clearer and tools (IDEs, mypy) can catch type errors.

---

## What does each file do?

Each answer is the **problem the file solves** and how to run it.

---

### **What does `0-add.py` do?**  
It defines a type-annotated function `add(a, b)` that adds two floats and returns a float. You practice annotating simple parameters and return type.  
**Run:** `python3 0-main.py`

### **What does `1-concat.py` do?**  
It defines `concat(str1, str2)` that concatenates two strings, with full type annotations.  
**Run:** `python3 1-main.py`

### **What does `2-floor.py` do?**  
It defines `floor(n)` that takes a float, floors it to an integer, and returns that int — all annotated.  
**Run:** `python3 2-main.py`

### **What does `3-to_str.py` do?**  
It defines `to_str(n)` that converts a float to its string representation, with annotations.  
**Run:** `python3 3-main.py`

### **What does `4-define_variables.py` do?**  
It defines a set of variables (`a`, `pi`, `i_understand_annotations`, `school`) with explicit type annotations (int, float, bool, str).  
**Run:** `python3 4-main.py`

### **What does `5-sum_list.py` do?**  
It defines `sum_list(input_list)` that takes a list of floats (using `typing.List`) and returns their sum as a float.  
**Run:** `python3 5-main.py`

### **What does `6-sum_mixed_list.py` do?**  
It defines a function that takes a list of integers and floats (mixed) and returns their sum as a float, using the right typing (e.g. `List[Union[int, float]]`).  
**Run:** `python3 6-main.py`

### **What does `7-to_kv.py` do?**  
It defines `to_kv(k, v)` that takes a string `k` and an int or float `v` and returns a tuple `(k, v * v)`, with correct annotations (Union for v).  
**Run:** `python3 7-main.py`

### **What does `8-make_multiplier.py` do?**  
It returns a multiplier function: given a float `multiplier`, it returns a function that takes a float and returns `multiplier * that_float`. You practice annotating higher-order functions (Callable).  
**Run:** `python3 8-main.py`

### **What does `9-element_length.py` do?**  
It defines a function that takes an iterable of sequences and returns a list of their lengths, using type annotations (e.g. Iterable, List).  
**Run:** `python3 9-main.py`

### **What does `100-safe_first_element.py` do?**  
It defines `safe_first_element(lst)` that returns the first element of a sequence if it exists, otherwise `None` — using `Union` or Optional in the return type.  
**Run:** `python3 100-main.py`

### **What does `101-safely_get_value.py` do?**  
It defines a function that safely gets a value from a mapping by key, with an optional default, using typing (Mapping, Optional, TypeVar or Any).  
**Run:** `python3 101-main.py`

### **What does `102-type_checking.py` do?**  
It uses conditionals and type narrowing (e.g. checking types before use) with annotations; often involves importing typing only when needed (e.g. TYPE_CHECKING) to avoid circular imports.  
**Run:** `python3 102-main.py`

---

### What are the `*-main.py` files?  
They are **driver scripts** that import and call the task functions to show expected behavior. Each `N-main.py` corresponds to the task file `N-*.py` (or the main task in that number). Use them to verify your implementation.

---

## How to do the exercises yourself

1. Open the task file (e.g. `5-sum_list.py`) and read the docstring.
2. Implement the function with the correct type annotations.
3. Run the matching `*-main.py` to confirm behavior.
4. Optionally run `mypy <file>.py` to check types.
