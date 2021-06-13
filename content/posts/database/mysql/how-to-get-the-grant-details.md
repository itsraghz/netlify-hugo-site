---
title: "How to get the Grant Details"
date: 2021-06-13T13:36:29+05:30
draft: false
tags: ["Database", "MySQL"]
toc: true
---

# How to get the Grant Details in MySQL

In this blog post, we will see how to get the privileges granted for a particular user, or the currently logged in 
user with the MySQL Database. 

A proper way to verify the privileges granted or revoked to an user, is a good practice for all the authorization activities.

<!--more-->

## Way 1 - Use `show grants`  statement

Using the `show` statement with the `grants` as an argument to get the privileges assigned to the currently logged in user. 

### Command Output

```sql
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 4
Server version: 10.1.13-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2016, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
MariaDB [itsraghz]> show grants;
+-----------------------------------------------------------------------------------------------------------------------+
| Grants for raghs@localhost                                                                                            |
+-----------------------------------------------------------------------------------------------------------------------+
| GRANT ALL PRIVILEGES ON *.* TO 'raghs'@'localhost' IDENTIFIED BY PASSWORD 'A Long Random Encoded String'              |
+-----------------------------------------------------------------------------------------------------------------------+
1 row in set (0.01 sec)
```
The string  `*.*` means the following.

* The first asterisk `*` indicates that for the databases. Here it indicates that the user is granted access for all the databases in the Database Server.
* The second asterisk `*` indicates the list of privileges. Here it indicates that the user is granted with all the privileges like `SELECT`, `INSERT`, `CREATE`, `ALTER`, `UPDATE` and `DELETE` etc., 

| Portion | Indication  | Reamrks  |
| ------- | ----------  | -------- | 
| `*`.*   | Databases   | User is granted access for all the databases in the Database Server |
| *.`*`   | Privileges  | User is granted with all the privileges like `SELECT`, `INSERT`, `CREATE`, `ALTER`, `UPDATE` and `DELETE` etc.,  |

> Note: It is always better to specify the selective privileges to the user, rather than the wildcard `*`, unless you are *very sure* of it. 

## Way 1 - `show grants` is *NOT* a function 

The `grants` is an argument to the `show` statement, and it is *NOT* a function. An attempt to use it as function will throw an error.

### Command Output 

```sql
MariaDB [itsraghz]> show grants();
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '()' at line 1
MariaDB [itsraghz]>
```
## Way 2 - Use `show grants for`  statement for the currently logged in user

Using the `show` statement with the `grants` as an argument with an additional `for` clause with for a specified user. 

We can use `current_user` OR `current_user()` to get the privileges assigned to the currently logged in user. 

### Command Output

```sql
MariaDB [itsraghz]> SHOW GRANTS FOR CURRENT_USER;
+-----------------------------------------------------------------------------------------------------------------------+
| Grants for raghs@localhost                                                                                            |
+-----------------------------------------------------------------------------------------------------------------------+
| GRANT ALL PRIVILEGES ON *.* TO 'raghs'@'localhost' IDENTIFIED BY PASSWORD 'A_Long_Encoded_String_Of_Password'         |
+-----------------------------------------------------------------------------------------------------------------------+
1 row in set (0.00 sec)

MariaDB [itsraghz]> SHOW GRANTS FOR CURRENT_USER();
+-----------------------------------------------------------------------------------------------------------------------+
| Grants for raghs@localhost                                                                                            |
+-----------------------------------------------------------------------------------------------------------------------+
| GRANT ALL PRIVILEGES ON *.* TO 'raghs'@'localhost' IDENTIFIED BY PASSWORD 'A_Long_Encoded_String_Of_Password'         |
+-----------------------------------------------------------------------------------------------------------------------+
1 row in set (0.00 sec)

MariaDB [itsraghz]>
```

## Way 3 - Use `show grants for`  statement for the specified user

Using the `show` statement with the `grants` as an argument with an additional `for` clause with for a specified user. 

We can specify the user of our interest in the format `username`@`host` to get the privileges assigned to that particular user. 

### Command Output

We will get the privileges to the same user `raghs`@`localhost` by explicitly specifying it in the `show grants for` statement. 

```sql
MariaDB [itsraghz]> SHOW GRANTS FOR 'raghs'@'localhost';
+-----------------------------------------------------------------------------------------------------------------------+
| Grants for raghs@localhost                                                                                            |
+-----------------------------------------------------------------------------------------------------------------------+
| GRANT ALL PRIVILEGES ON *.* TO 'raghs'@'localhost' IDENTIFIED BY PASSWORD 'A_Long_Encoded_String_Of_Password'         |
+-----------------------------------------------------------------------------------------------------------------------+
1 row in set (0.00 sec)
```

### Command Output

We will get the privileges to the *root* user as `root`@`localhost` by explicitly specifying it in the `show grants for` statement. 

```sql
MariaDB [itsraghz]> SHOW GRANTS FOR 'root'@'localhost';
+----------------------------------------------------------------------------------------------------------------------------------------+
| Grants for root@localhost                                                                                                              |
+----------------------------------------------------------------------------------------------------------------------------------------+
| GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' IDENTIFIED BY PASSWORD 'A_Long_Encoded_String_Of_Password' WITH GRANT OPTION         |
| GRANT PROXY ON ''@'%' TO 'root'@'localhost' WITH GRANT OPTION                                                                          |
+----------------------------------------------------------------------------------------------------------------------------------------+
2 rows in set (0.00 sec)

MariaDB [itsraghz]>
```

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
13 Jun 2021 | Sun | 13 06 PM IST
