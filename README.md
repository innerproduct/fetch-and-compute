# fetch-and-compute

## What is this project?
This is an experimental[^fantasy] project for trying to come up with a somewhat general-purpose framework[^isthatright] for serving computational jobs (perhaps in a job-list or job-queue) which can be decomposed into subtasks of the following character:

1. Long-running data fetching.
2. Some data-processing in python (perhaps in pandas or dask).
3. Potentially long-running computations in an external library.

It is **not** assumed that (1), (2), and (3) occur in that order or that they occur at-most once per job.

## What is the goal?
There are several goals:

1. The main goal is to serve jobs in a *cooperative-multitasking* manner using python's `asyncio` or similar to maximize utilization of computational-resources without unnecessary and lazy scaling to multiple workers.
2. Furthermore, the framework should provide a layer of abstraction for some common methods of fetching data from traditional or cloud-based databases or filestores. Similarly for some standard[^usefultome] compute or data-processing tasks.
3. The framework should provide logging and other features that would make the development and testing of these job-processors easier.

[^fantasy]: I have a dream.
[^isthatright]: Is `framework` the right term for what I describe?
[^usefultome]: I say `standard` but I just intend to make it useful for my own needs.
