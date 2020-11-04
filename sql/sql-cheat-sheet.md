## SQL Cheat Sheet :)

#### Create table
```sql
CREATE TABLE celebs (
   id INTEGER, 
   name TEXT, 
   age INTEGER
);
```
#### Inserting values into table
```sql
INSERT INTO celebs (id, name, age) 
VALUES (2, 'Beyonce Knowles', 33); 
```

#### Select values
```sql
SELECT * FROM celebs;
SELECT name FROM celebs;
SELECT name, genre FROM movies
```

#### Select `AS`
```sql
SELECT name AS 'title'
FROM movies;
```

#### Alter table
```sql
ALTER TABLE celebs 
ADD COLUMN twitter_handle TEXT; 
```

#### Update table
```sql
UPDATE celebs 
SET twitter_handle = '@taylorswift13' 
WHERE id = 4; 
```

#### Delete from table
```sql
 DELETE FROM celebs 
WHERE twitter_handle IS NULL;
```

#### Constrains
```sql
 CREATE TABLE awards (
   id INTEGER PRIMARY KEY,
   recipient TEXT NOT NULL,
   award_name TEXT DEFAULT 'Grammy'
);
```
1. `PRIMARY KEY` columns can be used to uniquely identify the row. Attempts to insert a row with an identical value to a row already in the table will result in a constraint violation which will not allow you to insert the new row.

2. `UNIQUE` columns have a different value for every row. This is similar to PRIMARY KEY except a table can have many different UNIQUE columns.

3. `NOT NULL` columns must have a value. Attempts to insert a row without a value for a NOT NULL column will result in a constraint violation and the new row will not be inserted.

4. `DEFAULT` columns take an additional argument that will be the assumed value for an inserted row if the new row does not specify a value for that column.

### Queries
#### `DISTINCT` - filtering duplicated values
```sql
SELECT DISTINCT genre 
FROM movies;
```

#### Select `WHERE`
```sql
SELECT * 
FROM movies 
WHERE year > 2014;
```

##### Comparison operators:
- `=` equal to
- `!=` not equal to
- `>` greater than
- `<` less than
- `>=` greater than or equal to
- `<=` less than or equal to

#### Select `LIKE`
```sql
SELECT * 
FROM movies
WHERE name LIKE 'Se_en';

SELECT * 
FROM movies
WHERE name LIKE 'A%';
```

#### Select `IS NOT NULL` / `IS NULL`
```sql
SELECT name
FROM movies 
WHERE imdb_rating IS NOT NULL;
```

#### Select `BETWEEN`
```sql
SELECT *
FROM movies
WHERE name BETWEEN 'A' AND 'J';

SELECT *
FROM movies
WHERE year BETWEEN 1990 AND 1999;
```

#### Select `AND`
```sql
SELECT * 
FROM movies
WHERE year BETWEEN 1990 AND 1999
   AND genre = 'romance';
```

#### Select `OR`
```sql
SELECT *
FROM movies
WHERE year > 2014
   OR genre = 'action';
```

#### Select `ORDER BY` (`ASC` / `DESC`)
```sql
SELECT *
FROM movies
WHERE imdb_rating > 8
ORDER BY year DESC;
```

#### Select `LIMIT`
```sql
SELECT *
FROM movies
LIMIT 10;
```

#### Select `CASE`
```sql
SELECT name,
 CASE
  WHEN genre == 'romance' THEN 'Chill'
  WHEN genre == 'comedy' THEN 'Chill'
  ELSE 'Intense'
 END AS 'Mood'
FROM movies;
```

### Aggregate functions
#### `COUNT`
```sql
SELECT COUNT(*)
FROM fake_apps
WHERE price = 0.0;
```

#### `SUM`
```sql
SELECT SUM(downloads)
FROM fake_apps;
```

#### `MAX` / `MIN`
```sql
SELECT MIN(downloads)
FROM fake_apps;
```

#### `AVG`
```sql
SELECT AVG(downloads)
FROM fake_apps;
```

#### `ROUND`
```sql
SELECT ROUND(price, 2)
FROM fake_apps;
```

#### `GROUP BY`
```sql
SELECT price, COUNT(*) 
FROM fake_apps
GROUP BY price;

SELECT category, SUM(downloads)
FROM fake_apps
GROUP BY category;

SELECT category, 
   price,
   AVG(downloads)
FROM fake_apps
GROUP BY category, price;
```
#### Select `HAVING`
```sql
SELECT price, 
   ROUND(AVG(downloads)),
   COUNT(*)
FROM fake_apps
GROUP BY price
HAVING COUNT(name) > 10;
```


### Multiple tables
#### Inner `JOIN`
The final result has all values from the first and last rows but does not include the non-matching middle row.
```sql
SELECT orders.order_id,
   customers.customer_name
FROM orders
JOIN customers
  ON orders.customer_id = customers.customer_id;
```

```sql
SELECT *
FROM orders
JOIN subscriptions
  ON orders.subscription_id = subscriptions.subscription_id;
```
```sql
SELECT *
FROM orders
JOIN subscriptions
  ON orders.subscription_id = subscriptions.subscription_id AND subscriptions.description = 'Fashion Magazine';
```

#### Left `JOIN`
 A left join will keep all rows from the first table, regardless of whether there is a matching row in the second table.
 ```SQL
SELECT *
FROM newspaper
LEFT JOIN online
  ON newspaper.id = online.id
WHERE online.id IS NULL;
```

### Cross join
```sql
SELECT shirts.shirt_color,
   pants.pants_color
FROM shirts
CROSS JOIN pants;
```

```sql
SELECT month, 
  COUNT(*)
FROM newspaper
CROSS JOIN months
WHERE start_month <= month 
  AND end_month >= month
GROUP BY month;
```

#### `UNION`
```sql
SELECT *
FROM newspaper
UNION 
SELECT *
FROM online;
```

#### `WITH` clause
```sql
WITH previous_query AS (
SELECT customer_id,
       COUNT(subscription_id) as subscriptions
FROM orders
GROUP BY customer_id)
SELECT customers.customer_name,
previous_query.subscriptions
FROM previous_query
JOIN customers
	ON customers.customer_id = previous_query.customer_id;
```
