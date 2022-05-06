# MySQL Einsteiger 

## Agenda 

  1. Technischer Hintergrund / Allgemeines 
     * [Wofür brauche ich MySQL - Anwendungsbeispiele](/technical-background/projects.md)
     * [Technical Structure](/technical-background/basics.md)
     * [Was ist SQL ?](/technical-background/sql.md)
     * [Excel vs. MySQL](/technical-background/excel-vs-mysql.md)
     * [Wie starte ich ? (Windows: MYSQL -Server/Workbench - Installation)](/installation-mysql-windows-8.md)
     * [Installation osx (Mac)](/installation-mysql-osx.md)
     
  1. Grundlagen 
     * [Was sind Datenobjekte und welche gibt es ?](/basics/database-objects.md) 
     * [SQL-Syntax](/basics/sql-syntax.md) 
     * [Datenbank-und-Tabellen-verwenden](/basics/databases-tables.md)
     * [Struktur und Indizes von Tabellen auslesen](/basics/struture-indexes-tables.md)

  1. SELECT's 
     * [Alle Datensätze abfragen und alias für Spalte setzen](/select/all-as-name.md) 
     * [Rechnen mit SELECT - Beispiele](/select/calculate.md)
     * [Beispiel und Übung - Berechnen aus Feldern](/select/beispiel-mit-berechnung-aus-feldern.md)
     * [Beispiel mit Select where ](/select/example-exercise-where.md)
     * [Beispiel mit select where in](/select/example-exercise-where-in.md) 
     * [Beispiel mit select und like](/select/using-like.md)
     * [Beispiele mit select und range](/select/example-select-range.md)
     * [Beispiel mit select und not in](/select/example-select-not-in.md) 
     * [Beispiel mit select und SUBSTR,LOWER,UPPER,CONCAT](/select/example-string-functions.md)
   
  1. IS NULL / IS NOT NULL 
     * [Beispiel und Übung mit IS NULL / IS NOT NULL](/select/example-is-null.md)
   
  1. DATUM (DATETIME,STR_TO_DATE oder der Unix Timestamp)
     * [Beispiel mit select by date](/select/example-select-by-date.md)
     * [Schlechtes Beispiel mit select by date](/select/bad-example-select-by-date.md)
     * [Beispiel mit Unix Timestamp (Umwandeln)](/select/unix-timestamp.md)  
     * [Beispiel mit Dateformat](/select/example-dateformat.md)
     * [Beispiel String in Date umwandeln](/select/str-to-date.md) 
   
  1. COUNT / STATISTIK  
     * [Zählen von Datensätzen](/select/count-rows.md) 
     * [Beispiel für Statistikabfrage (MAX,MIN)](/select/statistik.md) 
   
  1. NUMERISCHE FUNKTIONEN 
     * [Abrunden / Aufrunden / Kaufmännisch Runden](/select/functions-round-ceil-floor.md)  
   
  1. WEITERE STRINGFUNKTIONEN
     * [Überblick der Stringfunktionen](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html)
     * [CHAR_LENGTH und LENGTH](/select/char_length_length.md)
     * [Replace - Zeichen ersetzen](/select/replace.md) 
   
   
  1. ORDER BY (Sortierung)   
     * [Beispiel und Übung order by](/select/beispiel-order-by-mit-uebung.md)

  1. LIMIT 
     * [Kombiniertes Beispiel mit Order By und Limit + Übung](/select/example-exercise-order-by-limit.md)

  1. GROUP BY 
     * [Example GROUP BY / HAVING](/select/group-by-and-having.md)

  1. JOINS 
     * [Überblick über JOINS](/joins/simple-overview.md)
     * [Example join - 2 tables - 1:1](/joins/example-join.md) 
     * [Beispiel Join über 3 Tabellen](/joins/beispiel-join-ueber-3-tabellen.md)
     * [Beispiel Left join](/joins/example-leftjoin.md)
     * [Beispiel 2 Tabellen vergleichen](/joins/beispiel-2-tabellen-vergleichen.md) 
     * [Beispiel komplexer Join](/joins/example-complex-join.md)
    
  1. UPDATE 
     * [Update with example](/update/examples.md) 

  1. DELETE 
     * [Delete with example](/delete/examples.md)  
    
  1. ÜBUNGEN 
     * [Uebung - Berechnung aus Feld](beispiel-mit-berechnung-aus-feldern.md) 
     * [Übung order by](/select/beispiel-order-by-mit-uebung.md)
     * [Übung mit Order By und Limit](/select/example-exercise-order-by-limit.md)
     * [Übung mit Select where ](/select/example-exercise-where.md)
     * [Übung mit select where in](/select/example-exercise-where-in.md) 
     * [Übung mit select und like](/select/using-like.md)
     * [Übung 1+2 - Select Range](/select/example-select-range.md)
     * [Übung mit select und not in](/select/example-select-not-in.md) 
     * [Übung mit select by date](/select/example-select-by-date.md)
     * [Übung mit select by day](/select/bad-example-select-by-date.md)
     * [Übung - Zählen von Datensätzen](/select/count-rows.md)
     * [Übung - Statistik AVG](/select/statistik.md)
     * [Übung - NOT NULL / NULL](/select/example-is-null.md)
     * [Übung mit select und SUBSTR,LOWER,UPPER,CONCAT](/select/example-string-functions.md)
     * [Übung mit unix timestamp](/select/unix-timestamp.md)
     * [Übung mit Dateformat](/select/example-dateformat.md)
     * [Übung join - 2 tables - 1:1](/joins/example-join.md)
     * [Übung - Refresher Tag 2 - morgens - SELECT](/select/uebung-tag-2-morgens.md)
     * [Übung - Refresher Tag 3 - morgens - SELECT](/select/uebung-tag-3-morgens.md)
     * [Optional: Übung megajoin](/uebung-mega-join.md)

  1. Datenbanken und Tabellen anlegen, verändern und löschen, Daten einfügen 
     * [Datenbanken anlegen und löschen](/create-and-drop-databases.md)
     * [Übung - Tabelle kurs anlegen](/uebung/tabelle-kurs.md)
     * [Übung - Daten in kurs einfügen](/uebung/daten-insert.md)
     * [Übung - Daten updaten](/uebung/daten-updaten.md)

  1. Datentypen 
     * [Integer - Ganzzahlen](/datatypes/int.md)
     * [Strings - varchar](/datatypes/varchar.md)
     * [Text](https://www.mysqltutorial.org/mysql-text/)

  1. Variablen 
     * [Beispiel mit Abfrage und User-Variable](/variables/example-query.md)

  1. CSV export/import 
     * [Export von csv-daten aus der Workbench](/import-export-csv/workbench-export.md)
     * [Import von csv-daten mit der Workbench](/import-export-csv/workbench-import.md)
     * [Import von csv-daten als SQL-Befehl in der Workbench](/import-export-csv/load-data-infile.md)
     * [Dealing with charset in Excel (CSV)](/import-export-csv/dealing-with-charset.md)

  1. TIPPS & TRICKS 
     * [Cheatsheet - Auf dem System zurechtfinden - 1. Sichtung](cheatsheet/ueberblick.md) 
     * [Cheatsheet für Selects](cheatsheet/select.md)
     * [Restore auf der Kommandozeile (counterpart zu backup)](/backups-restore/restore.md)
     * [MYSQL-Workbench disable safe-mode](/workbench-disable-safe-mode.md)
     * [Datenbank mit mysql workbench exportieren](mysql-workbench-export.md)
     * [Datenbank mit mysql workbench importieren](mysql-workbench-import.md)

  1. Optional (Views & Triggers) 
     * [Views](views.md)
     * [Triggers](triggers.md)

  1. Documentation 
     * https://dev.mysql.com/downloads/windows/installer/8.0.html
     * https://www.mysqltutorial.org/
     * https://www.w3schools.com/sql/
  





  
