# MySQL Einsteiger 

## Agenda 

  1. Technical Background 
     * [Technical Structure](/technical-background/basics.md)
     * [Was ist SQL](/technical-background/sql.md)
     
  1. Grundlagen 
     * [Was sind Datenobjekte und welche gibt es ?](/basics/database-objects.md) 
     * [SQL-Syntax](/basics/sql-syntax.md) 
    
## Backlog      
       
  1. Beispieldaten / Testserver
     * [Sakila](sakila.md)
     * [Spendenliste](setup-training-data-contributions.md)
     * [Server Vagrant](server-vagrant.md)

  1. Client-Tools 
     * [mysql - client](mysql-client.md)

  1. Datentypen 
     * [Übersicht Datentypen](https://mariadb.com/kb/en/data-types/)
     * [Integer Datentypen](/datatypes/int.md)

  1. JOINS 
     * [Basics of Joins](joins/overview.md) 
     * [Working with LEFT JOIN](/joins/left-join.md)
     * [Join examples](/joins/join-examples.md)

  1. GROUP BY
     * [Simple Group By Example](group-by-example.md)
     * [Join and group - example](join-and-group.md)

  1. CONSTRAINTS
     * [Foreign Key Constraints - Example](foreign-key-constraints-with-example.md)
     * [Check constraint with example](check-constraints-with-example.md) 

  1. UPDATE 
     * [Sophisticated Update](update-extended.md)

  1. DELETE 
     * [Delete mit Transaktion](delete-transaktion.md)

  1. INDEX HINTS
     * [Force use of an Index](force-use-index.md) 
     * [Do not use an index if indexes are present](use-index-no.md)

  1. PREPARED STATEMENTS 
     * [Prepared Statements with examples](prepared-statements.md) 
     * [Prepared Statements and transactions](prepared-statements-transactions.md)

  1. TRIGGERS 
     * [Triggers](triggers.md) 

  1. EVENTS 
     * [Events](events.md) 

  1. FUNCTIONS
     * [Functions with example](function.md) 

  1. STORED PROCEDURES 
     * [Create Procedure](/stored-procedures/create-procedure.md)
     * [If](/stored-procedures/if.md)
     * [Cursors](/stored-procedures/cursor.md) 
     * [Cursor with Params](stored-procedures/cursor-with-params.md)
     * [Loop](/stored-procedures/loop.md)
     * [Case](/stored-procedures/case.md) 
     * [Continue Handler Example](/stored-procedures/continue-handler.md)
     * [Exit Handler Example](/stored-procedures/exit-handler.md)
     * [Custom Error message](/stored-procedures/custom-exception-error.md)

  1. ERRORS
     * [Error Codes List](https://mariadb.com/kb/en/mariadb-error-codes/)

  1. LOCKS
     * [Table wide locks](/locks/table-locks.md)  
     * [InnoDB Implicit Locks](/locks/innodb-implicit-locks.md)
     * [SELECT FOR UPDATE](/locks/select-for-update.md)

  1. sys (Database included since MariaDB 10.6 AFAIK) 
     * [Sys-Schema instalieren mariadb <= 10.6](/sys/sys-schema-installieren.md)
     * [show innodb locks with sys](/sys/sys-innodb-locks.md)

  1. Formatierung Ausgaben / Funktionen 
     * [Datumsausgabe formatieren](https://mariadb.com/kb/en/date_format/)
     * [Strings zusammenfügen](https://mariadb.com/kb/en/concat/)

  1. Partitions
     * [Partitions - Why and Howto?](/partitions/partitions-example.md)
     * [Maintain Partitions and Explain](/partitions/partitions-explain.md)
 
  1. Performance 
     * [Performance - Konfiguration von InnoDB Buffer Pool Size](/innodb/innodb.md) 
     * [Performance - Unterschied where between und <= and >=](performance/between-range-operators.md)
     * [* vs. specific field in field list - select](performance/all-vs-field.md)
     * [Möglichst keine Funktion in where (spalte) verwenden](mysq1-no-function-in-where.md)
     * [SQL-Rewrite Pager- Subselect](mysql-rewrite-subselect.md) 

  1. Slow Queries (Logging) 
     * [Log slow queries](/performance/slow-query-log.md)
     * [Log slow queries that do not use indexes](/performance/slow-query-log-queries-ohne-indexes.md)
    
  1. Analyzing Slow Queries / Indexes
     * [Prinzipien/Grundlagen von Indizies by MariaDB](/indexes/general.md)
     * [Create unique index](unique-index.md)
     * [Find indexes](indexes/findout-indexes.md)
     * [Create Index/Delete/Drop Index](create-index.md)
     * [Indizes (Table Scan / Cover Index)](indexes.md)
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
     * [Index neu aufbauen ?](reindex.md) 
     * [Index Stats](index-stats.md) 
  
  1. Tools 
     * [Percona Toolkit](/tools/percona-toolkit.md) 
     * [pt-query-digest - analyze slow logs](/tools/pt-query-digest.md)
     * [pt-query-digest - Windows/MariaDB](tools/pt-query-digest-windows.md)
     * [pt-online-schema-change howto](/tools/pt-online-schema-change.md)
     * [Example sys-schema and Reference](/tools/sys.md)
     * [Profiling](/performance/profiling.md)

  1. Backup und Restore
     * [Backup und Restore](/backup-restore.md)
     * [MariaBackup (Windows)](backups-restore/mariabackup-windows.md)

  1. User und Berechtigungen 
     * [Nutzer erstellen/Berechtigungen setzen/entfernen](rights/grant-revoke.md)

  1. Tipps & Tricks 
     * [Dummy table DUAL](https://mariadb.com/kb/en/dual/)
     * [Wie kann ich verwendete Storage Engine rausfinden - Table](show-create-table.md) 
     * [SHOW VARIABLES WITH WHERE](show-variables-with-where-or.md)
     * [Schnellster Import von Daten mit csv](/tricks/load-data-infile.md)
     * [Queries in Datenbank (mysql) loggen, die keine Indizes verwenden](queries-not-using-indexes.md)
     * [Workaround Materialized View](materialized-view-workaround.md)
     * [Zeichensatz umstellen](zeichensatz-umstellen.md)
     * [Hat InnoDB genug Speicher - Pages](innodb-free-pages.md)

  1. Storage Engines 
     * [MyISAM Key Buffer](http://www.mysqlab.net/knowledge/kb/detail/topic/myisam/id/7200)

  1. References/Documentation
     * [Server System Variables](https://mariadb.com/kb/en/server-system-variables/) 
     * [MySQL/MariaDB Performance Document](https://schulung.t3isp.de/documents/pdfs/mysql/mysql-performance.pdf)
     * [MariaDB - Changes in 10.6](https://mariadb.com/kb/en/changes-improvements-in-mariadb-106/#comment_5088)
     * [MariaDB - Installation Linux mit Repos](https://downloads.mariadb.org/mariadb/repositories/#distro=Ubuntu&distro_release=bionic--ubuntu_bionic&mirror=agdsn&version=10.6)
     * [JDBC-Treiber](https://mariadb.com/kb/en/about-mariadb-connector-j/)
   
  1. Oracle 
     * [Activating Oracle Sql-Mode](oracle/activating.md) 
     * [Overview Oracle Mode](https://mariadb.com/kb/en/sql_modeoracle/)
     * [When Others-Clause](https://www.techonthenet.com/oracle/exceptions/when_others.php)
     * [Demo Oracle sql_mode from MariaDB](https://www.youtube.com/watch?v=ntO2x4XHfUE)
     * [What is implemented in Oracle sql-mode - fromdual](https://fromdual.com/mariadb-sql-mode-oracle)
     * [Simple oracle examples pl/sql in mariadb](https://fromdual.com/select-hello-world-fromdual-with-mariadb-pl-sql)
     
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
     * [Dump/SQL-File einspielen auf der Kommandozeile - Windows](mysql-windows-sql-import.md)
    
  1. Tools 
     * [HeidiSQL Portable - works for windows](https://www.heidisql.com/download.php?download=portable-64)
  
  1. Tipps & Tricks 
     * [Best Practice DBAL - Kochrezept](recipe-dbal.md) 
  
  1. References 
     * [Examples Left Join](https://www.quackit.com/mysql/examples/mysql_left_join.cfm)
     * [Notes on Specific MySQL Knowledge](https://www.burnison.ca/notes)
     * [Many Sakila Example Queries](https://github.com/ashok-bidani/MySQL-Sakila-queries-and-joins)
     * [Helpful Examples](https://www.quackit.com/mysql/examples/mysql_group_by_clause.cfm)
     
  1. Übungen 
     * [Übung Update/Insert](uebung-insert-update.md)




  
