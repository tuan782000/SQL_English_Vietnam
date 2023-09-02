# Creating a Table - Câu lệnh tạo bảng

The `CREATE TABLE` statement is used to create a new table in a database.

Câu lệnh `CREATE TABLE` được sử dụng để tạo một bảng mới trong cơ sở dữ liệu.

## "CREATE TABLE" statement - Câu lệnh tạo bảng

To create a table, use the `CREATE TABLE` statement followed by the name of the table and the fields you want in the table.

Để tạo được 1 bảng, sử dụng câu lệnh `CREATE TABLE` theo sau đó là "tên bảng" và các trường sẽ có trong bảng

Example:

```SQL
-- Tạo ra bảng có tên là employees, trong bảng có các trường id, name, age, is_manager, salary
-- Các trường thì có kiểu dữ liệu riêng của nó. 
CREATE TABLE employees (id INTEGER, name TEXT, age INTEGER, is_manager BOOLEAN, salary INTEGER);
```

Each field name is followed by its *datatype*. We'll get to data types in a minute.
Mỗi tên trường được theo sau bởi *kiểu dữ liệu* của nó. Chúng ta sẽ chuyển sang các loại dữ liệu sau một phút.

It's also acceptable and common to break up the `CREATE TABLE` statement with some whitespace like this:

Việc chia câu lệnh `CREATE TABLE` bằng một số khoảng trắng như thế này cũng được chấp nhận và phổ biến:

Example:

```SQL
CREATE TABLE employees(
    id INTEGER,
    name TEXT,
    age INTEGER,
    is_manager BOOLEAN,
    salary INTEGER
);
```

## Assignment

Let's begin building a table for *CashPal* database! Create the `people` table with the following fields:

1. id - `Integer`
2. handle - `Text`
3. name - `Text`
4. age - `Integer`
5. balance - `Integer`
6. is_admin - `boolean`

Do it:

```SQL
CREATE TABLE people(
    id INTEGER,
    handle TEXT,
    name TEXT,
    age INTEGER,
    balance INTEGER,
    is_admin BOOLEAN,
);
```
