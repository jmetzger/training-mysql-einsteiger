# Slow query log 

## Schritt 1: slow_query_log permanent aktivieren 

```
# Minimal 
# my.ini /my.cnf 
slow-query-log 
 

# Server neu starten. 
```

## Schritt 2: was ist eine langsame Query ? (long_query_time) 

```
# jeder query die >= long_query_time ist, wird geloggt. 
# z.B. 0.000001 Sekunden oder langsamer 
# Setzen das während der Laufzeit (serverweit)
SET GLOBAL lonq_query_time = 0.000001
# und zusätzlich für die aktuelle Session 
SET lonq_query_time = 0.000001

```

## Wo ist das slow query log zu finden ? 

```
Datenverzeichnis von MariaDB 
{HOSTNAME}-slow.log 
z.B. 
ITSLAB101-slow.log 
# Datei lässt sich mit Editor öffnen 

```

## Wie kann ich mehr Ausgaben in jeden Eintrag bekommen ? 

```
# oder direkt in my.ini / my.cnf 
SET GLOBAL log_slow_verbosity='query_plan,explain';
SET log_slow_verbosity='query_plan,explain';

```
