## Chapter 4: Advanced File I/O

* Scatter/gather (vectored) I/O vs linear I/O
* Segment, vector
* `readv(), writev()`
* Event poll (epoll) vs select and poll
* `epoll_create1(), epoll_ctl(), epoll_wait()`
* Level-triggered vs edge-triggered watch
* Memory mapping of files, memory pages, page size, readahead
* `mmap(), sysconf(), getpagesize(), munmap(), mremap(), mprotect(), msync(), madvise()`
* `posix_fadvise(), readahead()`
* Synchronous vs asynchronous operations
* Synchronized vs non-synchronized operations
* Asynchronous I/O: `aio_read(), aio_write(), aio_error(), aio_return(), aio_cancel(), aio_fsync(), aio_suspend()`
* Disk seek, I/O scheduler
* Disk addressing, CHS addressing, cylinders, heads, sectors, platters, tracks
* Physical (device) blocks vs logical (filesystem) blocks, LBA (logical block addressing)
* Merging and sorting of I/O requests, read latency, writes-starving-reads problem
* I/O schedulers: Linus elevator, Deadline scheduler, Anticipatory scheduler, CFQ scheduler, Noop scheduler
* Solid-state drives (SSDs)
* Configuring I/O scheduler
  * `iosched` kernel parameter (options `as, cfq, deadline, noop`)
  * `/sys/block/[device]/queue/scheduler`, `/sys/block/[device]/queue/iosched`
* User space scheduling: sorting by path, inode, physical block
* `stat(), ioctl()`