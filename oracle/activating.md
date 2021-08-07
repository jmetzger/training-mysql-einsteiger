# Activating Oracle SQL-Mode 

```
# ACTIVATE GLOBALLY (for complete server) - not persistent 
# if you want to activate it globally 
# this will not be available in the current session though 
mysql>SET GLOBAL sql_mode='ORACLE'
mysql> SELECT @@GLOBAL.sql_mode -- available globally 
mysql> SELECT @@sql_mode -- in session. not present yet.

# FOR THE session to be active, either reconnect or set it explicitly 
mysql>SET sql_mode='ORACLE'
mysql>SELECT @@sql_mode 
```
