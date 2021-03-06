# InnoDB 

## Innodb buffer pool

  * How much data fits into memory 
  * Free buffers = pages of 16 Kbytes 
  * Free buffer * 16Kbytes = free innodb buffer pool in KByte  

## Find out size of innodb_buffer_pool_size 

```
# in bytes but free pages in pages (=16KBytes per page) 
SHOW VARIABLES LIKE 'innodb_buffer_pool_size';
```

## Find free buffer pool pages (linux style)

```
# grep befehl geht nur unter linux 
pager grep -i 'free buffers'
show engine innodb status \G
Free buffers       7905
1 row in set (0.00 sec)
```

## Find free buffer pool pages (Windows and Linux) 
```
# OR: 
MariaDB [(none)]> show status like '%free%';
+-------------------------------+---------+
| Variable_name                 | Value   |
+-------------------------------+---------+
| Innodb_buffer_pool_pages_free | 48083   |
| Innodb_buffer_pool_wait_free  | 0       |
| Innodb_ibuf_free_list         | 0       |
| Qcache_free_blocks            | 1       |
| Qcache_free_memory            | 1031304 |
+-------------------------------+---------+
5 rows in set (0.002 sec)
```

## Change innodb_buffer_pool_size 

```
# Windows change in my.ini 
# Linux my.cnf 50-server.cnf etc.
innodb_buffer_pool_size=3200M

# Server neu starten 
```

## Overview innodb server variables / settings 

  * https://dev.mysql.com/doc/refman/5.7/en/innodb-parameters.html

## Change innodb_buffer_pool 

```
# /etc/mysql/mysql.conf.d/mysqld.cnf 
# 70-80% of memory on dedicated mysql
[mysqld]
innodb-buffer-pool-size=6G

#
systemctl restart mysql

# 
mysql
mysql>show variables like 'innodb%buffer%';
```

## innodb_flush_method 

```
Ideally O_DIRECT on Linux, but please test it, if it really works well. 
```

## 	innodb_flush_log_at_trx_commit

```
When is fliushing done from innodb_log_buffer to log.
Default: 1 : After every commit 
-> best performance 2. -> once per second

# Good to use 2, if you are willing to loose 1 second of data on powerfail 
```

## innodb_flush_neighbors 

```
# on ssd disks set this to off, because there is no performance improvement 
innodb_flush_neighbors=0 

# Default = 1 

```

## skip-name-resolv.conf 

```
# work only with ip's - better for performance 
/etc/my.cnf 
skip-name-resolve
```

  * https://nixcp.com/skip-name-resolve/


## Ref:

  * https://dev.mysql.com/doc/refman/5.7/en/innodb-buffer-pool-resize.html
  

## Privilegs for show engine innodb status 

```
 show engine innodb status \G
ERROR 1227 (42000): Access denied; you need (at least one of) the PROCESS privilege(s) for this operation

```
