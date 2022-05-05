# Übung - Tabelle kurs anlegen 

## Schritt 1:

```
Tabelle 'kurs' anlegen mit dem Feld 

kurs_id 
  o smallint oder smallint(10) - Auswahl in MySQL workbench 
  o Haken bei PK (primary key - Primärschlüssel - nur 1x pro Tabelle möglich) 
  o Haken bei NN (not null, kurs_id immer gesetzt sein muss) 
  o Haken bei AI (Auto_increment - automatisches Hochzählen bei Anlage eines neuen Datensatzes)
  o Haken bei UN (Unsigned - d.h. nur positiver Wertbereich 0 bis ....)

# Warum smallint 
# Wir nehmen an, dass wir nicht mehr als 65000 kurs haben, jeder Kurs hat 
# eine eindeutige id, tinyint mit 0 bis 255 (unsigned wäre uns zu klein) 

Dann kommt -> Apply 

# Er zeigt mir dann das SQL-Statement an:
# Backticks macht er immer, brauchen wir aber nicht `
# nur benötigt wenn Leerzeichne im Tabellennamen -> ABER NICHT empfohlen.

CREATE TABLE `training`.`kurs` (
  `kurs_id` SMALLINT(10) UNSIGNED NOT NULL AUTO_INCREMENT,
  PRIMARY KEY (`kurs_id`));

Dann -> 2. Apply 


Dann -> Finish (Jetzt führt er es erst aus) 

```

## Schritt 2: Weitere Felder 


```
titel - varchar(60) - NOT NULL (NN) 
startdatum - DATE - NOT NULL (NN) - Default 2 
tage - TINYINT - NOT NULL (NN) 

```
