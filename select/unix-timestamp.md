# Beispiel zum Unix Timestamp 

## Was ist das ? 

  * Das Datum wird dargestellt als Sekunden seit 01.01.1970

## Warum ? 

  * Mit dem Unix Timestamp lassen sich einfache Vergleiche machen 
  * und Auswahlen treffen (z.B. Range - Abfrage) 

## Beispiele 

```
# Datum auslesen und in unixtime stamp umwandeln 
select last_update,unix_timestamp(last_update) from actor;

# Unix Timestamp in Datum umwandeln 


```
