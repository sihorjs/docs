# Shell script

Shell script begins with comment `#!/bin/sh`

## Escaping characters

-   `` ", `, \, $ `` are not escaped without backslash `\`;

## Built-in commands

-   `read` - takes input entered by user from terminal.
-   `[` or `test`.

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
