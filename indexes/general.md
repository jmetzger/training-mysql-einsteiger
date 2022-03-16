# MariaDB / MySQL - Indizes 

## Prinzipien 

### Prinzip 1: Nur ein Index pro Tabelle kann verwendet werden (i.d.R.)

  * Bei mehreren Indizes die für eine Tabelle gesetzt sind, kann i.d.R. (99 %) nur ein Index verwendet
  * Stehen mehrere zur Auswahl, entscheidet sich der Optimierer für den bestmöglichen (aus seiner Sicht) 

### Prinzip 2: Ein Index kann nur von links nach rechts gelesen werden 

```
# Kann einen Index verwenden 
select first_name,last_name from actor where last_name like 'B%';


# Kann keinen Index verwenden 
# Weil er nichts weiss, bei welchem Buchstaben er anfangen soll 
# Es kann A-Z sein. 
select first_name,last_name from actor where last_name like '%B%';

```

## Indizes - Typen 

### Primary 
  
  * eindeutig, darf nur 1x pro Tabelle 1x erstellet 
  * Darf nur in den Daten in einer Zeile vorkommen, d.h. es gibt nur eine Zeile mit der actor_id = 1

### Unique 

  * wenn ich einen weiteren eindeutigen Schlüssel haben möchte, kann ich auf eine Spalte einen Unique-Key setzen
  * Dann der Wert auch nur in einer Datenzeile für diese Spalte vorkommen 

### Index 

  * Ganz normaler Index 
  * Werte dürfen mehrmals vorkommen 
