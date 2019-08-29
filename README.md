# path.janet

Simple path manipulation module for Janet. Supports manipulation both
windows and posix paths on any platform, and provides functions that
work according to the current host platform.

All functions have three forms, under `path`, `path/win`, and `path/posix`. The prefix
indicates which type of path the function manipulates.

```clojure
(import path)

# Examples for a non-windows system, use path/win/ for windows and
# path/posix/ for posix.

(path/ext "my/long/path.txt") # -> ".txt"
path/sep # -> "/" on posix, "\\" on windows
path/delim # -> ":" on posix, ";" on windows
(path/basename "some/path.txt") # -> "path.txt"
(path/parts "some/path/file.txt") # -> ["some" "path" "file.txt"]
(path/normalize "some/.././thing/file.txt") # -> "thing/file.txt"
(path/join "some/path" "../thing/file.txt") # -> "some/thing/file.txt"
(path/abspath? "/home/blah") # -> true
(path/abspath "file.txt") # -> "/home/me/cwd/file.txt"
```

## Installation

```
[sudo] jpm install https://github.com/janet-lang/path.git
```

## License

Licensed under the MIT License.
See LICENSE for details.
