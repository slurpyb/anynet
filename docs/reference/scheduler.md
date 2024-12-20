
# Module: <code>anynet.scheduler</code>

Provides a class that schedules events after a certain amount of time.

<code>**async with create**() -> [Scheduler](#scheduler)</code><br>
<span class="docs">Creates a scheduler. All events are canceled when the context manager exits.</span>

## Scheduler
<code>**def start**() -> None</code><br>
<span class="docs">Begins executing scheduled events. Call this after `schedule()` or `repeat()`.</span>

<code>**def schedule**(function: Callable, delay: float, \*args) -> int</code><br>
<span class="docs">Schedules an asynchronous function call after `delay` seconds. Returns a handle that can be passed to `remove()`.</span>

<code>**def repeat**(function: Callable, delay: float, \*args) -> int</code><br>
<span class="docs">Schedules an asynchronous function call after `delay` seconds. The call is repeated every `delay` seconds. Returns a handle that can be passed to `remove()`.</span>

<code>**def remove**(handle: int) -> None</code><br>
<span class="docs">Cancels an event. Does nothing if `handle` is invalid.</span>

<code>**def remove_all**() -> None</code><br>
<span class="docs">Cancels all events.</span>
