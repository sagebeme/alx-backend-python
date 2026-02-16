0x01. Python - Async
====================

This project introduces **asynchronous programming** in Python: coroutines, `async`/`await`, and running many I/O-bound tasks concurrently with `asyncio`.

Tasks
-----

### 0. Basic async syntax

`wait_random(max_delay=10)` waits a random number of seconds using `asyncio.sleep` and returns the delay. Run from REPL or a script with `asyncio.run(wait_random())`.

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x01-python_async_function`
-   File: `0-basic_async_syntax.py`

### 1. Concurrent coroutines

`wait_n(n, max_delay)` runs `wait_random(max_delay)` n times concurrently (e.g. `asyncio.gather`) and returns the list of delays sorted. Run: `asyncio.run(wait_n(5, 6))` or use a main.

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x01-python_async_function`
-   File: `1-concurrent_coroutines.py`

### 2. Measure runtime

Measures total time to run four invocations of `wait_n(2, 5)` in parallel (~5s, not ~20s). Run: `python3 2-measure_runtime.py`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x01-python_async_function`
-   File: `2-measure_runtime.py`

### 3. Tasks

`task_wait_random(max_delay)` wraps `wait_random` in an `asyncio.Task` and returns that task. Used by `4-tasks.py`.

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x01-python_async_function`
-   File: `3-tasks.py`

### 4. Task wait n

`task_wait_n(n, max_delay)` runs n tasks (using `task_wait_random`) concurrently with `asyncio.gather` and returns sorted delays. Run: `asyncio.run(task_wait_n(4, 5))`

**Repo:**

-   GitHub repository: `alx-backend-python`
-   Directory: `0x01-python_async_function`
-   File: `4-tasks.py`

---

**How to do the exercises yourself**

1. **0:** Write `async def wait_random(max_delay=10)`, use `await asyncio.sleep(delay)`, return the delay.
2. **1:** Use `asyncio.gather()` (or a list of tasks) to run `wait_random` n times; sort the result list.
3. **2:** Create 4 coroutines that each call `wait_n(2, 5)`; measure time with `time.perf_counter()` before/after `asyncio.run(...)`.
4. **3:** Use `asyncio.create_task(wait_random(max_delay))` (or `Task`) and return the task.
5. **4:** Use the task from 3 in a loop or with gather; return sorted delays. Run with: `python3 2-measure_runtime.py` (and similar for others).
