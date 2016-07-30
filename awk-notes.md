## awk notes
- `ARGC` stores the count of number of arguments
- `NF` number of columns (fields)
- `NR` number of lines (records)
- `OFS` output fields separator, default value is space
- `ORS` output record separator, default value is newline
- `RS` input record separator, default value is newline
- `RLENGTH` length of matched string
- `$n` nth field in the current record
# redirection
```bash
BEGIN {
    print "hello , world" > "/tmp/test.txt"
}
```
```bash
BEGIN {
    print "hello , world" > "/tmp/test.txt"
}
```

# pipe
```awk
BEGIN {
    print "hello, world" | "tr [a-z] [A-Z]"
}
```
* output\* HELLO, WORLD
# pass arguments to awk
`awk -v name='vikrant'` 
```bash
awk -v var='hello' '
BEGIN {
    print var; # no $ is required in front of var
}
'
```
# to show value of all global variables
`awk --dump-variables ''`
`cat awkvars.out`
