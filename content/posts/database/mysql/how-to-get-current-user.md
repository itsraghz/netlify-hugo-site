---
title: "How to Get the Current User Details"
date: 2021-06-13T11:22:15+05:30
draft: false
tags: ["Database", "MySQL"]
toc: true
---

# How to Get the Current User Details in MySQL

In this blog post, we will see the different ways we can get the currently logged in user in the 
MySQL Client inside the MySQL Session. 

It is good to verify the currently logged in user details with the host name, for certain authentication 
and authorization purposes. 

<!--more-->

# Way to get the current user

## Way 1 - Predefined `user()` function 

You can use the predefined function `user()` to get the currently logged in user with the MySQL Database server.

### Command Output

```sql
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 4
Server version: 10.1.13-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2016, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [itsraghz]> select user();
+-----------------+
| user()          |
+-----------------+
| raghs@localhost |
+-----------------+
1 row in set (0.00 sec)
```

## Way 2 - Predefined `current_user()` function

You can invoke a function without any parantheses if there are no parameters supplied to it. Hence, the invocation 
`current_user` and `current_user()` is the same. 

### Command Output 

```sql
MariaDB [itsraghz]> select current_user;
+-----------------+
| current_user    |
+-----------------+
| raghs@localhost |
+-----------------+
1 row in set (0.00 sec)

MariaDB [itsraghz]> select current_user();
+-----------------+
| current_user()  |
+-----------------+
| raghs@localhost |
+-----------------+
1 row in set (0.00 sec)
```

## Way 3 - Predefined `current_user()` function with `from dual` clause

You can also use the `from dual;` clause for the predefined functions, as it is one of the good/*standard practices*.

### Command Output 

```sql
MariaDB [itsraghz]> select current_user() from dual;
+-----------------+
| current_user()  |
+-----------------+
| raghs@localhost |
+-----------------+
1 row in set (0.00 sec)

MariaDB [itsraghz]>
```

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
13 Jun 2021 | Sun | 11 23 AM IST
