# Joins

Joins are one of the most important features that SQL offers. Joins allow us to make use of the relationships we have set up between our tables. In short, joins allow us to query multiple tables at the *same time.*

Tham gia là một trong những tính năng quan trọng nhất mà SQL cung cấp. Các phép nối cho phép chúng ta tận dụng các mối quan hệ mà chúng ta đã thiết lập giữa các bảng của mình. Tóm lại, các phép nối cho phép chúng ta truy vấn nhiều bảng cùng lúc *cùng một lúc.*

## Inner Join

The simplest and most common type of join in SQL is the `INNER JOIN`. By default, a `JOIN` command is an `INNER JOIN`. An `INNER JOIN` returns all of the records in `table_a` that have matching records in `table_b` as demonstrated by the following Venn diagram.

Kiểu nối đơn giản và phổ biến nhất trong SQL là `INNER JOIN`. Theo mặc định, lệnh `JOIN` là `INNER JOIN`. `INNER JOIN` trả về tất cả các bản ghi trong `table_a` có các bản ghi trùng khớp trong `table_b` như được minh họa bằng sơ đồ Venn sau.

![inner join](https://i.imgur.com/wgxAmhA.png)

## On

In order to perform a join, we need to tell the database which fields should be "matched up". The  `ON` clause is used to specify these columns to join.

Để thực hiện kết nối, chúng ta cần cho cơ sở dữ liệu biết trường nào cần được "khớp". Mệnh đề `ON` được sử dụng để chỉ định các cột này sẽ tham gia.

```SQL
SELECT *
FROM employees
INNER JOIN departments 
ON employees.department_id = departments.id;
```

The query above returns *all* the fields from *both* tables. The `INNER` keyword doesn't have anything to do with the number of *columns* returned - it only affects the number of *rows* returned.

Truy vấn ở trên trả về *tất cả* các trường từ bảng *cả hai*. Từ khóa `INNER` không liên quan gì đến số *cột* được trả về - nó chỉ ảnh hưởng đến số *hàng* được trả về.

## Assignment

Our frontend team is working on a profile page and would like to display a user's country *name* instead of just the country's two-letter *code*. Let's start by writing a simple join between the `users` table and `countries` table. We will expand on this query more in the next exercise.

* Write an `INNER JOIN` between `users` and `countries`
* Return *all* fields from both tables
* Join on the `country_code` field

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

SELECT *
FROM users
INNER JOIN countries 
ON countries.country_code = users.country_code;

-- Mệnh đề ON chỉ định các cột sẽ tham gia
-- `INNER JOIN` trả về tất cả các bản ghi trong `table_a` có các bản ghi trùng khớp trong `table_b`

```
