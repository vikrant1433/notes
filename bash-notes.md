# To print a range of lines of a file
- `sed -n 'start_line_number, end_line_number p' input_file`
# to extract text between two strings
- `sed -n '/string1/,/string2/p' input_file`
- `-n` means do not print the lines by default
- `p` flag means print the lines only if pattern matches
# Bash notes
- `!!` - run the previous command
# to convert string in lower case
- echo "print $str.lower()" | python
- echo $str | sed 's/./\L&/g'
- echo $str:l (only in zsh)

