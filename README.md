# ALX Backend — Python

## Description

Backend Python track: variable annotations, async/await, and unit/integration testing. Each folder is a separate project. This README explains **what each file does** and **how to run the exercises** so you can follow or redo them yourself.

## Structure

* [0x00. Python - Variable annotations](./0x00-python_variable_annotations)
* [0x01. Python - Async](./0x01-python_async_function)
* [0x02. Python - Async comprehension](./0x02-python_async_comprehension)
* [0x03. Unittests and integration tests](./0x03-Unittests_and_integration_tests)

| Folder | Topic | What you'll practice |
|--------|--------|----------------------|
| [0x00-python_variable_annotations](./0x00-python_variable_annotations) | Variable annotations | Type hints, `typing` module |
| [0x01-python_async_function](./0x01-python_async_function) | Async basics | `async`/`await`, coroutines, `asyncio` |
| [0x02-python_async_comprehension](./0x02-python_async_comprehension) | Async comprehensions | Async generators, `async for` |
| [0x03-Unittests_and_integration_tests](./0x03-Unittests_and_integration_tests) | Testing | `unittest`, mocking, fixtures, integration tests |

---

## 0x00 — Python variable annotations

**Problem:** Code is clearer and tools (IDEs, mypy) can catch type errors when you annotate function parameters and return types. This project practices writing type-annotated functions and using the `typing` module.

### Files and what they solve

| File | Problem solved | How to run |
|------|----------------|------------|
| `0-add.py` | Add two floats with type hints | `python3 0-main.py` |
| `1-concat.py` | Concatenate two strings (annotated) | `python3 1-main.py` |
| `2-floor.py` | Floor a float and return int (annotated) | `python3 2-main.py` |
| `3-to_str.py` | Convert float to string (annotated) | `python3 3-main.py` |
| `4-define_variables.py` | Define annotated variables (int, float, bool, str) | `python3 4-main.py` |
| `5-sum_list.py` | Sum a list of floats (annotated) | `python3 5-main.py` |
| `6-sum_mixed_list.py` | Sum a list of ints and floats | `python3 6-main.py` |
| `7-to_kv.py` | Build (key, value²) tuple from str and int/float | `python3 7-main.py` |
| `8-make_multiplier.py` | Return a multiplier function (annotated) | `python3 8-main.py` |
| `9-element_length.py` | Annotate function that returns list of lengths | `python3 9-main.py` |
| `100-safe_first_element.py` | Safely return first element of a sequence (Union) | `python3 100-main.py` |
| `101-safely_get_value.py` | Safely get value from dict with default (typing) | `python3 101-main.py` |
| `102-type_checking.py` | Use conditionals for type narrowing (import) | `python3 102-main.py` |

### Doing the exercises yourself

1. Open the task file (e.g. `5-sum_list.py`) and read the docstring.
2. Implement the function with the correct type annotations (`typing.List`, `-> float`, etc.).
3. Run the corresponding `*-main.py` to see expected behavior.
4. Use `mypy` if available: `mypy 5-sum_list.py`.

---

## 0x01 — Python async (coroutines)

**Problem:** I/O-bound work (network, sleep) can block the program. Async lets you run many such tasks concurrently without threads. This project introduces `async`/`await` and `asyncio`.

### Files and what they solve

| File | Problem solved | How to run |
|------|----------------|------------|
| `0-basic_async_syntax.py` | Simplest async function: `wait_random` (random delay) | `python3 0-main.py` (or run and call from REPL) |
| `1-concurrent_coroutines.py` | Run `n` coroutines concurrently with `wait_n` | Run via main or REPL |
| `2-measure_runtime.py` | Measure total time for running 4× `wait_n` in parallel | Run script to see ~4s (not 16s) |
| `3-tasks.py` | Wrap coroutine in `asyncio.Task` (task_wait_random) | Used by `4-tasks.py` |
| `4-tasks.py` | Run `n` tasks concurrently and return sorted delays | Run to see concurrent execution |

### Doing the exercises yourself

1. **0:** Write an `async def` that `await asyncio.sleep(...)` and returns the delay.
2. **1:** Use `asyncio.gather()` or a list of tasks to run `wait_random` n times; return sorted delays.
3. **2:** Create 4 tasks that each run `wait_n(2, 5)`; measure time—should be ~5s, not ~10s.
4. **3–4:** Use `asyncio.create_task()` (or `Task`) and `asyncio.gather()`; ensure results are sorted.

Run with: `python3 2-measure_runtime.py` (and similar for others).

---

## 0x02 — Python async comprehension

**Problem:** You want to iterate over async streams (e.g. async generators) with a compact syntax. This project uses async comprehensions and async generators.

### Files and what they solve

| File | Problem solved | How to run |
|------|----------------|------------|
| `0-async_generator.py` | Async generator yielding 10 random floats (1s apart) | Run and iterate with `async for` |
| `1-async_comprehension.py` | Collect 10 numbers from `async_generator` using async comprehension | Run script |
| `2-measure_runtime.py` | Run 1-async_comprehension 4 times in parallel; measure ~10s | `python3 2-measure_runtime.py` |

### Doing the exercises yourself

1. **0:** `async def async_generator()` with `yield` and `await asyncio.sleep(1)`.
2. **1:** `[x async for x in async_generator()]` (or equivalent).
3. **2:** Use `asyncio.gather()` to run the comprehension coroutine 4 times and measure total time.

---

## 0x03 — Unittests and integration tests

**Problem:** You need to verify that utilities and the GitHub org client behave correctly without hitting the real GitHub API. This project teaches unit tests (with mocks) and integration tests (with fixtures).

### Provided files (do not change)

| File | Role |
|------|------|
| `utils.py` | `access_nested_map`, `get_json`, `memoize` — used by the client and tested in isolation |
| `client.py` | `GithubOrgClient`: fetches org and repos from GitHub API (you test it with mocks) |
| `fixtures.py` | Sample API payloads for integration tests |

### Files you write / extend

| File | Problem solved |
|------|----------------|
| `test_utils.py` | Unit tests for `access_nested_map` (normal + KeyError), `get_json` (mock requests.get), `memoize` (mock method, assert called once) |
| `test_client.py` | Unit tests for `GithubOrgClient` (org, _public_repos_url, public_repos, has_license) and integration tests using `fixtures.py` |

### Concepts by task

- **Parameterized tests:** Use `@parameterized.expand` to run the same test with different inputs (e.g. different `nested_map`/`path`).
- **Mocking HTTP:** Patch `requests.get` so `get_json` returns a fixed payload; assert URL and return value.
- **Mocking a property:** Patch `GithubOrgClient.org` (memoized property) to control what `_public_repos_url` returns.
- **Integration:** Use fixtures to mock `requests.get` per URL and assert `public_repos` and `public_repos(license="apache-2.0")` match expected lists.

### Running tests

```bash
cd 0x03-Unittests_and_integration_tests
python3 -m unittest test_utils.py
python3 -m unittest test_client.py
# Or run a specific test class/method
python3 -m unittest test_utils.TestAccessNestedMap.test_access_nested_map
```

### Doing the exercises yourself

1. Read `utils.py` and `client.py`; run them in the REPL to understand behavior.
2. Implement `TestAccessNestedMap` with `@parameterized.expand` for success and KeyError cases.
3. Implement `TestGetJson`: patch `requests.get`, check URL and that return value equals test payload.
4. Implement `TestMemoize`: patch the inner method and assert it’s called once when the memoized property is accessed twice.
5. In `test_client.py`, add tests for `org`, `_public_repos_url`, `public_repos`, `has_license`, then integration tests with `fixtures.py`.

---

## General requirements (all projects)

- Python 3.7+, Ubuntu 18.04 LTS style environment.
- First line: `#!/usr/bin/env python3`.
- Style: pycodestyle (2.5).
- Docstrings on modules, classes, and functions; type annotations on functions/coroutines where required.

---

## Quick reference: run by project

```bash
# Variable annotations (example)
cd 0x00-python_variable_annotations && python3 5-main.py

# Async
cd 0x01-python_async_function && python3 2-measure_runtime.py
cd 0x02-python_async_comprehension && python3 2-measure_runtime.py

# Tests
cd 0x03-Unittests_and_integration_tests && python3 -m unittest discover
```

Each subfolder has its own `README.md` with more task details; use this README as a map of **what each file is for** and **how to run and redo the exercises**.
