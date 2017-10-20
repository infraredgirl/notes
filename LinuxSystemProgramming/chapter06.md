## Chapter 6: Advanced Process Management

* Process scheduler, runnable process vs blocked process
* Multitasking OSs: preemptive vs cooperative, timeslices, yielding
* Processor-bound vs I/O-bound processes
* Completely Fair Scheduler (CFS), fair scheduling, target latency, switching costs, minimum granularity
* Yielding the processor, `sched_yield()`
* Process priorities, nice values, `nice(), getpriority(), setpriority()`
* I/O priority, `ionice`
* Migrating a process, load balancing, processor affinity, soft vs hard affinity, `sched_getaffinity(), sched_setaffinity()`
* Real-time systems, operational deadlines, hard vs soft real-time systems, latency, jitter
* Scheduling policies (classes): FIFO, RR, normal, batch (idle)
* Static priority, `sched_getscheduler(), sched_setscheduler(), sched_getparam(), sched_setparam(), sched_get_priority_min(), sched_get_priority_max(), sched_rr_get_interval()`
* `chrt`
* Deterministic actions, prefaulting data and locking memory to prevent swapping, dedicating processors to real-time processes to avoid multitasking
* Resource limits, `getrlimit(), setrlimit()`, soft limit vs hard limit
* `RLIMIT_AS, RLIMIT_CORE, RLIMIT_CPU, RLIMIT_DATA, RLIMIT_FSIZE, RLIMIT_LOCKS, RLIMIT_MEMLOCK, RLIMIT_MSGQUEUE, RLIMIT_NICE, RLIMIT_NOFILE, RLIMIT_NPROC, RLIMIT_RSS, RLIMIT_RTTIME, RLIMIT_RTPRIO, RLIMIT_SIGPENDING, RLIMIT_STACK`

