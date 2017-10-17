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
