## Chapter 9: Memory Management

* Memory allocation, process virtual address space, pages, page size, valid vs invalid page, paging in/out, page fault
* Data sharing between processes, copy-on-write (COW)
* Memory regions (mappings, areas): text segment, stack, data segment (heap), bss segment, `pmap`
* Dynamic memory, `malloc(), calloc(), realloc(), free()`
* Memory leak, use-after-free error, use-before-initialized error, dangling pointer
* Data alignment, n-byte alignment, natural alignment, `posix_memalign()`
* Data segment, heap, break, `brk(), sbrk()`
* Buddy memory allocation scheme, internal and external fragmentation, anonymous memory mapping, `mmap(), munmap()`
* `mallopt()`, fast bins, memory poisoning, padding, `malloc_usable_size(), malloc_trim()`
* `MALLOC_CHECK_, mallinfo(), malloc_stats()`
* Stack-based allocations, `alloca(), strdupa(), strndupa()`, variable-length array (VLA)
* `memset(), memcmp(), memmove(), memcpy(), memccpy(), mempcpy(), memchr(), memrchr(), memmem(), memfrob()`
* Demand paging, locking pages, `mlock(), mlockall(), munlock(), munlockall(), RLIMIT_MEMLOCK, mincore()`
* Opportunistic allocation, overcommitment, out-of-memory (OOM) condition, OOM killer, `/proc/sys/vm/overcommit_memory, /proc/sys/vm/overcommit_ratio`, strict accounting
