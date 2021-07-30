# Training: MySQL Grundlagen/Performance (Hannover)

## Agenda 

  1. Technical Background 
     * [Technical Structure](/technical-background/basics.md)
     * [Process of Queries](/performance/mysql-server-architecture.md)

  1. Beispieldaten / Testserver
     * [Sakila](sakila.md)
     * [Spendenliste](setup-training-data-contributions.md)
     * [Server Vagrant](server-vagrant.md)

  1. JOINS 
     * [Basics of Joins](joins/overview.md) 
     * [Working with LEFT JOIN](/joins/left-join.md)
     * [Join examples](/joins/join-examples.md)

  1. GROUP BY
     * [Simple Group By Example](group-by-example.md)
     * [Join and group - example](/joins/join-and-group.md)

  1. CONSTRAINTS
     * [Foreign Key Constraints - Example](foreign-key-constraints.md) 

  1. UPDATE 
     * [Sophisticated Update](update-extended.md) 

  1. JSON 
     * [Short Introduction working JSON](json.md) 

  1. Performance 
     * [* vs. specific field in field list - select](performance/all-vs-field.md)
     * [Möglichst keine Funktion in where (spalte) verwenden](mysq1-no-function-in-where.md)
     * [SQL-Rewrite Pager- Subselect](mysql-rewrite-subselect.md) 

  1. Analyzing Slow Queries / Indexes
     * [Find indexes](indexes/findout-indexes.md)
     * [Create Index/Delete/Drop Index](create-index.md)
     * [Indizes](indexes.md)
     * [Explain](explain.md) 
     * [profiling-get-time-for-execution-of.query](/indexes/profiling.md)
     * [Kein function in where verwenden](/performance/no-function-in-where.md)
     * [Optimizer-hints (and why you should not use them)](performance/optimizer-hints.md)
     * [Query-Plans aka Explains](performance/query-plans.md)
     * [Query Pläne und die Key-Länge](performance/query-plans-explain-keylen.md)
     * [Index und Likes](indexes/like-index-not-index.md)
     * [Index und Joins](indexes/join-index.md)
     * [Find out cardinality without index](/indexes/cardinality.md)
     * [Index and Functions](index-and-functions.md) 
 
  1. Tools 
     * [Percona Toolkit](/tools/percona-toolkit.md) 
     * [pt-query-digest - analyze slow logs](/tools/pt-query-digest.md)
     * [pt-online-schema-change howto](/tools/pt-online-schema-change.md)
     * [Example sys-schema and Reference](/tools/sys.md)

  1. Storage Engines 
     * [MyISAM Key Buffer](http://www.mysqlab.net/knowledge/kb/detail/topic/myisam/id/7200)

  1. References 
     * [MySQL Performance Document](https://schulung.t3isp.de/documents/pdfs/mysql/mysql-performance.pdf)
     * [MySQL 5.7 was has changed to 8.0](https://severalnines.com/database-blog/moving-mysql-57-mysql-80-what-you-should-know)

## Backlog 

  1. Working with database objects 
     * [Working with databases](/database-objects/databases.md) 
     * [Working with tables](/database-objects/tables.md) 
     * [Teststellung - Feld verkleinern](/database-objects/tables-smaller-column.md)
 
  1. SELECT 
     * [Select Beispiele](table-select.md) 
     * [Select Beispiele mit Like](select-like.md)
     * [SELECT ORDER BY](select-order-by.md)
     * [Unterschiede einfache und doppelte Hochkommas bei Oracle/MySQL](unterschiede-hochkommas-mysql-oracle.md)
 
  1. INSERT/UPDATE
     * [Praktisches Beispiel und erweitertes insert - INSERT](insert.md) 
     * [Praktisches Beispiel - Update](update.md) 
 
  1. DELETE 
     * [Einfaches Delete Beispiel](delete-example.md)
     * [Delete mit Transaktion](delete-transaktion.md)

  1. Datentypen 
     * [Integer - INT - Datentypen](int.md)
 
  1. Basics 
     * [Connection to DB + exit](/basics/connection-db.md) 
     * [mysql-client](mysql-client.md) 
     * [Charset-Collations](basic/charset-collation.md)
     * [server system variablen abfragen](server-system-variables.md) 
     
  1. Storage Engines 
     * [Which engine is used](storage-engine-used.md) 
     
  1. Working with the data modelling language (DML's)
     * [Working with INSERT](/data-modelling-commands/insert.md)
    
  1. Tipps & Tricks / Do Not 
     * [SQL-Query im Query Tab (MySQL Workbench) direkt ausführen](workbench-strg-enter.md)
     * [Dump/SQL-File einspielen auf der Kommandozeile - Windows](mysql-windows-sql-import.md)
     
     * [Export Partial Columns in MYSQL with INTO OUTFILE](mysql-select-into-outfile.md)
    
  1. Tools 
     * [HeidiSQL Portable - works for windows](https://www.heidisql.com/download.php?download=portable-64)
  
  1. Tipps & Tricks 
     * [Best Practice DBAL - Kochrezept](recipe-dbal.md) 
  
  
  1. References 
     * [Examples Left Join](https://www.quackit.com/mysql/examples/mysql_left_join.cfm)
     * [Notes on Specific MySQL Knowledge](https://www.burnison.ca/notes)
     * [Many Sakila Example Queries](https://github.com/ashok-bidani/MySQL-Sakila-queries-and-joins)
     * [Helpful Examples](https://www.quackit.com/mysql/examples/mysql_group_by_clause.cfm)
     
  1. Extra (Optional)  
     * [Schnellster Import von Daten mit csv](/tricks/load-data-infile.md)

  1. Übungen 
     * [Übung Update/Insert](uebung-insert-update.md)

  
