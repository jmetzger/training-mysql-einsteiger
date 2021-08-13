# Hat InnoDB noch freien Speicher (pages) 

## Variante 1 

```
SHOW STATUS LIKE '%pages_free%';
```

## Variante 2:

```

MariaDB [sakila]> pager grep "Free buffer";
PAGER set to 'grep "Free buffer"'
MariaDB [sakila]> show engine innodb status;
Free buffers       0
1 row in set (0.001 sec)



```
