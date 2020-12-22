# InnoDB Implicit Locks 

## How do the work in general 

  * Implicit locks are done by InnoDB itself 
  * We can only partly influence them. 
  
## Who wants what ? 

```
<who?, what?, how?, granted?>
```

## Explanation (a bit clumsy) 

  * IS and IX (intended share an intended write lock) 
  * IS and IX can be trigged on SQL
  * IX -> SUFFIX -> FOR UPDATE (this triggers a IX lock) 
  * IX and IS are the first step (on table layer) 
  * After that IX -> tries to get an write lock on row-level -> X 
  * Works unless there is another X 
  * IX and IS is not retrieved on TABLE spaced operations (construction --- alter) 

## Lock Type compability matrix 

```
    X           IX          S           IS
X   Conflict    Conflict    Conflict    Conflict
IX  Conflict    Compatible  Conflict    Compatible
S   Conflict    Conflict    Compatible  Compatible
IS  Conflict    Compatible  Compatible  Compatible
```


## The best explanation across the internet ;o) 

  * http://stackoverflow.com/questions/25903764/why-is-an-ix-lock-compatible-with-another-ix-lock-in-innodb|IX_and_IS-locks

```



```
