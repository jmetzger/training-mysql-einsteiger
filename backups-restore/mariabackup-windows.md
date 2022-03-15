# Mariabackup (Windows)

## Installation mariabackup 

  * Installation wird mit Installation des Servers durchgeführt.
  * Ist also in der Grundinstallation beinhalten


## Walkthrough (Windows) - Sicherung 

```
REM -- Schritt 1: Backup 
REM -- mariadb console starten  
REM -- Programmpunkt unter mariadb 10.6 
REM -- Achtung: backup - Ordner händisch in Explorer ohne Unterordner 
mariabackup --backup --user=root --password=password --target-dir=C:\Users\Admin\Desktop\backup\2022031501
```

```
REM -- Schritt 2: Prepare 
REM -- mariadb console starten  
REM -- Programmpunkt unter mariadb 10.6 
REM -- Achtung: backup - Ordner händisch in Explorer ohne Unterordner 
mariabackup --prepare --user=root --password=password --target-dir=C:\Users\Admin\Desktop\backup\2022031501
```

## Walkthrough (Windows) - Restore (Zurückspielen) 

```
REM -- Schritt 1: Server stoppen  
REM - Über Dienste -> MariaDB -> Rechte Maustaste -> Beenden 

REM -- Schritt 2: data - Verzeichnis umbenennen 
REM - Im Explorer -> z.B. data-backup 


REM -- Schritt 3: Restore  
REM -- mariadb console starten  
REM -- Programmpunkt unter mariadb 10.6 
REM -- Achtung: backup - Ordner händisch in Explorer ohne Unterordner 
mariabackup --copy-backup --user=root --password=password --target-dir=C:\Users\Admin\Desktop\backup\2022031501

REM -- Schritt4: my.ini aus altem Verzeichnis in neues Kopieren (data-backup\my.ini -> data\my.ini)


REM -- Schritt3: Rechte vom neuen Verzeichnis (erstellt durch Schritt 2) anpassen 
REM -- Rechte Maustaste -> Eigenschaften -> Sicherheit -> Bearbeiten -> Hinzufügen -> NT Service\MariaDB -> Namen überprüfen
REM -- MariaDB muss als Name erscheinen -> Übernehmen -> OK 
REM -- Evtl. nochmal überprüfen ob der Nutzer drin ist. 

REM -- Schritt 4: Server starten 
REM -- Dienste -> MariaDB -> Starten 

```

## Ref (nur für Linux)

  * https://mariadb.com/kb/en/full-backup-and-restore-with-mariabackup/
