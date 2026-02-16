# 0x01. Python — Async

This project introduces **asynchronous programming** in Python: coroutines, `async`/`await`, and running many I/O-bound tasks concurrently with `asyncio`.

---

## What does each file do?

Each answer is the **problem the file solves** and how to run it.

---

### **What does `0-basic_async_syntax.py` do?**  
It defines the simplest async function: `wait_random(max_delay=10)` that waits a random number of seconds (between 0 and `max_delay`) using `asyncio.sleep` and returns the delay. You learn the basic `async def` and `await` syntax.  
**Run:** Run from REPL or a small script that calls `asyncio.run(wait_random())`.

### **What does `1-concurrent_coroutines.py` do?**  
It defines `wait_n(n, max_delay)`: run `wait_random(max_delay)` **n times concurrently** (e.g. with `asyncio.gather` or multiple tasks) and return the list of delays **sorted**. So you see that total time is about one max_delay, not n times it.  
**Run:** Call from a script with `asyncio.run(wait_n(5, 6))` or use a main.

### **What does `2-measure_runtime.py` do?**  
It measures the **total elapsed time** to run four invocations of `wait_n(2, 5)` in parallel. It demonstrates that running them concurrently takes about ~5 seconds (one batch), not ~20 seconds (if they were sequential).  
**Run:** `python3 2-measure_runtime.py`

### **What does `3-tasks.py` do?**  
It defines `task_wait_random(max_delay)`: a function that **wraps** the `wait_random` coroutine in an `asyncio.Task` and returns that task. You learn the difference between a coroutine and a scheduled task.  
**Run:** Used by `4-tasks.py`; you can run a small script that creates a task and awaits it.

### **What does `4-tasks.py` do?**  
It defines `task_wait_n(n, max_delay)`: run **n tasks** (using `task_wait_random` from `3-tasks.py`) concurrently with `asyncio.gather` and return the **sorted** list of delays. Same idea as `1-concurrent_coroutines` but using the task factory.  
**Run:** Run from script or REPL with `asyncio.run(task_wait_n(4, 5))`.

---

## How to do the exercises yourself

1. **0:** Write `async def wait_random(max_delay=10)`, use `await asyncio.sleep(delay)`, return the delay.
2. **1:** Use `asyncio.gather()` (or a list of tasks) to run `wait_random` n times; sort the result list.
3. **2:** Create 4 coroutines that each call `wait_n(2, 5)`; measure time with `time.perf_counter()` before/after `asyncio.run(...)`.
4. **3:** Use `asyncio.create_task(wait_random(max_delay))` (or `Task`) and return the task.
5. **4:** Use the task from 3 in a loop or with gather; return sorted delays.
