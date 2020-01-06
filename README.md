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

## Check the Database Set Up

To check if the set up and teh data import was successfule, you should run three queries

```sql
show full tables;
select count(*) from film;
select count(*) from film_text;
```

and make sure that the results look like this

```sql
mysql> use sakila;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
mysql> show full tables;
+----------------------------+------------+
| Tables_in_sakila           | Table_type |
+----------------------------+------------+
| actor                      | BASE TABLE |
| actor_info                 | VIEW       |
| address                    | BASE TABLE |
| category                   | BASE TABLE |
| city                       | BASE TABLE |
| country                    | BASE TABLE |
| customer                   | BASE TABLE |
| customer_list              | VIEW       |
| film                       | BASE TABLE |
| film_actor                 | BASE TABLE |
| film_category              | BASE TABLE |
| film_list                  | VIEW       |
| film_text                  | BASE TABLE |
| inventory                  | BASE TABLE |
| language                   | BASE TABLE |
| nicer_but_slower_film_list | VIEW       |
| payment                    | BASE TABLE |
| rental                     | BASE TABLE |
| sales_by_film_category     | VIEW       |
| sales_by_store             | VIEW       |
| staff                      | BASE TABLE |
| staff_list                 | VIEW       |
| store                      | BASE TABLE |
+----------------------------+------------+
23 rows in set (0.00 sec)

mysql> select count(*) from film;
+----------+
| count(*) |
+----------+
|     1000 |
+----------+
1 row in set (0.00 sec)

mysql> select count(*) from film_text;
+----------+
| count(*) |
+----------+
|     1000 |
+----------+
1 row in set (0.00 sec)

mysql>
```

## Database Structure

This picture is the original from <https://dev.mysql.com/doc/sakila/en/sakila-structure.html> and shows the DB's structure:

![Sakila Database Structure](./sakila-schema.png)