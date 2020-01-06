# Sakila Sample Database

## Download and Installation

Download the [archive](https://downloads.mysql.com/docs/sakila-db.tar.gz) with the SQL scripts and unpack it. Reade the expanantion in (<https://downloads.mysql.com/docs/sakila-en.a4.pdf)> and (<https://dev.mysql.com/doc/sakila/en/>).

Then run the two commands

```bash
oofenloch@teben:~/workspaces/mysql/sakila$ mysql `cat ~/.mysql/oofenloch@localhost` < sakila-schema.sql 
mysql: [Warning] Using a password on the command line interface can be insecure.
oofenloch@teben:~/workspaces/mysql/sakila$ mysql `cat ~/.mysql/oofenloch@localhost` < sakila-data.sql 
mysql: [Warning] Using a password on the command line interface can be insecure.
oofenloch@teben:~/workspaces/mysql/sakila$ 
```

For this to work, the file `~/.mysql/oofenloch@localhost` must contain a single line like this
```bash
oofenloch@teben:~/workspaces/mysql/sakila$ cat ~/.mysql/oofenloch@localhost
-uoofenloch -pbah2vouRUa9Lu7Ie
oofenloch@teben:~/workspaces/mysql/sakila$
```
with a valid user (oofenloch in this example) and a valid password (bah2vouRUa9Lu7Ie in this example). Of course, the user needs the proper privileges.

## Database Structure

This picture is the original from <https://dev.mysql.com/doc/sakila/en/sakila-structure.html> and shows the DB's structure:

![Sakila Database Structure](./sakila-schema.png)