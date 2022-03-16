# MariaDB / MySQL - Indizes 

## Prinzip 1: Nur ein Index pro Tabelle kann verwendet werden (i.d.R.)

  * Bei mehreren Indizes die für eine Tabelle gesetzt sind, kann i.d.R. (99 %) nur ein Index verwendet
  * Stehen mehrere zur Auswahl, entscheidet sich der Optimierer für den bestmöglichen (aus seiner Sicht) 

## Prinzip 2: Ein Index kann nur von links nach rechts gelesen werden 

```
# Kann einen Index verwenden 
select first_name,last_name from actor where last_name like 'B%';


# Kann keinen Index verwenden 
# Weil er nichts weiss, bei welchem Buchstaben er anfangen soll 
# Es kann A-Z sein. 
select first_name,last_name from actor where last_name like '%B%';

```
