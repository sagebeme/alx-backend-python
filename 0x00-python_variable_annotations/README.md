0x00. Python - Variable Annotations
====================================

This project practices **type hints** in Python: annotating function parameters and return types so code is clearer and tools (IDEs, mypy) can catch type errors.

Tasks
-----

### 0. Add two floats

Defines a type-annotated function `add(a, b)` that adds two floats and returns a float. You practice annotating simple parameters and return type so tools (IDEs, mypy) can check correctness. Run: `python3 0-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `0-add.py`

### 1. Concatenate strings

`concat(str1, str2)` that concatenates two strings, with full type annotations. Run: `python3 1-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `1-concat.py`

### 2. Floor a float

`floor(n)` that takes a float, floors it to an integer, and returns that int — all annotated. Run: `python3 2-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `2-floor.py`

### 3. Float to string

`to_str(n)` that converts a float to its string representation, with annotations. Run: `python3 3-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `3-to_str.py`

### 4. Define annotated variables

Variables (`a`, `pi`, `i_understand_annotations`, `school`) with explicit type annotations (int, float, bool, str). Run: `python3 4-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `4-define_variables.py`

### 5. Sum list of floats

`sum_list(input_list)` takes a list of floats (`typing.List`) and returns their sum as a float. Run: `python3 5-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `5-sum_list.py`

### 6. Sum mixed list

Function that takes a list of integers and floats and returns their sum as a float (e.g. `List[Union[int, float]]`). Run: `python3 6-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `6-sum_mixed_list.py`

### 7. Tuple (key, value²)

`to_kv(k, v)` takes a string `k` and an int or float `v` and returns a tuple `(k, v * v)` with correct annotations. Run: `python3 7-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `7-to_kv.py`

### 8. Make multiplier (Callable)

Returns a multiplier function: given a float `multiplier`, returns a function that takes a float and returns `multiplier * that_float`. Run: `python3 8-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `8-make_multiplier.py`

### 9. Element length

Function that takes an iterable of sequences and returns a list of their lengths (e.g. Iterable, List). Run: `python3 9-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `9-element_length.py`

### 10. Safe first element

`safe_first_element(lst)` returns the first element of a sequence if it exists, otherwise `None` (Union or Optional). Run: `python3 100-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `100-safe_first_element.py`

### 11. Safely get value

Function that safely gets a value from a mapping by key with an optional default (Mapping, Optional). Run: `python3 101-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `101-safely_get_value.py`

### 12. Type checking

Conditionals and type narrowing with annotations; e.g. TYPE_CHECKING to avoid circular imports. Run: `python3 102-main.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x00-python_variable_annotations`
-   File: `102-type_checking.py`

---

**How to do the exercises yourself**

1. Open the task file (e.g. `5-sum_list.py`) and read the docstring.
2. Implement the function with the correct type annotations (`typing.List`, `-> float`, etc.).
3. Run the matching `*-main.py` to verify behavior (e.g. `python3 5-main.py`).
4. Optionally run `mypy <file>.py` to check types. The `*-main.py` files are driver scripts that import and call the task functions.
