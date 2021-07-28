# Performance - All fields/columns (*) vs specific columns 

```
# You need to set up contributions database to test that 
use contributions 

# Variant 1: ALL Fields 

mysql> select * from contributions limit 0,100000
100000 rows in set (0.25 sec)

# Variant 2: Specific field 
# Try this multiple times, because the first time it is not 
# in the innodb buffer (cache)

mysql> select vendor_last_name from contributions limit 0,100000;
100000 rows in set (0.04 sec)

# Result: Variant 2 wins over Variant 1 
# The difference between these 2 is factor 5x in my case 

```
