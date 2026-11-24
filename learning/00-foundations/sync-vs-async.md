# 00 — Synchronous vs Asynchronous Execution

**Status:** Learning (not yet assessed)  
**Prerequisites:** Basic Python function calls  
**Goal:** Explain the difference in your own words and run a small example.

## Plain-language meaning

- **Synchronous:** In a simple sequential example, the caller waits for an operation to finish before moving to the next instruction.
- **Asynchronous:** Code can suspend while awaiting an operation (typically I/O), letting other ready tasks make progress. It does **not** automatically imply multiple CPU instructions run in parallel.

**Intuition:** After ordering food, either stand at the counter until it's ready (waiting), or receive a token and use the waiting time for something else. The kitchen still needs time to prepare the food.

## First Python experiment: synchronous

```python
import time

def fetch_data(name):
    print(f"Start {name}")
    time.sleep(2)  # Simulates a blocking wait
    print(f"Finish {name}")

fetch_data("A")
fetch_data("B")
```

**Predict before running:** What order will the four lines print? About how many seconds total?

## Second experiment: asynchronous

```python
import asyncio

async def fetch_data(name):
    print(f"Start {name}")
    await asyncio.sleep(2)  # Simulates non-blocking waiting
    print(f"Finish {name}")

async def main():
    await asyncio.gather(fetch_data("A"), fetch_data("B"))

asyncio.run(main())
```

**Predict before running:** What order might the lines print? Roughly how long should it take? Why? Exact scheduling can vary.

## Important distinctions

- Calling an `async def` function creates a coroutine; it must be awaited or scheduled to run.
- `await` permits the current coroutine to suspend; it does not turn blocking code into non-blocking code.
- `time.sleep(2)` blocks the current thread; `await asyncio.sleep(2)` lets other asyncio tasks run.
- **Concurrency** means tasks can make progress over overlapping time; **parallelism** means simultaneous execution. We'll study these terms separately.

## Connection to AI systems

If an AI API call takes time to respond, a server may be able to serve other requests while that call is pending. Later we'll learn how this relates to HTTP, FastAPI, timeouts, retries, idempotency and durable queues.

## Evidence for completion

- [ ] Explain sync vs async in your own words without memorizing definitions.
- [ ] Predict and run both examples; note elapsed time and output order.
- [ ] Explain why `await asyncio.sleep` differs from `time.sleep`.
- [ ] Answer a scenario question about two independent API requests.
- [ ] Add a dated note or code commit with what surprised you.

**Current status:** Not verified. The lesson existing in this repo is not proof of mastery.
