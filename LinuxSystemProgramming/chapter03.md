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
