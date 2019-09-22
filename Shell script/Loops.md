# Loops

## For loop

```shell
#!bin/sh
for i in 1 2 3 4 5 # or any list of values without comma
do
  # body of loop
done
```

## While loop

Conditions:

-   `while [ val1 != val2 ]`
-   `while :` - always evaluated to true.
-   `while read VAR`
-   `` while i=`line` ``

```shell
#!bin/sh
while condition
do
    # body of loop
done
```

## If-else block

```shell
#!bin/sh
if condition
then
    # if-block body
elif condition; then
    # if-then body
else
    # body of else block, note without then keyword
fi
```

## Case

```shell
#!bin/sh
case value in
    a)
        # body a
        ;;
    b)
        # body b
        break
        ;;
    *)
        # default case
        ;;
esac
```
