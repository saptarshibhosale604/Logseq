level:: 2
comment:: managing and manipulating data stored in RDBMS
type:: language

- [[Intro]]
	- Relational Database Management System: RDBMS
	- Field: column // vertical
	- record: row // horizontal
	- Not case sensitive
- SELECT
	- SELECT * FROM table1
	- SELECT col1, col2 ... FROM table1
	- SELECT DISTINCT col1 FROM table1
	- SELECT * FROM table1 
	  WHERE col1=val1
	- Operators
	  collapsed:: true
		- =
		- >
		- <
		- AND
			- SELECT * FROM table1
			  WHERE col1=val1 AND col2=val2
		- OR
		- NOT
			- SELECT * FROM table1
			  WHERE NOT col1=val1
		- BETWEEN
			- SELECT * FROM table1
			  WHERE col1 BETWEEN val1 and val2
			- NOT BETWEEN
				- SELECT * FROM table1
				  WHERE col1 NOT BETWEEN val1 and val2
		- LIKE
			- SELECT * FROM table1
			  WHERE col1 LIKE 'a%'
			- % : 0, 1, multi characters
			- _ : One character
			- NOT LIKE
				- SELECT * FROM table1
				  WHERE col1 NOT LIKE 'a%'
		- IN
			- SELECT * FROM table1
			  WHERE col1 IN (val1, val2)
			- NOT IN
				- SELECT * FROM table1
				  WHERE col1 NOT IN (val1, val2)
	- SELECT * FROM table1 
	  ORDER BY col1 [ /ASC/DESC]
	- SELECT * FROM table1
	  WHERE col1 IS NULL
	- SELECT * FROM table1
	  WHERE col1 IS NOT NULL
	- SELECT * FROM table1
	  LIMIT 3
	- Aggregate functions
		- MIN()
			- SELECT MIN(col1) FROM table1
			- SELECT MIN(col1) AS minCol1, col2 FROM table1
			  GROUP BY col2
		- MAX()
		- COUNT()
		- SUM()
		- AVG()
		- SELECT MAX(col1) maxCol1, col2 FROM table1
		  WHERE col2 = 3
		  GROUP BY col2
		  HAVING maxCol1 > 5
		  ORDER BY col2
	- Joins
		- (INNER) JOIN
			- SELECT * FROM table1 t1
			  JOIN table2 t2 ON t1.col1=t2.col1
		- LEFT (OUTER) JOIN
		- RIGHT (OUTER) JOIN
		- FULL (OUTER) JOIN
		- SELF JOIN
			- SELECT * FROM table1 t1, table1 t2
			  WHERE t1.col1 = t2.col1
	- UNION
		- SELECT * FROM table1
		  UNION
		  SELECT * FROM table2 // Distinct values only
		- UNION ALL // all values
- INSERT INTO
  collapsed:: true
	- INSERT INTO table1 (col1, col2 ...)
	  VALUES (val1, val2 ...)
	- INSERT INTO table1
	  VALUES (val1, val2 ...)
	- INSERT INTO table1
	  VALUES 
	  (val01, val02 ...),
	  (val11, val12 ...),
	  ...
- UPDATE table1
  SET col1=val1, col2=val2, ...
  WHERE colx=valx
- DELETE FROM
  collapsed:: true
	- DELETE FROM table1
	  WHERE col1=val1
	- DELETE FROM table1
	- DROP TABLE table1