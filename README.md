# gnosh is a fuzzy CLI & GUI helper for GNOS

## Usage

### `Info` gathers spreaded information on files.

- Identifies target file by short pattern or shows all matches
- Supports *default* bash session **aliases & functions**
- Resolves **desktop entries**, symbolic links
- By default, crops to console width, use `-v` for detailed output

```
USAGE: i [-v] [PATH|PATTERN ...]
```

| Title  |              Description              |   Source   |
|--------|---------------------------------------|------------|
| `stat` | Inode number, Ownership & Permissions | `stat`     |
| `bits` | sticky bit, set-group-ID, set-user-ID | `test`     |
| `date` | Meta, Read & Write dates              | `stat`     |
| `real` | Canonical name                        | `readlink` |
| `hard` | hard links                            | `find`     |
| `size` | Byte count, On-disk size              | `stat`     |
| `file` | File type                             | `file`     |
| `mime` | Mime type                             | `xdg-mime` |
| `dpkg` | Original package name                 | `dpkg`     |
| `sha1` | Hash value                            | `sha1sum`  |

For directories:

| Title  |        Description         | Source |
|--------|----------------------------|--------|
| `fail` | unreadables + broken links | `find` |

For `.desktop` launchers:

| Title  |      Description       |   Source  |
|--------|------------------------|-----------|
| `name` | Desktop entry name     | `crudini` |
| `exec` | Executing command line | `crudini` |

For text files:

| Title  | Description | Source |
|--------|-------------|--------|
| `line` | Line count  | `wc`   |
| `head` | First line  | `head` |
| `foot` | Last line   | `tac`  |

For binaries/sockets:

| Title  |               Description               |   Source  |
|--------|-----------------------------------------|-----------|
| `libs` | Dynamic libraries                       | `ldd`     |
| `lsof` | Running instances PIDs, `sudo` required | `lsof`    |
| `sock` | Running instances PIDs, `sudo` required | `netstat` |

For different/supported fs files:

| Title  |     Description     |   Source   |
|--------|---------------------|------------|
| `flag` | ext2fs flags        | `lsattr`   |
| `attr` | extended attributes | `getfattr` |
| `phys` | FS type, mountpoint | `df`       |

### `Open` is a `.desktop` entries launcher, CLI to GUI helper

- Identifies target file by short pattern or shows all matches
- Supports *default* bash session **aliases & functions**
- Resolves **desktop entries**, symbolic links
- GUI Apps launched with `nohup` to keep clean console
- CLI Apps launched into GUI console, output kept & return code shown

```
USAGE: o [DRY] PATTERN
```

### `Seek` searches for matching binaries & `.desktop` launchers.

```
USAGE: s PATTERN
```

## Install

Just symlink `gnosh` script to `i`, `o` & `s` for handy usage.

`gnosh` is written for bash and requires the following binaries:

`crudini` `df` `dpkg` `file` `find` `getfattr` `head` `ldd` `lsattr` `lsof` `netstat` `readlink` `sha1sum` `stat` `tac` `test` `wc` `xdg-mime`
