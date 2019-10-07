# Strings

## Cut

`Cut` is used to extract substring from file. **Note**: `cut` start index of string is 1, not 0. Elements with start and end are included in substring.

Usage - `cut -[flag][value] [filename]`.

Flags:

-   `-c` - column - slice indices/index of substring.
-   `-d` - delimiter - character that splits string in array. Tab (`\t`) is default delimiter.
-   `-f` - field - slice index/indices of string tokens split by delimiter.
-   `--output-delimiter`.

Examples:

```bash
#!/bin/sh
cut -d"." -f5- test.txt # all fields from position 5
cut -c5,8 test.txt # only fifth and eighth character

read VAR
echo $VAR | cut -c-3 # reads user input and prints 1, 2 and 3 character
```
