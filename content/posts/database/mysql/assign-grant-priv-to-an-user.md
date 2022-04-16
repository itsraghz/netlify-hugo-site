---
title: "Assign Grant Priviliges to an User in MySQL"
date: 2022-04-16T18:10:13+05:30
draft: false
tags:
  - Technical
  - Database
  - MySQL
toc: true
author: Raghs
---

# Assign Grant Priviliges to an User in MySQL Database

In this post, we will see how do we assign the *Grant* Privileges to a particular user, without which it is very difficult to assign a grant to an another user, and we need to always be dependent on the *root* user or the *DBA*. 

<!--more-->

Time to time, we might need to assign certain priviliges (like `SELECT`, `INSERT`, `CREATE`, `DROP` etc., ) to a DB user with which the user can conduct the business operations on the Database Schema. However, in order to assign these privileges, the user through which we are granting, should have the *GRANT* privileges in the first place, without which the DB will throw an error. 

```sql
ERROR 1045 (28000) at line 38: Access denied for user 'raghs'@'localhost' (using password: YES)
```
The statement on line # 38 in the SQL script was granting some privileges to a different user. 

## Verify the status of the `grant` priviliges to the user

We can verify the status of the `grant` privileges to the user, by issuing the following command. 

> *Note*: The privileges are stored in a table named `user` in the schema `mysql`.

```sql
MariaDB [(none)]> select Host, User, Grant_Priv from mysql.user where user='raghs';
+-----------+-------+------------+
| Host      | User  | Grant_Priv |
+-----------+-------+------------+
| localhost | raghs | N          |
+-----------+-------+------------+
1 row in set (0.00 sec)
```

## List out the privileges available 

We can see the list of available privileges by issuing the following command, again on the `mysql` schema. 

```sql 
MariaDB [(none)]> DESC mysql.db;
+-----------------------+---------------+------+-----+---------+-------+
| Field                 | Type          | Null | Key | Default | Extra |
+-----------------------+---------------+------+-----+---------+-------+
| Host                  | char(60)      | NO   | PRI |         |       |
| Db                    | char(64)      | NO   | PRI |         |       |
| User                  | char(80)      | NO   | PRI |         |       |
| Select_priv           | enum('N','Y') | NO   |     | N       |       |
| Insert_priv           | enum('N','Y') | NO   |     | N       |       |
| Update_priv           | enum('N','Y') | NO   |     | N       |       |
| Delete_priv           | enum('N','Y') | NO   |     | N       |       |
| Create_priv           | enum('N','Y') | NO   |     | N       |       |
| Drop_priv             | enum('N','Y') | NO   |     | N       |       |
| Grant_priv            | enum('N','Y') | NO   |     | N       |       |
| References_priv       | enum('N','Y') | NO   |     | N       |       |
| Index_priv            | enum('N','Y') | NO   |     | N       |       |
| Alter_priv            | enum('N','Y') | NO   |     | N       |       |
| Create_tmp_table_priv | enum('N','Y') | NO   |     | N       |       |
| Lock_tables_priv      | enum('N','Y') | NO   |     | N       |       |
| Create_view_priv      | enum('N','Y') | NO   |     | N       |       |
| Show_view_priv        | enum('N','Y') | NO   |     | N       |       |
| Create_routine_priv   | enum('N','Y') | NO   |     | N       |       |
| Alter_routine_priv    | enum('N','Y') | NO   |     | N       |       |
| Execute_priv          | enum('N','Y') | NO   |     | N       |       |
| Event_priv            | enum('N','Y') | NO   |     | N       |       |
| Trigger_priv          | enum('N','Y') | NO   |     | N       |       |
+-----------------------+---------------+------+-----+---------+-------+
22 rows in set (0.01 sec)
```

## Assign the grant privilege to the user 

Now let us execute the following SQL command to update the User privileges to have the *grant* privileges. 

> *Note*: It is better you can select the `mysql` schema so that you don't need to prefix the schema name in front of the table name everytime. 

```sql
MariaDB [(none)]> use mysql;
Database changed
```

```sql
MariaDB [mysql]> UPDATE `user` SET `Grant_priv` = 'Y' WHERE `user`.`Host` = 'localhost' AND `user`.`User` = 'raghs';
Query OK, 0 rows affected (0.00 sec)
Rows matched: 1  Changed: 0  Warnings: 0
```

Now, if we verify the status of privileges, we can see that it is properly set. 

```sql 
MariaDB [mysql]> select Host, User, Grant_Priv from mysql.user where user='raghs';
+-----------+-------+------------+
| Host      | User  | Grant_Priv |
+-----------+-------+------------+
| localhost | raghs | Y          |
+-----------+-------+------------+
1 row in set (0.00 sec)
```
> *Note*: Please note that we must *flush* the privileges for the settings to take an immediate effect. 

```sql
MariaDB [mysql]> flush privileges;
Query OK, 0 rows affected (0.00 sec)

MariaDB [mysql]> 
```

Now the user in question - *raghs* can assign any privileges to a different user, without any errors. 

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
16 Apr 2022 | Sat | 18:10:13 PM IST
