---
title: "How to get the current time in MySQL"
date: 2021-06-13T14:16:51+05:30
draft: false
tags: ["Database", "MySQL"]
toc: true
---

# How to get the Current Server Time in MySQL

In this blog post, we will see how to get the current server time in the MySQL session.

<!--more-->

## Ways to get the time 

### Way 1 - use the predefined function `now()` 

We can use the `now()` function with the `select` statement to get the current serer time in the MySQL session.

### Command Output 

```sql
MariaDB [itsraghz]> select now();
+---------------------+
| now()               |
+---------------------+
| 2021-06-13 14:15:44 |
+---------------------+
1 row in set (0.00 sec)
```

### Way 2 - use the predefined function `now()` with the `from dual` clause

As a best / standard practice, we can add the `from dual` clause with the `select now()` statement. 

### Command Output 

```sql
MariaDB [itsraghz]> select now() from dual;
+---------------------+
| now()               |
+---------------------+
| 2021-06-13 14:15:50 |
+---------------------+
1 row in set (0.00 sec)

MariaDB [itsraghz]>
```

### Way 2 - with a meaningful column name in the output using `AS` clause

The default output column name comes with the name of the `function` unless it is modified explicitly. We can modify 
it via the `AS <Name>` clause. 

This way, we can have a short but meaningful name for a better understanding.

### Command Output

```sql
MariaDB [itsraghz]> select now() as "Current Server Time" from dual;
+---------------------+
| Current Server Time |
+---------------------+
| 2021-06-13 14:58:07 |
+---------------------+
1 row in set (0.01 sec)

MariaDB [itsraghz]>
```

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
25 May 2021 | Tue | 14 56 PM IST
