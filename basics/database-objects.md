# Datenobjekte 

## Was sind Datenbankobjekte 

```
Bilden eine Strutkur um Daten zu speichern 
```

## Welche gibt es ? 

### Ebene 1 (oberste Ebene) Datenbank (databases/schemas) 

```
eine Organisationseinheit: die Datenbank 
wie ein Behältnis 
unter der Haube: Verzeichnis 

z.B. Datenbank sakila
```

### Ebene 2 - Tabellen 

```
Eine Datenbank kann mehrere Tabellen haben. 
Ähnlich eines Vorratsschrankes. 
Im Filesystem finden man diese unterhalb der Datenbank mit 
dem entsprechenden der Tabelle:
z.B. sakila\actor.ibd 

Jede Tabelle hat eine Struktur -> Columns (Felder) 

```

### Ebene 3 - Felder / Columns 

```
Die Tabelle hat eine Struktur, die bestimmt wird durch die Columns (Felder) 
Jedes Feld (Column) hat einen Datentyp, der bestimmt welcher Daten dort rein dürfen.
z.B. Strings (varchar), oder Zahlen (z.B. INT -> Integer) 

```
