# Beispiel zum Unix Timestamp 

## Was ist das ? 

  * Das Datum wird dargestellt als Sekunden seit 01.01.1970

## Warum ? 

  * Mit dem Unix Timestamp lassen sich einfache Vergleiche machen 
  * und Auswahlen treffen (z.B. Range - Abfrage) 

## Beispiele 

```
SELECT unix_timestamp('2022-01-04');
-- Datum auslesen und in unix timestamp umwandeln 
SELECT last_update,unix_timestamp(last_update) from actor;
-- Aktuelles Datum als unix timestamp (inkl Uhrzeit) - Systemzeit des Servers/Rechners 
-- Rechner auf dem MySQL - Server läuft 
select unix_timestamp();

-- Unix timestamp in einer Datum umwandeln 
SELECT from_unixtime('1648202962');

```

## Exercise 

```
Frage aus rental alle Datensätze ab beidenen
o Das return_date nicht null (NOT NULL) ist 
o Gib als einziges Feld das return_date umgewandelt zum Unix timestamp an. 
o HINT: UNIX_TIMESTAMP() 


```
