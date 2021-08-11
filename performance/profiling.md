# Profiling 

## Example 

```
MariaDB [(none)]> SET profiling = 1;
Query OK, 0 rows affected (0.000 sec)

MariaDB [(none)]> select * from actor where last_name like 'D%';
ERROR 1046 (3D000): No database selected
MariaDB [(none)]> use sakila;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
MariaDB [sakila]> select * from actor where last_name like 'D%';
+----------+------------+-----------+---------------------+
| actor_id | first_name | last_name | last_update         |
+----------+------------+-----------+---------------------+
|        4 | JENNIFER   | DAVIS     | 2006-02-15 04:34:33 |
|       35 | JUDY       | DEAN      | 2006-02-15 04:34:33 |
|       36 | BURT       | DUKAKIS   | 2006-02-15 04:34:33 |
|       41 | JODIE      | DEGENERES | 2006-02-15 04:34:33 |
|       48 | FRANCES    | DAY-LEWIS | 2006-02-15 04:34:33 |
|       81 | SCARLETT   | DAMON     | 2006-02-15 04:34:33 |
|       89 | CHARLIZE   | DENCH     | 2006-02-15 04:34:33 |
|      100 | SPENCER    | DEPP      | 2006-02-15 04:34:33 |
|      101 | SUSAN      | DAVIS     | 2006-02-15 04:34:33 |
|      106 | GROUCHO    | DUNST     | 2006-02-15 04:34:33 |
|      107 | GINA       | DEGENERES | 2006-02-15 04:34:33 |
|      109 | SYLVESTER  | DERN      | 2006-02-15 04:34:33 |
|      110 | SUSAN      | DAVIS     | 2006-02-15 04:34:33 |
|      123 | JULIANNE   | DENCH     | 2006-02-15 04:34:33 |
|      138 | LUCILLE    | DEE       | 2006-02-15 04:34:33 |
|      143 | RIVER      | DEAN      | 2006-02-15 04:34:33 |
|      148 | EMILY      | DEE       | 2006-02-15 04:34:33 |
|      160 | CHRIS      | DEPP      | 2006-02-15 04:34:33 |
|      166 | NICK       | DEGENERES | 2006-02-15 04:34:33 |
|      173 | ALAN       | DREYFUSS  | 2006-02-15 04:34:33 |
|      188 | ROCK       | DUKAKIS   | 2006-02-15 04:34:33 |
+----------+------------+-----------+---------------------+
21 rows in set (0.001 sec)

MariaDB [sakila]> show profiles;
+----------+------------+-----------------------------------------------+
| Query_ID | Duration   | Query                                         |
+----------+------------+-----------------------------------------------+
|        1 | 0.00078507 | select * from actor where last_name like 'D%' |
|        2 | 0.00073284 | SELECT DATABASE()                             |
|        3 | 0.00074666 | show databases                                |
|        4 | 0.00117272 | show tables                                   |
|        5 | 0.00190385 | select * from actor where last_name like 'D%' |
+----------+------------+-----------------------------------------------+
5 rows in set (0.000 sec)

MariaDB [sakila]> show profile all for query  5 \G
*************************** 1. row ***************************
             Status: Starting
           Duration: 0.000239
           CPU_user: 0.000000
         CPU_system: 0.000238
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: NULL
        Source_file: NULL
        Source_line: NULL
*************************** 2. row ***************************
             Status: checking permissions
           Duration: 0.000185
           CPU_user: 0.000000
         CPU_system: 0.000185
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_parse.cc
        Source_line: 6703
*************************** 3. row ***************************
             Status: Opening tables
           Duration: 0.000039
           CPU_user: 0.000000
         CPU_system: 0.000038
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_base.cc
        Source_line: 4222
*************************** 4. row ***************************
             Status: After opening tables
           Duration: 0.000012
           CPU_user: 0.000000
         CPU_system: 0.000012
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_base.cc
        Source_line: 4505
*************************** 5. row ***************************
             Status: System lock
           Duration: 0.000009
           CPU_user: 0.000000
         CPU_system: 0.000009
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: lock.cc
        Source_line: 337
*************************** 6. row ***************************
             Status: table lock
           Duration: 0.000016
           CPU_user: 0.000000
         CPU_system: 0.000016
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: lock.cc
        Source_line: 342
*************************** 7. row ***************************
             Status: init
           Duration: 0.000050
           CPU_user: 0.000000
         CPU_system: 0.000050
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_select.cc
        Source_line: 4967
*************************** 8. row ***************************
             Status: Optimizing
           Duration: 0.000022
           CPU_user: 0.000000
         CPU_system: 0.000022
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_select.cc
        Source_line: 1973
*************************** 9. row ***************************
             Status: Statistics
           Duration: 0.000088
           CPU_user: 0.000000
         CPU_system: 0.000090
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_select.cc
        Source_line: 2451
*************************** 10. row ***************************
             Status: Preparing
           Duration: 0.000038
           CPU_user: 0.000000
         CPU_system: 0.000037
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_select.cc
        Source_line: 2526
*************************** 11. row ***************************
             Status: Executing
           Duration: 0.000009
           CPU_user: 0.000000
         CPU_system: 0.000009
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_select.cc
        Source_line: 4533
*************************** 12. row ***************************
             Status: Sending data
           Duration: 0.000299
           CPU_user: 0.000000
         CPU_system: 0.000301
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_select.cc
        Source_line: 4731
*************************** 13. row ***************************
             Status: End of update loop
           Duration: 0.000016
           CPU_user: 0.000000
         CPU_system: 0.000013
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_select.cc
        Source_line: 5011
*************************** 14. row ***************************
             Status: Query end
           Duration: 0.000007
           CPU_user: 0.000000
         CPU_system: 0.000008
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_parse.cc
        Source_line: 6009
*************************** 15. row ***************************
             Status: Commit
           Duration: 0.000010
           CPU_user: 0.000000
         CPU_system: 0.000010
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_parse.cc
        Source_line: 6055
*************************** 16. row ***************************
             Status: closing tables
           Duration: 0.000008
           CPU_user: 0.000000
         CPU_system: 0.000008
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_base.cc
        Source_line: 786
*************************** 17. row ***************************
             Status: Unlocking tables
           Duration: 0.000006
           CPU_user: 0.000000
         CPU_system: 0.000006
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: lock.cc
        Source_line: 429
*************************** 18. row ***************************
             Status: closing tables
           Duration: 0.000015
           CPU_user: 0.000000
         CPU_system: 0.000016
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: lock.cc
        Source_line: 442
*************************** 19. row ***************************
             Status: Starting cleanup
           Duration: 0.000007
           CPU_user: 0.000000
         CPU_system: 0.000007
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_parse.cc
        Source_line: 6121
*************************** 20. row ***************************
             Status: Freeing items
           Duration: 0.000011
           CPU_user: 0.000000
         CPU_system: 0.000011
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_parse.cc
        Source_line: 8047
*************************** 21. row ***************************
             Status: Updating status
           Duration: 0.000803
           CPU_user: 0.000000
         CPU_system: 0.000040
  Context_voluntary: 0
Context_involuntary: 1
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_parse.cc
        Source_line: 2400
*************************** 22. row ***************************
             Status: Reset for next command
           Duration: 0.000012
           CPU_user: 0.000000
         CPU_system: 0.000011
  Context_voluntary: 0
Context_involuntary: 0
       Block_ops_in: 0
      Block_ops_out: 0
      Messages_sent: 0
  Messages_received: 0
  Page_faults_major: 0
  Page_faults_minor: 0
              Swaps: 0
    Source_function: <unknown>
        Source_file: sql_parse.cc
        Source_line: 2432
22 rows in set (0.001 sec)

MariaDB [sakila]> 



```
