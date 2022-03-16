# pt-query-digest windows (MariaDB) 

## Walkthrough 

```
# Step 1: install strawberry perl as msi - 64Bits 
# https://strawberryperl.com/

# Step 2: Open Browser in RDP and open this Page
# https://www.percona.com/get/pt-query-digest

# Step 3: Rechte Maustaste -> Speichern unter auf Desktop: pt-query-digest.pl 

# Step 4: Verschieben in bin - ordner von MariaDB-Server 

# Step 5: Console mit MariaDB - Umgebung öffnen. 

# Step 6: Analysieren der slow-query-log mit pt-query-digest.pl 
# z.B. report.txt 
# hie öffnet sich ein 2. Fenster mit der Frage, wo es ausgeführt -> Strawberry Perl 
pt-query-digest.pl <pfad-und-name-des-slow-query-logs> > <pfad-zur-neuen-datei>/report.txt 

```

## Ref:

  * Achtung: URL (Domain) von percona ist falsch 
  * http://www.jonathanlevin.co.uk/2012/01/query-digest-on-windows.html
