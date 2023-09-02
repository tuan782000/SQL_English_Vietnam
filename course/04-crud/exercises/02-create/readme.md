# Insert Statement

Tables are pretty useless without data in them! In SQL we can add records to a table using an `INSERT INTO` statement. When using an `INSERT` statement we must first specify the `table` we are inserting the record into, followed by the `fields` within that table we want to add `VALUES` to.

Example `INSERT INTO` statement:

```SQL
INSERT INTO employees(id, name, title)
VALUES (1, 'Allan', 'Engineer');
```

## Assignment

Let's start manually adding some of the records to our `users` table!

Take a look at the `CREATE TABLE` statement in the *setup code* below for the `users` table structure, and use that information to insert the following records into the table:

### Record 1

* `id`: 1
* `name`: David
* `age`: 34
* `country_code`:  US
* `username`: DavidDev
* `password`: insertPractice
* `is_admin`: false

### Record 2

* `id`: 2
* `name`: Samantha
* `age`: 29
* `country_code`:  BR
* `username`: Sammy93
* `password`: addingRecords!
* `is_admin`: false

```SQL
CREATE TABLE users (
    id INTEGER PRIMARY KEY.
    name TEXT NOT NULL,
    age INTEGER NOT NULL,
    country_code TEXT NOT NULL,
    username TEXT UNIQUE NOT NULL,
    password TEXT UNIQUE NOT NULL,
    is_admin BOOLEAN
)

INSERT INTO users (id, name, age, country_code, username, password, is_admin)
VALUES (1 ,'David', 34 ,'US' ,'DavidDev' ,'insertPractice',0 ),
VALUES (2 ,'Samantha', 29 ,'BR' ,'Sammy93' ,'addingRecords!',0 );
```