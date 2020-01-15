# Arrays

## Creating

```bash
array[index]=item

# More explicit way
declare -a array=(item1 item2)
```

## Reading

```bash
# Display all elements in console
echo ${array[@]}

array_length=${#array[@]}
array_element_length=${#array[index]}

# Read from StdIn
array=($(cat))
# Read from file
filecontent=( `cat "file" `)
```

## Manipulation

```bash
# Slicing
array_slice=${ARRAY[@]:start_index:slice_length}
array_element_slice=${ARRAY[index]:start_index:slice_length}


array_replace=${ARRAY[@]/search_string/replace_string}

# Adding new element
array=(element1, element2)
array=("${array[@]}" element3)

# Remove element
unset array[index] # Sets element on selected position to null
array=(${array[@]:0:index} ${array[@]:$((index + 1))})

# Delete array
unset array

# Concatenation of arrays
array=("${array1[@]}" "${array2[@]}")
```
