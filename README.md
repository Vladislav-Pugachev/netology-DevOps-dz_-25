## 1.

```commandline
mysql> \s
--------------
mysql  Ver 8.0.28 for Linux on x86_64 (MySQL Community Server - GPL)

```

```commandline
mysql> select count(*) from orders where price > 300;
+----------+
| count(*) |
+----------+
|        1 |
+----------+
1 row in set (0.00 sec)
```


## 2.

```commandline
mysql> select * from information_schema.user_attributes where User="test";
+------+-----------+---------------------------------------+
| USER | HOST      | ATTRIBUTE                             |
+------+-----------+---------------------------------------+
| test | localhost | {"fname": "James", "lname": "Pretty"} |
+------+-----------+---------------------------------------+
1 row in set (0.00 sec)

```
## 3.

```commandline
mysql> select engine from information_schema.TABLES where table_schema='testdb';
+--------+
| ENGINE |
+--------+
| InnoDB |
+--------+
1 row in set (0.00 sec)

```

```commandline
mysql> alter table orders engine = innodb;
Query OK, 5 rows affected (0.26 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> alter table orders engine = myisam;
Query OK, 5 rows affected (0.08 sec)
Records: 5  Duplicates: 0  Warnings: 0


|       16 | 0.25955725 | alter table orders engine = innodb                                                   |
|       17 | 0.08719525 | alter table orders engine = myisam                                                   |
+----------+------------+--------------------------------------------------------------------------------------+
quit


```

## 4.
```commandline
[mysqld]
pid-file        = /var/run/mysqld/mysqld.pid
socket          = /var/run/mysqld/mysqld.sock
datadir         = /var/lib/mysql
secure-file-priv= NULL
innodb_buffer_pool_size     = 6144M
innodb_compression_level    = 9
innodb_log_buffer_size      = 1048576
innodb_buffer_pool_size     = 2566914048
innodb_log_file_size        = 104857600
innodb_flush_log_at_trx_commit = 0
```
