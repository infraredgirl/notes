## Chapter 7: Threading

* Binaries, processes, threads
* Single threaded vs multithreaded processes
* Virtualized memory, virtualized processor
* Pros and cons of multithreading
* Kernel-level (1:1) vs user-level (n:1) vs hybrid (n:m) threading
* Thread-per-conneciton vs event-driven threading
* Concurrency and parallelism
* Race conditions, critical regions, atomic operations
* Locks (mutexes); lock data, not code
* Deadlock, priority inversion, ABBA deadlock
* Pthreads, LinuxThreads, Native POSIX Thread Library (NTPL)
* libpthread, `-pthread` flag
* `pthread_create(), pthread_self(), pthread_equal(), pthread_exit(), pthread_cancel(), pthread_setcancelstate(), pthread_setcanceltype(), pthread_join(), pthread_detach(), pthread_mutex_lock(), pthread_mutex_unlock(), pthread_mutex_t`
* Thread ID, cancellation, cancellation state, type, points
* Global locks vs fine grained locking
