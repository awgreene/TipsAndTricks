# Tips for Bash

## Request user input then do something
```
read -r -p "Some questions (option/options): " response
```

## case insensitive comparison
```
if [ "${response,,}" != 'y' ]; then
  # code
fi
```

## Check that dir exists
```
dir=someDir
if [ -d "$dir" ]; then
  # Code
else
  # Code
fi
```i

## Check that a file exists
```
if [ -e $file ]; then
  # Code
else  
  # Code
fi
```

## For each line in path
```
# Create the new file based based off template
  while read -r -u 3 line; do
    # Do something with $line
  done 3< $file
```

## Split string on delimiter
```
IFS=': ' read -r key value <<< "$string"

```
