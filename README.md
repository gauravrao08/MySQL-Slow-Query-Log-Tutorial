# MySQL-Slow-Query-Log-Tutorial

```
mysql -u root -p

SET GLOBAL slow_query_log = 'ON';

show global variables like '%slow%';
+---------------------------+-----------------------------------+
| Variable_name             | Value                             |
+---------------------------+-----------------------------------+
| log_slow_admin_statements | OFF                               |
| log_slow_slave_statements | OFF                               |
| slow_launch_time          | 2                                 |
| slow_query_log            | ON                                |
| slow_query_log_file       | /var/lib/mysql/localhost-slow.log |
+---------------------------+-----------------------------------+
```

```
vim /etc/my.cnf

slow-query-log = 1
slow-query-log-file=/var/lib/mysql/localhost-slow.log
```

systemctl restart mysqld

```
mysql -u root -p

> select sleep (10);
> exit
```
cat /var/lib/mysql/localhost-slow.log
