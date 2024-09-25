Handy tools for development on FujiNet:

* backtrace - given the hex dump strack trace will print the backtrace with source files and line numbers
* search - will search the source code or ESPIDF source for strings
* debug_version.py - embed current commit ID into firmware without modifying repo

To use debug_version.py, add to the `[env]` section in `platformio.local.ini`:

    [env]
    build_flags += !python3 debug_version.py

Also make sure your include/version.h has the `_VERSION_H` guard:

    diff --git a/include/version.h b/include/version.h
    index e57ce2b9..62925799 100644
    --- a/include/version.h
    +++ b/include/version.h
    @@ -7,6 +7,9 @@
      as needed.
     */

    +#ifndef _VERSION_H
    +#define _VERSION_H
    +
     #define FN_VERSION_MAJOR 1
     #define FN_VERSION_MINOR 4

    @@ -15,3 +18,5 @@
     #define FN_VERSION_DATE "2024-08-07 20:49:13"

     #define FN_VERSION_FULL "v1.4"
    +
    +#endif /* _VERSION_H */
