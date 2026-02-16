0x02. Python - Async Comprehension
===================================

This project practices **async generators** and **async comprehensions**: producing and consuming streams of values asynchronously with `async for` and `[x async for x in ...]`.

Tasks
-----

### 0. Async generator

`async_generator()` yields 10 random floats (0–10), waiting 1 second between each yield. Run from a script with `async for value in async_generator(): print(value)` then `asyncio.run(main())`.

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x02-python_async_comprehension`
-   File: `0-async_generator.py`

### 1. Async comprehension

Coroutine that collects all 10 values from `async_generator()` using `[x async for x in async_generator()]` and returns that list. Run: `asyncio.run(async_comprehension())` and print the list.

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x02-python_async_comprehension`
-   File: `1-async_comprehension.py`

### 2. Measure runtime

Runs the async comprehension four times in parallel and measures total time (~10s). Run: `python3 2-measure_runtime.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x02-python_async_comprehension`
-   File: `2-measure_runtime.py`

---

**How to do the exercises yourself**

1. **0:** In `async def async_generator()`, loop 10 times: `await asyncio.sleep(1)`, then `yield random.uniform(0, 10)`. Return type hint: `AsyncGenerator[float, None]` or `Generator` from typing.
2. **1:** Define an async function that returns `[x async for x in async_generator()]`.
3. **2:** Use `asyncio.gather` to run the comprehension coroutine 4 times; measure time with `time.perf_counter()`; print the duration (should be around 10 seconds). Run: `python3 2-measure_runtime.py`.
