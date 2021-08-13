# Hat InnoDB noch freien Speicher (pages) 

## Variante 1 

```
SHOW STATUS LIKE '%pages_free%';
```

## Variante 2:

```


mysql>pager free;
mysql>show engine innodb status;
mysql>pager;


```
