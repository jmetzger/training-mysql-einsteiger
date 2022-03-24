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

```
