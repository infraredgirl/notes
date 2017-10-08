# Linux System Programming

Notes taken while reading the book [Linux System Programming](http://shop.oreilly.com/product/0636920026891.do).

## Chapter 1: Introduction and Essential Concepts

* System software vs application software
* Kernel
* Core system libraries
* System calls vs library calls/functions
* Execution modes: kernel mode vs user mode
* Kernel space vs user space
* libc, glibc
* gcc
* API, ABI
* UNIX standards: POSIX, SUS
* C standards: K&R, ANSI, ISO
* Files, file descriptors
* Regular files vs special files
* File offset, file length, truncation
* inode, filenames, directories, pathname resolution
* Absolute vs relative pathnames, current working directory
* Hard links vs symlinks
* Specials files: character device files, block device files, named pipes, socket files
* Namespace of files, filesystems, (un)mounting, mount points, root filesystems, virtual filesystems, network filesystems, device partitions, sectors, blocks
* Processes, executable format (ELF), sections (text, data, bss)
* Process resources, process descriptors
* Threads, single-threaded vs multithreaded processes, Pthreads
* pid, process tree, init process, `fork()` system call, parent/child processes, waiting on a terminated process, zombie processes
* Users, uid
* Usernames, `/etc/passwd`
* Login program, login shell
* root
* Real uid, effective uid, saved uid, filesystem uid
* Groups, gid
* Primary group, supplemental groups, `/etc/group`
* Real gid, effective gid, saved gid, filesystem gid
* Permissions, owning user, owning group
* Permission bits (`r`,`w`,`x`)
* Access control lists (ACLs)
* Signals, signal handlers, async-signal-safe function
* IPC mechanisms (pipes, named pipes, semaphores, message queues, shared memory, futexes)
* Error handling, `errno`, error value (-1), `perror()`, `strerror()`
* Error codes: `E2BIG, EACCES, EAGAIN, EBADF, EBUSY, ECHILD, EDOM, EEXIST, EFAULT, EFBIG, EINTR, EINVAL, EIO, EISDIR, EMFILE, EMLINK, ENFILE, ENODEV, ENOENT, ENOEXEC, ENOMEM, ENOSPC, ENOTDIR, ENOTTY, ENXIO, EPERM, EPIPE, ERANGE, EROFS, ESPIPE, ESRCH, ETXTBSY, EXDEV`


## Chapter 2: File I/O

* File table, file descriptors
* stdin, stdout, stderr
* `open()`
  * access mode flags: `O_RDONLY, O_WRONLY, O_RDWR`
  * other flags: `O_APPEND, O_ASYNC, O_CLOEXEC, O_CREAT, O_DIRECT, O_DIRECTORY, O_EXCL, O_LARGEFILE, O_NOATIME+, O_NOCTTY, O_NOFOLLOW, O_NONBLOCK, O_SYNC, O_TRUNC`
  * mode: `S_IRWXU, S_IRUSR, S_IWUSR, S_IXUSR, S_IRWXG, S_IRGRP, S_IWGRP, S_IXGRP, S_IRWXO, S_IROTH, S_IWOTH, S_IXOTH`
* umask
* `creat()`
* `read()`, nonblocking reads
* `write()`, nonblocking writes, writeback, write ordering, maximum buffer age
* Synchronized I/O: `fsync(), fdatasync(), sync()`
* Direct I/O: `O_DIRECT`
* `close()`
* `lseek()`
  * `origin` argument: `SEEK_CUR, SEEK_END, SEEK_SET`
* holes, sparse files
* `pread(), pwrite()`
* `ftruncate(), truncate()`
* Multiplexed I/O: `select(), pselect(), poll(), ppoll()`
* Virtual filesystem
* Page cache, temporal locality vs sequential locality, pruning vs swapping, readahead
* Page writeback, flusher threads


## Chapter 3: Buffered I/O

* Blocks
* User-buffered I/O
* `dd`
* `stat`
* Buffer size
* stdio
* File pointers
* Input stream, output streams
* `fopen(), fdopen()`
  * `mode` argument: `r, r+, w, w+, a, a+`
* `fclose(), fcloseall()`
* `fgetc(), ungetc(), fgets(), fread()`
* `fputc(), fputs(), fwrite()`
* `fseek(), fsetpos(), rewind()`
  * `whence` argument for `fseek(): SEEK_CUR, SEEK_END, SEEK_SET`
* `ftell(), fgetpos()`
* `fflush()`
* `ferror(), feof(), clearerr()`
* `fileno()`
* Types of user buffering: unbuffered, line-buffered, block-buffered (full buffering)
* `setvbuf()`
  * `mode` argument: `_IONBF, _IOLBF, _IOFBF`
* Thread-safety, locking
* `flockfile(), funlockfile(), ftrylockfile()`
* Unlocked stream operations: `fgetc_unlocked()`, etc


## Chapter 5: Process Management

* Binaries (programs), processes, process resources, threads
* pid, idle process, init process
* System boot
* pid allocation
* Process hierarchy: parent, child, ppid, owning user/group, process group
* `getpid(), getppid()`
* Running a new process: `fork()` + `exec()`
* Exec family: `execl(), execlp(), execle(), execv(), execvp(), execve()`
* `fork()`, copy-on-write, `vfork()`
* Terminating a process: `exit()`, return from `main()`, `SIGTERM` or `SIGKILL`, killed by kernel for illegal operation
* `atexit(), on_exit()`
* `SIGCHLD`
* Zombie processes, waiting on processes, `wait()`, status macros (`WIFEXITED, WIFSIGNALED, WIFSTOPPED, WIFCONTINUED, WEXITSTATUS, WTERMSIG, WSTOPSIG, WCOREDUMP`), `waitpid(), waitid()`
* `system()`
* Orphan processes
* Real, effective and saved user/group IDs
* `setuid(), setgid(), seteuid(), setegid(), getuid(), getgid(), geteuid(), getegid()`
* Process groups, pgid, process group leader, sessions
* `setsid(), getsid(), setpgid(), getpgid()`
* Deamons


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
