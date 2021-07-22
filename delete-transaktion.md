# Delete mit Transaktion 

## Beispiel 

```
Variante 1: Andere sehen es erst nach commit (andere Sessions/Verbindungen) 

BEGIN;
DELETE FROM actor where actor_id = 200;
COMMIT;

Variante 2: Aktion mir nicht, ich rolle sie zurück, mache sie rückgängig
BEGIN;
DELETE FROM actor where actor_id = 200;
ROLLBOCK;

```
