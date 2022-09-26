---
sort: 8
---

# Threads

*Format:* `threads: int`

*Example:* `threads: 4`

*Default*: `-1`

Jekyll Picture tag will run all image generation inside a parallel threadpool
(specifically [`Concurrent::ThreadPoolExecutor`](https://ruby-concurrency.github.io/concurrent-ruby/1.1.4/Concurrent/ThreadPoolExecutor.html)
to improve performance. The behavior for any non-positive number (the default)
is twice the number of CPU's, as much of the image generation is I/O bound.
Setting a value of `0` will disable threading, and instead perform generation
in a [`Concurrent::ImmediateExecutor`](https://ruby-concurrency.github.io/concurrent-ruby/1.1.4/Concurrent/ImmediateExecutor.html).
The recommended behavior is the default automatic behavior - the number of
threads should be reduced (or threading disabled) only on systems with
significant memory restrictions.