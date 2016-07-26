## sed
* `-r` : using extended regular expressions  so that you don’t have to escape some of the regular expression characters (if you’re curious, they are `?+(){}`)
* 
## to copy file from one server to another using third pc 
* scp -3 username1@remote_ip1:/path/to/src/  username2@remote_ip2:/path/to/destination/
## permissions for ~/.ssh directory
* The .ssh folder: 700 (drwx------)
* The public key: 644 (-rw-r--r--)
The private key: 600 (-rw-------)
## to print the full path of a file
* `readlink -f filename`
## to exlude subfolders while copy a directory
- rsync -arvu --exclude=/R1/A R1 /tmp/R7 : this will exclude R1/A subdirectory if leading /(slash) is not there then any subfolder name A will get excluded
## to update LS_COLORS
- `wget https://raw.github.com/trapd00r/LS_COLORS/master/LS_COLORS -O $HOME/.dircolors`
short link for tx.sh on mars
======
- http://bit.do/tx-sh

short link for connect_iitb
======
- http://bit.do/i-sh
to check if have sudo permissions
=======
```bash
if [ $(sudo -v | grep -c "sudo") -eq 0 ]; then
    echo "don't have sudo rights exiting..."
    exit
fi
```
to check if a package is installed or not
==========
```bash
if [  $(dpkg-query -W -f='${Status}' package_name 2>/dev/null | grep -c "ok installed") -eq 0 ]; then
    echo "package_name not installed"
fi
```
rsync
=====
- -z : used for compression
- -q : quiet 
- -v : verbose
-------------
to run a script at startup
=====
- `crontab -e`
- `@reboot /full/path/to/script.sh`
to install ohmyzsh
=====
- `sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
to run zsh first wizard
=====
- `autoload -U zsh-newuser-install`
- `zsh-newuser-install -f`
----------
- to display size of a directory `du --summarize --human-readable`
- to execute a command repeatedly use `crontab -e` command to open crontab file 
> minute(0-59) hour(0-23) day(1-31) month(1-12) weekday(0-6) command
- use * for repeat the selected duration
e.g. if 
For example, let’s say we want to run the command `/usr/bin/example ` at 12:30 a.m. every day. We’d type:
> 29 0 * * * /usr/bin/example
We use 29 for the 30-minute mark and 0 for 12 a.m. because the minute, hour and weekday values start at 0. Note that the day and month values start at 1 instead of 0.
Multiple Values and Ranges
Use comma-separated values to specific multiple times. For example, the line
0,14,29,44 * * * * /usr/bin/example2
runs /usr/bin/example2 at the 15-minute mark on every hour, every day. Make sure you add each new task on a new line.
Use dash-separated values to specify a range of values. For example, the line
0 11 * 1-6 * /usr/bin/example3
runs `/usr/bin/example3 `at noon every day, but only in the first six months of the year.

to exclude some files while diffing two directories
d
`iff -x '*.foo' -x '*.bar' -x '*.baz' /destination/dir/1 /destination/dir/2`

to delete all empty files or directories
`find /path/to/dir -empty -type d -delete`
`find /path/to/dir -empty -type f -delete`
to limit the find to only 1 level 
find /path/to/dir -maxdepth 1 -empty -type f -print

-s = file exists AND not zero bytes
To delete nth line in a file
sed -i '5d' file.txt
if [[ -s file ]]; then
do something
fi
[ -e filepath ] Returns true if file exists.
[ -x filepath ] Returns true if file exists and executable.

To search exact word
grep -w word file
To find all the symlinks which points to a folder
find -L /dir/to/start -xtype l -samefile /path/to/original_folder 2>/dev/null
-L - Follow symbolic links.
-xtype l - File is symbolic link
-samefile name - File refers to the same inode as name. When -L is in effect, this can include symbolic links.
fg # put the most recent suspended job in foreground
jobs	# show the list of suspended jobs

to give an alias to an ip address:
write ip address followed by a space then the alias name in /etc/hosts file
127.0.0.1	localhost
127.0.1.1	vikrant
10.15.29.123 room

to add host in .ssh/config file
touch ~/.ssh/config 
Host anu
        Hostname 10.129.26.239
        User anupreet
Host testbed
        Hostname 10.129.5.155
        User testbed
Host *
        ForwardX11 yes

to start / stop apache server on ubuntu 16.04
sudo systemctl stop apache2.service
sudo systemctl start apache2.service

To keep a small password for user in ubuntu
sudo passwd user
- How to change shell to zsh
- chsh -s $(which zsh)

To repair hp wifi driver on ubuntu
====
- `sudo add-apt-repository ppa:hanipouspilot/rtlwifi` 
- `sudo apt-get update` 
- `sudo apt-get install rtlwifi-new-dkms linux-firmware`
- Then restart your system

If windows is not showing in grub menu after dual boot installation of windows and ubuntu run below commands on the ubuntu terminal. No need to boot to live ubuntu.
=====
- `sudo add-apt-repository ppa:yannubuntu/boot-repair &&`
- `sudo apt-get update &&`
- `sudo apt-get install -y boot-repair &&`
- `boot-repair`

To copy files from remote host:
=======
- `scp  username@remote_ip_address:path destination_path`
- E.g `scp vikrant@10.15.29.121:/home/Download/a.txt /home/nivia/Download`
```bash
    if [ ! -f /tmp/foo.txt ]; then 
    echo "File not found!" 
    fi
```

How to read line by line in bash
while IFS='' read -r line || [[ -n "$line" ]]; do
    echo "$line"
done < "$1"

-r is used to prevent treating backslash as a special character
IFS=’ ‘ is used to prevent striping leading/trailing spaces
|| [[ -n $line ]] prevents the last line from being ignored if it doesn't end with a \n (since read returns a non-zero exit code when it encounters EOF).

In bash there should not be any space when assigning a value to a variable.
E.g. a=”correct”
       a= “wrong”

In bash
basename give the folder name without full path
E.g. a=”\tmp\folder_name”
->basename $a
->folder_name
How to get the last field with cut:
echo $a | rev | cut -d'/' -f1 | rev

rev : command will reverse the line. Last field become the first field and reverse again to get the field.

In makefile:
$$? Give the return value of the previous command ran
Use - in front of command to suppress the command errors 
E.g. 
test2:
	@./a.out < input2.txt > out_ref 
	-@diff -wBy --suppress-blank-empty output2.txt out_ref1 >/dev/null ;\

To run bash command inside makefile write all commands in one single line separated by semicolon ;
	E.g. 

test2:
```make
	@./a.out < input2.txt > out_ref 
	-@diff -wBy --suppress-blank-empty output2.txt out_ref1 >/dev/null ;\
	if [ $$? -eq 0 ] ; then \
		echo "${green}TEST CASE#2 PASS${reset}" ; \
	fi ;\
		echo "${red}TEST CASE#2 FAILED${reset}" ; \
		echo "input:" ;\
		cat input2.txt ;\
		echo "-----------------------------------------------------------------------" ;\
		echo "expected output                    			  your output" ;\
		echo "-----------------------------------------------------------------------" ;\
		diff -wBy --suppress-blank-empty output2.txt out_ref1 ;\
```
Program to generate all possible combination of n elements choosing k at a time.
http://stackoverflow.com/a/12992511/1685263

In bash removing shortest match pattern from the front of the string 
${var#pattern}
E.g. var=”1234567”;
```bash
echo ${var#123} 		# 4567
echo ${var#12*5}		#67
```
To remove pattern from the back use % instead of #
echo ${var%567}		# 1234
echo ${var%4*7}		#123
For longest match use ## and %%
var=”0123456701234567”
```bash
echo ${var##0*4}		# 567
echo ${var%%4*7}		# 0123
```
Finding and replacing string in bash
Replace only first match
${var/pattern/replacement}
var=”0123456789”
echo ${var/123/hello}		#0hello456789
Replace all the matches
${var//pattern/replacement}

To match the pattern with the starting of the string use # after / 
${var/#pattern/replacement}
echo ${var/#123/hello} 		#0123456789
To match the pattern with the ending of the string use % after / 

Extract a Substring from a Variable inside Bash Shell Script
${var:position}
Extract substring from $var at position start_pos
${var:start_position:offset}
If offset is +ve: extract the string from start_pos (0 base indexing) to start_position + offset
If offset is -ve: extract the string from start_pos (0 base indexing) to length - |offset|
```bash
var=”123456”
echo ${var:0}				# 123456
echo ${var:1}				# 23456
echo ${var:0:3}			# 123
echo ${var:0:-1}			#12345
echo ${var:2:-2}			#34
```
In bash multiline string is made using heredoc
Example

Var = `cat << EOM
Line1
Line2
EOM
`
echo “$Var”

Note: Use double quotes to preserve the newline in the string.

In bash $? Is the return value of the previous command
In bash (()) double parenthesis are arithmetic expression:
((var++))
In bash ${VAR##PATERN} will remove the pattern from front of the variable
In bash ${VAR%%PATERN} will remove the pattern from back of the variable
In c++:
lower_bound(ForwardIterator first, ForwardIterator last, value)

 lower_bound returns a pointer to the first value in range [first, last) >= value in the sorted vector v

 Whereas upper_bound returns a pointer to the first value in range [first, last) > value.
To compile c++ program with c++14:
g++ file.cpp -std=c++1y
To convert string to lower case in bash shell:
tr
$ echo "$a" | tr '[:upper:]' '[:lower:]' hi all
AWK
$ echo "$a" | awk '{print tolower($0)}' hi all
Bash 4.0
$ echo "${a,,}" hi all

Not null in bash 
If [ -n $a ]; then
	body
If

To make virtual environment with python3
mkvirtualenv -p python3 <env_name>

To clear dmesg:
sudo dmesg -C

Search multiple words:
grep -e word1 -e word2 file
Show the changes continuosly in nth line of file:
watch -n1 -d "head -n12 /proc/interrupts | tail -1"
To continuously watch changes in a file: use watch command
watch -d -n1 cat file_name.txt

To print nth line of file use:
sed 'NUMq;d' file
How to download with axel?
axel -avn 50 download_url
To save wget download file with different name
wget google.com -O foo.html

#### To display size of a directory
- `du --summarize --human-readable`
- to disable mysql `sudo systemctl disable mysql`
- to enable mysql `sudo systemctl enable mysql`

