# Shell script

Shell script begins with comment `#!/bin/sh`.

## CLI arguments

-   `$0` - basename of shell script.
-   `$@` - arguments of program.
-   `$1, $2, $3` - first three parameters. Can use up to 9 arguments.
-   `$#` - number of arguments.

## Escaping characters

-   `` ", `, \, $ `` are not escaped without backslash `\`.

## Built-in commands

-   `read` - takes input entered by user from terminal.
-   `[` or `test`.
-   `shift` - removes argument of script. Can be called with integer to remove multiple args.

## Wildcards

### Logical:

-   `*` - selects all values.
-   `&& \` - AND condition that moved to next line.
-   `||`

### For integers:

-   `-eq` - numeric equality.
-   `-ne` - numeric inequality.
-   `-lt` - less than.
-   `-le` - less than or equal.
-   `-gt` - greater than.
-   `-ge` - greater than or equal.

### For strings:

-   `-n` - non-zero length string.
