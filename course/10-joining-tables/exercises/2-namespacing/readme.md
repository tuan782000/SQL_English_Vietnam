# Namespacing on Tables

When working with multiple tables, you can specify which table a field exists on using a `.`. For example:

> table_name.column_name

```SQL
SELECT students.name, classes.name
FROM students
INNER JOIN classes on classes.class_id = students.class_id;
```

The above query returns the `name` field from the `students` table and the `name` field from the `classes` table. 

## Assignment

Adjust the query to:

* Return the `name`, and `age` fields from the `users` table.
* Return the `name` field from the `countries` table and rename it to `country_name`.
* Sort by the `country_name` in ascending order.


```SQL
CREATE TABLE users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER NOT NULL,
    country_code TEXT NOT NULL,
    username TEXT UNIQUE,
    password TEXT NOT NULL,
    is_admin BOOLEAN
);

CREATE TABLE countries (
  id INTEGER PRIMARY KEY,
  country_code TEXT,
  name TEXT,
  FOREIGN KEY (country_code)
  REFERENCES users (id)
);

SELECT users.name, users.age, countries.name as country_name
FROM users
--INNER JOIN Phần chung countries của bảng users và bảng countries
INNER JOIN countries on countries.country_code = users.country_code
ORDER BY country_name;

```