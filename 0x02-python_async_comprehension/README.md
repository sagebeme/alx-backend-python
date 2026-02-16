# 0x02. Python — Async Comprehension

This project practices **async generators** and **async comprehensions**: producing and consuming streams of values asynchronously with `async for` and `[x async for x in ...]`.

---

## What does each file do?

Each answer is the **problem the file solves** and how to run it.

---

### **What does `0-async_generator.py` do?**  
It defines an **async generator** `async_generator()` that yields 10 random floats (between 0 and 10), waiting 1 second between each yield using `await asyncio.sleep(1)`. You learn how to write a function that uses `yield` inside an `async def`.  
**Run:** Use from a script with `async for value in async_generator(): print(value)` inside an async function, then `asyncio.run(main())`.

### **What does `1-async_comprehension.py` do?**  
It defines a coroutine that **collects** all 10 values from `async_generator()` using an **async list comprehension**: `[x async for x in async_generator()]`, and returns that list. You learn the syntax for consuming an async generator into a list.  
**Run:** Run a script that does `asyncio.run(async_comprehension())` and prints the list.

### **What does `2-measure_runtime.py` do?**  
It runs the async comprehension from `1-async_comprehension.py` **four times in parallel** (e.g. with `asyncio.gather`) and measures the total time. Because the generator yields every second, running 4 in parallel still takes about 10 seconds total (not 40), demonstrating concurrency.  
**Run:** `python3 2-measure_runtime.py`

---

## How to do the exercises yourself

1. **0:** In `async def async_generator()`, loop 10 times: `await asyncio.sleep(1)`, then `yield random.uniform(0, 10)`. Return type hint: `AsyncGenerator[float, None]` or `Generator` from typing.
2. **1:** Define an async function that returns `[x async for x in async_generator()]`.
3. **2:** Use `asyncio.gather` to run the comprehension coroutine 4 times; measure time with `time.perf_counter()`; print the duration (should be around 10 seconds).
