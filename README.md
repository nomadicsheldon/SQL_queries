# SQL_queries

---

## creating a table ==>

```sql
CREATE TABLE cities (
  name VARCHAR(50),
  country VARCHAR(50),
  population INTEGER,
  area INTEGER
);
```

---

## inserting data into the table ==>

```sql
INSERT INTO cities (name, country, population, area)
VALUES('India', 'delhi', 3876500, 45645);
```

---

## inserting multiple data into the table ==>

```sql
INSERT INTO cities (name, country, population, area)
VALUES
  ('Delhi', 'India', 3876500, 45645),
  ('Sanghai', 'China', 234324, 34344),
  ('Sao Paulo', 'Brazil', 345344, 45461);
```

## retrieving all data from the table ==>

```sql
SELECT * FROM cities;
```

---

## retrieving selected data from the table ==>

we can retrieve in any order, it can be (name, country) or (country, name), etc.
```sql
SELECT name, country FROM cities;
```

---

## retrieving calculated columns from the table ==>
"AS" we use for renaming calculated column.

```sql
SELECT name, population/ area AS density FROM cities;
```

---

## string operators and functions ==>

>- || => join two strings
>- CONCAT() => join two strings
>- LOWER() => gives a lowercase string
>- UPPER() => gives a uppercase string
>- LENGTH() => gives number of characters in a string

examples -
```sql
SELECT name || ', '|| country AS location FROM cities; 
```
```sql
SELECT CONCAT(name,', ',country) AS location FROM cities;
```
```sql
SELECT CONCAT(UPPER(name),', ',UPPER(country)) AS location FROM cities;
```
```sql
SELECT UPPER(CONCAT(name,', ',country)) AS location FROM cities;
```

---

## filtering rows with "WHERE" ==>

#### Math Operations for "where"
- "=" => are the values equal?
- ">" => is the value on the left is greater?
- "<" => is the value on the left is less?
- ">=" => is the value on the left is greater or equal to?
- "IN" => is the value present in the list?
- "<=" => is the value on the left is lesser or equal to?
- "<>" => are the value not equal?
- "!=" => are the value not equal?
- "BETWEEN" => is the value between two other values?
- "NOT IN" => is the value not present in the list?

####example =>

```sql
SELECT name, area FROM cities WHERE area > 40000;
```
```sql
SELECT name, area FROM cities WHERE area BETWEEN 30000 AND 40000;
```
```sql
SELECT name, area FROM cities WHERE name IN ('Delhi', 'Sanghai');
```
```sql
SELECT name, area FROM cities WHERE name NOT IN ('Delhi', 'Sanghai');
```
- multiple comparison
```sql
SELECT name, area FROM cities WHERE name NOT IN ('Delhi', 'Sanghai') AND area > 45500;
```
- remember order of execution(1st- FROM cities, 2nd- WHERE population/area < 50, 3rd- SELECT name, population/area AS density), so you can't use "density" instead of "population/area" at population/area < 50.
```sql
SELECT name, population/area AS density FROM cities WHERE population/area < 50;
```

---

## Updating rows =>
> remember: when we are upating the value then be specific with "WHERE" it can change multiple rows which follows the condition. So "WHERE" statement should be like it selects only one row.

```sql
UPDATE cities SET population = 5000000 WHERE name='Delhi';
```

---

## Deleting rows =>

```sql
DELETE FROM cities WHERE name='Sao Paulo';
```

---

## Creating table with primary key =>

```sql
CREATE TABLE users (
	id SERIAL PRIMARY KEY,
  username VARCHAR(50)
);
```
### inserting in table
```sql
INSERT INTO users (username)
VALUES
  ('himanshu'),
  ('shivanshu')
```
### reading data
```sql
SELECT * FROM users;
```

---



