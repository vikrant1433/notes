## apache2
/etc/apache2/ports.conf file tells the ports on which apache is listening
`lsof -i` list open ports and the corresponding applications
`netstat -anp | grep apache` :You could see the listening port and PID from this if it's running.
apachectl -V to see the apache2 version
