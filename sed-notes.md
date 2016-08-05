## to replace only the first occurrence of a pattern in a file
sed '0,/pattern/s/pattern/replacement/' filename
e.g.
sed '0,/Apple/s/Apple/Banana/' filename
start at line 0, continue until you match 'Apple', execute the substitution in curly brackets
