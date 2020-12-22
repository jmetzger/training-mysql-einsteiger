# Select for update

## Important 

  * It only locks (X) the rows needed, not the complete table 


## When is it used ? 

  * You want to be sure, a specific dataset will not be changed 

## Example 
```
create database if not exists training;
use training;
create table rooms (room_id tinyint auto_increment, room varchar(20), primary key(room_id));
create table bookings (booking_id int auto_increment, room_id tinyint, name varchar(20), primary key(booking_id)); 
insert into rooms (room) values ('Honeymoon');
insert into rooms (room) values ('Sunset');

# Session 1:
BEGIN;
select room_id from rooms where room_id = 1 for update;

# Session 2: 
BEGIN 
use training;
delete from rooms where room_id = 1;
-- transaction waiting 

# Session 3:
SELECT   waiting_trx_id,   waiting_pid,   waiting_query,   blocking_trx_id,   blocking_pid,   blocking_query FROM sys.innodb_lock_waits;

# Session 1:
COMMIT;

# Session 2:
# See what happens 





```
