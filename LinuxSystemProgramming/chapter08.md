## Chapter 8: File and Directory Management

* inode, inode number, file metadata, `stat(), lstat(), fstat()`
* Permissions, `chmod(), fchmod()`
* Ownership, `chown(), lchown(), fchown()`
* Extended attributes (xattrs), MIME type sniffing
* xattrs namespaces (system, security, trusted, user)
* xattrs operations, `getxattr(), lgetxattr(), fgetxattr(), setxattr(), lsetxattr(), fsetxattr(), listxattr(), llistxattr(), flistxattr(), removexattr(), lremovexattr(), fremovexattr()`
* Directories, directory entry, link, subdirectory vs parent directory, root directory, pathname, absolute vs relative pathname
* Current working directory (cwd), `getcwd()`, `cd`, `chdir(), fchdir()`
* `mkdir(), rmdir()`
* Directory stream, `DIR, opendir(), readdir(), closedir()`
* Links, hard vs sym(bolic) (soft) links, link count vs usage count, link target, dangling symlinks, `link(), symlink()`, `fsck`
* Unlinking files, `unlink(), remove()`
* Copying and moving files, `cp, mv`, `rename()`
* Device nodes, major and minor number
* Special device nodes: `/dev/null, /dev/zero, /def/full`
* Random number generator, `/dev/random, /dev/urandom`, entropy pool
* Out-of-band communication, `ioctl()`
* Monitoring file events, inotify, watch, watch descriptor, watch mask, `inotify_init(), inotify_add_watch(), inotify_event, inotify_rm_watch()` 
