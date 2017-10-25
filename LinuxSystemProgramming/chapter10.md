## Chapter 10: Signals

* Signals, raising (sending, generating) signals, handling signals, signal actions (ignore, catch and handle, default action), signal name, signal number
* Linux signals: `SIGABRT, SIGALRM, SIGBUS, SIGCHLD, SIGCONT, SIGFPE, SIGHUP, SIGILL, SIGINT, SIGIO, SIGKILL, SIGPIPE, SIGPROF, SIGPWR, SIGQUIT, SIGSEGV, SIGSTKFLT, SIGSTOP, SIGSYS, SIGTERM, SIGTRAP, SIGTSTP, SIGTTIN, SIGTTOU, SIGURG, SIGUSR1, SIGUSR2, SIGVTALRM, SIGWINCH, SIGXCPU, SIGXFSZ`
* `signal(), pause(), sys_siglist, psignal(), strsignal()`, `kill`, `kill(), raise(), killpg()`
* Reentrancy, reentrant function, signal-safe
* Signal sets, `sigemptyset(), sigfillset(), sigaddset(), sigdelset(), sigismember(), sigisemptyset(), sigorset(), sigandset()`
* Critical regions, blocked signals, signal mask, `sigprocmask()`, pending signals, `sigpending(), sigsuspend()`
* `sigaction(), sigqueue()`
