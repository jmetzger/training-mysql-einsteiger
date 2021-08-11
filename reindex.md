# Index neu organisieren / Statistik 

```
# Aus meiner Sicht sollte das auch so für die aktuelle MariaDB Version 10.6 gelten 

For basic cleanup and re-analyzing you can run "OPTIMIZE TABLE ...", it will compact out the overhead in the indexes and run ANALYZE TABLE too, but it's not going to re-sort them and make them as small & efficient as they could be.

https://dev.mysql.com/doc/refman/8.0/en/optimize-table.html

However, if you want the indexes completely rebuilt for best performance, you can:

drop / re-add indexes (obviously)
dump / reload the table
ALTER TABLE and "change" using the same storage engine
REPAIR TABLE (only works for MyISAM, ARCHIVE, and CSV)
https://dev.mysql.com/doc/refman/8.0/en/rebuilding-tables.html

If you do an ALTER TABLE on a field (that is part of an index) and change its type, then it will also fully rebuild the related index(es).



```
