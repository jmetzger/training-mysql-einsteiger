# Select mit Order (Sortierung) 

## Syntax 
```

-- Variante 1: (ohne where) 
-- SELECT * FROM <welche_tabelle> ORDER BY <welches_feld>


-- Variante 2: (mit where) 
-- SELECT * FROM <welche_tabelle> WHERE <welche_bedingung> ORDER BY <welches_feld>

```

## Beispiel ohne where 

```
# feld aufsteigend 
SELECT last_name,first_name,actor_id FROM sakila.actor ORDER BY last_name

# feld absteigend 
SELECT last_name,first_name,actor_id FROM sakila.actor ORDER BY last_name desc

# erstes feld aufsteigend, zweites feld absteigend
SELECT last_name,first_name,actor_id FROM sakila.actor ORDER BY last_name,first_name DESC 
```

## Beispiel mit where 

```

```
