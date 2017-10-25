## Chapter 11: Time

* Real (wall) time vs process time vs monotonic time
* User time vs system time
* Absolute time vs relative time
* Epoch, software vs hardware clock, system timer, tick (jiffy), jiffies counter, HZ, `hwclock`
* Precision: second (`time_t`), microsecond (`timeval`), nanosecond (`timespec`)
* `tm, clock_t`, POSIX clocks, `clockid_t, clock_getres()`
* Getting and setting time: `time(), gettimeofday(), clock_gettime(), times()`, `date`, `stime(), settimeofdate(), clock_settime()`
* Converting time: `asctime(), asctime_r(), mktime(), ctime(), ctime_r(), gmtime(), gmtime_r(), localtime(), localtime_r(), difftime()`
* Tuning the system clock: slewing, `adjtime(), adjtimex()`
* Sleeping: `sleep(), usleep(), nanosleep(), clock_nanosleep()`, timer overruns
* Timers, delay, expiration, `alarm(), gettimer(), settimer(), timer_create(), timer_gettime(), timer_settime(), timer_getoverrun(), timer_delete()`
