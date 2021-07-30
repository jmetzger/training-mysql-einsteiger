# Short Introduction working with JSON (mysql 8) 

## General

  * Introduced since MySQL 5.7 

## Pitfalls 

  * Luke, use the index properly 

## Step 1: Create structure 

```
create schema training;
use training;
CREATE TABLE events( 
  id int auto_increment primary key, 
  event_name varchar(255), 
  visitor varchar(255), 
  properties json, 
  browser json
);
```

## Step 2: Fill with data 

```
INSERT INTO events(event_name, visitor,properties, browser) 
VALUES (
  'pageview', 
   '1',
   '{ "page": "/" }',
   '{ "name": "Safari", "os": "Mac", "resolution": { "x": 1920, "y": 1080 } }'
),
('pageview', 
  '2',
  '{ "page": "/contact" }',
  '{ "name": "Firefox", "os": "Windows", "resolution": { "x": 2560, "y": 1600 } }'
),
(
  'pageview', 
  '1',
  '{ "page": "/products" }',
  '{ "name": "Safari", "os": "Mac", "resolution": { "x": 1920, "y": 1080 } }'
),
(
  'purchase', 
   '3',
  '{ "amount": 200 }',
  '{ "name": "Firefox", "os": "Windows", "resolution": { "x": 1600, "y": 900 } }'
),
(
  'purchase', 
   '4',
  '{ "amount": 150 }',
  '{ "name": "Firefox", "os": "Windows", "resolution": { "x": 1280, "y": 800 } }'
),
(
  'purchase', 
  '4',
  '{ "amount": 500 }',
  '{ "name": "Chrome", "os": "Windows", "resolution": { "x": 1680, "y": 1050 } }'
);
Code language: SQL (Structured Query Language) (sql)
To pull values out of the JSON columns, you use the column path operator ( ->).
```

## Get data (within select)

```
# mit hochkommas
SELECT id, browser->'$.name' browser
FROM events;

# ohne hochkommas 
SELECT id, browser->'$.name' browser
FROM events;

# Die x-Auflösung
select id, browser->'$.resolution.x' browser from events

```

## Reference 

  * https://www.mysqltutorial.org/mysql-json/

