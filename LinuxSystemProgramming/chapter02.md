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
