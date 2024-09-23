Handy tools for development on FujiNet:

* backtrace - given the hex dump strack trace will print the backtrace with source files and line numbers
* search - will search the source code or ESPIDF source for strings
* debug_version.py - embed current commit ID into firmware without modifying repo

To use debug_version.py, add to the `[env]` section in `platformio.local.ini`:

    [env]
    build_flags += !python3 debug_version.py
