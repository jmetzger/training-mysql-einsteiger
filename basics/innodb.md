# InnoDB 

## InnoDB Structure 

![InnoDB Structure](/images/InnoDB-Structure.jpg)


## Innodb buffer pool

  * How much data fits into memory 
  * Free buffers = pages of 16 Kbytes 
  * Free buffer * 16Kbytes = free innodb buffer pool in KByte  
```
pager grep -i 'free buffers'
show engine innodb status \G
Free buffers       7905
1 row in set (0.00 sec)
```

## Overview innodb server variables / settings 

  * https://dev.mysql.com/doc/refman/5.7/en/innodb-parameters.html

## Change innodb_buffer_pool 
