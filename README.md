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
