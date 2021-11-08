# SQL2

mysql> SELECT birthday FROM wizard WHERE 1975 AND 1985;
+------------+
| birthday   |
+------------+
| 1980-07-31 |
| 1979-09-19 |
| 1960-01-30 |
| 1980-03-01 |
| 1981-08-11 |
| 1978-04-01 |
| 1978-04-01 |
| 1950-02-06 |
| 1949-01-01 |
| 1980-06-05 |
| 1881-07-01 |
| 1960-01-09 |
| 1926-12-31 |
| 1980-06-23 |
+------------+
14 rows in set (0,00 sec)

mysql> SELECT firstname LIKE 'H';
ERROR 1054 (42S22): Unknown column 'firstname' in 'field list'
mysql> SELECT firstname LIKE H;
ERROR 1054 (42S22): Unknown column 'firstname' in 'field list'
mysql> SELECT firstname FROM wizard WHERE firstname='H';
Empty set (0,00 sec)

mysql> SELECT firstname FROM wizard WHERE firstname='H%';
Empty set (0,00 sec)

mysql> SELECT firstname FROM wizard WHERE firstname LIKE 'H%';
+-----------+
| firstname |
+-----------+
| harry     |
| hermione  |
+-----------+
2 rows in set (0,00 sec)

mysql> SELECT * FROM wizard WHERE lastname='Potter' ORDER BY firstname;
+----+-----------+----------+------------+-------------+------------------------+-----------+
| id | firstname | lastname | birthday   | birth_place | biography              | is_muggle |
+----+-----------+----------+------------+-------------+------------------------+-----------+
|  1 | harry     | potter   | 1980-07-31 | london      |                        |         0 |
|  3 | lily      | potter   | 1960-01-30 |             | mother of Harry Potter |         0 |
+----+-----------+----------+------------+-------------+------------------------+-----------+
2 rows in set (0,00 sec)

mysql> SELECT firstname, lastname, birthday ORDER BY birthday DESC;
ERROR 1054 (42S22): Unknown column 'firstname' in 'field list'
mysql> SELECT firstname, lastname, birthday FROM wizard ORDER BY birthday DESC;
+-----------+------------+------------+
| firstname | lastname   | birthday   |
+-----------+------------+------------+
| ginny     | weasley    | 1981-08-11 |
| harry     | potter     | 1980-07-31 |
| dudley    | dursley    | 1980-06-23 |
| drago     | malefoy    | 1980-06-05 |
| ron       | weasley    | 1980-03-01 |
| hermione  | granger    | 1979-09-19 |
| fred      | weasley    | 1978-04-01 |
| george    | weasley    | 1978-04-01 |
| lily      | potter     | 1960-01-30 |
| severus   | rogue      | 1960-01-09 |
| arthur    | weasley    | 1950-02-06 |
| molly     | weasley    | 1949-01-01 |
| tom       | jÃ©dusor   | 1926-12-31 |
| albus     | dumbledore | 1881-07-01 |
+-----------+------------+------------+
14 rows in set (0,00 sec)

mysql> 

