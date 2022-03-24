# Werden events ausgeführt ? 

## Wir überprüfen in den Server System Variablen, ob events aktiviert sind 

```
# Server System Variablen
# Welche Einstellungen in der Konfiguration während der Laufzeit 

```

 * https://dev.mysql.com/doc/refman/8.0/en/server-system-variable-reference.html

## Konkret: Welche ist 

```
-- variante 1
show variables like '%event%';
-- variante 2
show variables like 'event_scheduler';
-- variante 3 
select @@event_scheduler 

'event_scheduler', 'ON'


MySQL 8  - event_scheduler per default eingeschaltet. 
https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_event_scheduler

MySQL 5.7 (und früher: Erfahrung des Trainers) 
https://dev.mysql.com/doc/refman/5.7/en/server-system-variables.html#sysvar_event_scheduler


# Abschalten in MySQL 5.7 und früher (wenn ihr es während der Laufzeit deaktiviert, ist es
# beim nächsten Start wieder aktiv
SET GLOBAL event_scheduler=OFF 

# Abschalten (speziell MySQL 8) 
SET GLOBAL event_scheduler=OFF;
SET PERSIST event_scheduler=OFF;
SELECT @@event_scheduler;

```


```
