# Left Join

A `LEFT JOIN` will return every record from `table_a` regardless of whether or not any of those records have a match in `table_b`. A left join will *also* return any matching records from `table_b`. Here is a Venn diagram to help visualize the effect of a `LEFT JOIN`.

`LEFT JOIN` sẽ trả về mọi bản ghi từ `table_a` bất kể bản ghi nào trong số đó có khớp trong `table_b` hay không. Phép nối bên trái sẽ *cũng* trả về bất kỳ bản ghi trùng khớp nào từ `table_b`. Đây là sơ đồ Venn để giúp hình dung tác dụng của `LEFT JOIN`.

Lấy hết bảng a, riêng bảng b chỉ lấy phần chung với a thui

![left-join](https://i.imgur.com/mNbhWfM.png)

A small trick you can do to make writing the SQL query easier is define an [alias](https://en.wikipedia.org/wiki/Alias_(SQL)) for each table. Here's an example:

Một mẹo nhỏ bạn có thể thực hiện để viết truy vấn SQL dễ dàng hơn là xác định [bí danh](https://en.wikipedia.org/wiki/Alias_(SQL)) cho mỗi bảng. Đây là một ví dụ:

```SQL
SELECT e.name, d.name
FROM employees e
LEFT JOIN departments d
ON e.department_id = d.id;
```

Notice the simple alias declarations `e` and `d` for `employees` and `departments` respectively.

Some developers do this to make their queries less verbose. That said, I personally *hate it* because single-letter variables are harder to understand the meaning of.

Lưu ý các khai báo bí danh đơn giản `e` và `d` tương ứng cho `nhân viên` và `phòng ban`.

Một số nhà phát triển làm điều này để làm cho truy vấn của họ ít dài dòng hơn. Điều đó nói lên rằng, cá nhân tôi *ghét nó* vì các biến một chữ cái khó hiểu ý nghĩa hơn.

## Assignment

The *CashPal* team needs a report on all the transactions a user has made. Join the `users` and `transactions` tables on `users.id` and `transactions.user_id`.

Your query should return 3 fields: - Truy vấn của bạn sẽ trả về 3 trường:

1. A user's `name` as `name`- `name` của người dùng là `name`
2. The sum of all of their transaction `amount`s as `sum` - Tổng của tất cả các giao dịch `số tiền` của họ là `tổng`
3. The count of all of their transactions as `count` - Đếm tất cả các giao dịch của họ dưới dạng `count`

* Be sure to order the data by the `sum` field in descending order. - Đảm bảo sắp xếp dữ liệu theo trường `sum` theo thứ tự giảm dần.
* Be sure to still return user records of users who have no transactions. - Đảm bảo vẫn trả lại hồ sơ người dùng của những người dùng không có giao dịch.

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

CREATE TABLE transactions (
  id INTEGER PRIMARY KEY, 
  user_id INTEGER NOT NULL,
  recipient_id INTEGER, 
  sender_id INTEGER, 
  note TEXT, 
  amount INTEGER,
  was_successful BOOLEAN
);
                -- Tính tổng transactions.amount    -- Đếm transactions.id
SELECT users.name, sum(transactions.amount) as sum, count(transactions.id) as count
FROM users
LEFT JOIN transactions
ON users.id = transactions.user_id
GROUP BY users.id
ORDER BY sum DESC;

```
