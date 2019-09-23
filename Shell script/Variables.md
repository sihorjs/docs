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
