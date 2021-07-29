# Optimizer Hints 

## Tell the optimizer what to do and what not to do 

  * https://dev.mysql.com/doc/refman/5.7/en/optimizer-hints.html#optimizer-hints-syntax

## This one is good for debugging / do not use index at all 

```

explain select vendor_city from contributions use index() where vendor_city like 'S%'

```
