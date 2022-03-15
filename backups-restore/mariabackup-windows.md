# Mariabackup (Windows)

## Installation mariabackup 

  * Installation wird mit Installation des Servers durchgeführt.
  * Ist also in der Grundinstallation beinhalten


## Walkthrough (Windows)

```
# Schritt 1: Backup 
# mariadb console starten  
# Programmpunkt unter mariadb 10.6 
# Achtung: backup - Ordner händisch in Explorer ohne Unterordner 
mariabackup --backup --user=root --password=password --target-dir=C:\Users\Admin\Desktop\backup\2022031501
```


## Ref (nur für Linux)

  * https://mariadb.com/kb/en/full-backup-and-restore-with-mariabackup/
