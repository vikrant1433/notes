# Determine the path of the executing BASH script 
MY_PATH="`dirname \"$0\"`"              # relative
MY_PATH="`( cd \"$MY_PATH\" && pwd )`"  # absolutized and normalized
if [ -z "$MY_PATH" ] ; then
  # error; for some reason, the path is not accessible
  # to the script (e.g. permissions re-evaled after suid)
  exit 1  # fail
fi
echo "$MY_PATH"

 To print a range of lines of a file
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

