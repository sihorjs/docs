# Variables

## Declaring and reading variables

All variables values are stored as strings.

Example of creation and reading variable:

```bash
#!/bin/sh
# Declaring
VARIABLE="Some value"
# Reading value
echo $VARIABLE
```

## Accessing of variables in other parts of program

-   To access variable in other shell script, use `export`. After its running variable left unchanged.
-   Every script spawns own interactive shell. To run script inside current environment use `.` command. In this case shell can change values created variables outside it.

Example:

```bash
#!/bin/sh
VAR=5
# Assume that script.sh changes VAR to 10
. ./script.sh
# Prints 10
echo $VAR
```

## Default values

To assign default value to variable use `:=` or `:-` operator.

Example:

```bash
#!/bin/sh
read VAR
echo "${VAR:=Default value}"
```

## Escaping variables

Variables can be escaped with backticks and curly brackets - `${VAR}`.

Example:

```bash
#!/bin/sh
VAR=5
echo "This is ${VAR}"
```
