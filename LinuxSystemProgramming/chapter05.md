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
