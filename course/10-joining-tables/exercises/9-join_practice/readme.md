# Join Practice

Joins take some time to get used to, but the key to understanding them and using them effectively is *practice*!

## Multiple Joins

To incorporate data from more than *two* tables, you can utilize multiple joins to execute more complex queries!

```SQL
SELECT *
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.id
INNER JOIN regions
ON departments.region_id = regions.id
```

## Assignment

Our front-end team is finalizing the *profile* page for *CashPal*. We need to write a query that returns all the `user` data they need for an individual user's profile. The query needs to return the following fields:

1. The user's `id`
2. The user's `name`
3. The user's `age`
4. The user's `username`
5. The user's country name, renamed to `country_name`
6. The sum of the user's transaction amounts, renamed to `balance`

Return only a single user record - specifically the one with `id=6`


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
  REFERENCES users (country_code)
);

CREATE TABLE transactions (
  id INTEGER PRIMARY KEY, 
  user_id INTEGER NOT NULL,
  recipient_id INTEGER, 
  sender_id INTEGER, 
  note TEXT, 
  amount INTEGER,
  was_successful BOOLEAN
);

SELECT users.id, users.name, users.age, users.username, countries.name as country_name, sum(transactions.amount) as balance
FROM users
INNER JOIN countries
ON users.country_code = countries.country_code
INNER JOIN transactions
ON users.id = transactions.user_id
WHERE users.id = 6;
```