# Shell script

Shell script begins with comment `#!/bin/sh`.

External programs can be executed in backticks. They run in subshell and don't affect parent shell.

## CLI arguments

-   `$0` - basename of shell script.
-   `$@` - arguments of program.
-   `$1, $2, $3` - first three parameters. Can use up to 9 arguments.
-   `$#` - number of arguments.
-   `$$` - PID of current shell.
-   `$?` - exit code of last COMMAND (including if-block etc).

## Escaping characters

-   `` ", `, \, $ `` are not escaped without backslash `\`.

## Functions

-   There is only global scope of functions.
-   Can be recursive.
-   Cannot modify own arguments ($1, $2 etc), but can change global variables.

Example:

```bash
#!/bin/sh
VARIABLE=value

func()
{
    # body of function processing value
    $VARIABLE=$1
    return $VARIABLE
}

# Calling
func random
```

## Reuse functions and variables via sourcing

Example:

```bash
# common.lib - file with common functions that doesn't spawn new shell

# common.lib
# body of common.lib

# script.sh - Consumer of common.lib

#!/bin/sh
# script.sh
. ./common.lib
# body of script.sh
```

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
