# mysql-client

## Basics 

```
mysql
mysql>

# Wie kommen wie raus ? 
exit; 

```

## Delimiter 
```
Normalerweise ";" 

Ist zum Trennen von Befehlen 
```

## Use user and password automatically 

```
nano /root/.my.cnf 
# BE CAREFUL EVERYBODY CAN LOGIN AS ROOT TO MYSQL NOW 
# in there
[mysql]
user=root
password=root-password-on-your-system 
