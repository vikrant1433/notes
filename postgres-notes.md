to connect to remote postgres database
======
- `psql -h <host> -p <port> -u <database></port></host>`
psql -d mydb -U myuser -W
psql -h myhost -d mydb -U myuser -W
\du to display users
\dt to display the database tables and their respective owners
\z to list all the tables, views and sequences in the database
\conninfo to view the information about the current database connection type

