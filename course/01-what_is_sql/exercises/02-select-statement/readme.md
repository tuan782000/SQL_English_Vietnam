# SQL Select Statement - Câu lệnh Select trong SQL

Let's write our own SQL statement from scratch! A `SELECT` statement is the most common operation in SQL - often called a "query". `SELECT` retrieves data from one or more tables. Standard `SELECT` statements do *not* alter the state of the database.

Hãy viết câu lệnh SQL của riêng chúng ta từ đầu! Câu lệnh `SELECT` là thao tác phổ biến nhất trong SQL - thường được gọi là "truy vấn". `SELECT` lấy dữ liệu từ một hoặc nhiều bảng. Các câu lệnh `SELECT` tiêu chuẩn *không* làm thay đổi trạng thái của cơ sở dữ liệu.

Example:

```SQL
SELECT id from users;
```

## Select a single field - Chọn 1 cột cụ thể

A `SELECT` statement begins with the keyword `SELECT` followed by the fields you want to retrieve.

Câu lệnh `SELECT` bắt đầu với từ khóa `SELECT` theo sau các trường bạn muốn truy xuất

Example:

```SQL
SELECT id from users;
```

## Select multiple fields - Chọn nhiều trường.

If you want to select more than one field you can specify multiple fields separated by commas.

Nếu bạn muốn chọn nhiều hơn một trường, bạn có thể chỉ định nhiều trường bằng các phân cách chúng bằng dấu phẩy ","

Example:

```SQL
SELECT id, name from users;
```

## Select all fields - Chọn tất cả các trường

If you want to select *every* field in a record you can use the shorthand `*` syntax.

Nếu bạn muốn chọn *tất cả* các trường trong 1 bảng ghi bạn có thể viết tắt cú pháp như sau: `*` 

Example:

```SQL
SELECT * from users;
```

After specifying fields, you need to indicate which table you want to pull the records *from* using the `from` statement followed by the name of the table. We'll talk more about tables later, but for now, you can think about them like structs or objects. For example, the `users` table might have 3 fields:

Sau khi chỉ định các trường, bạn cần chỉ ra các bảng bào bạn muốn lấy bản ghi *từ* bằng cách sử dụng câu lệnh `form` theo sau là tên bảng. Chúng ta sẽ nói nhiều hơn về bảng sau, nhưng hiện tại, bạn có thể nghĩ về chúng như cấu trúc hoặc đối tượng. Ví dụ,
bảng `users` có thể có 3 trường:

* `id`
* `name`
* `balance`

And finally, *all* statements end with a semi-colon `;`.

Và cuối cùng, câu lệnh *all* kết thúc bằng dấu chấm phẩy `;`.

## Assignment

The state of our *CashPal* `users` table is as follows:

| id  | name          | age | balance | is_admin |
| --- | ------------- | --- | ------- | -------- |
| 1   | John Smith    | 28  | 450     | 1        |
| 2   | Darren Walker | 27  | 200     | 1        |
| 2   | Jane Morris   | 33  | 496.24  | 0        |

It's very common to write queries that only return specific portions of data from a table. Our HR team has requested a report asking for all the `name`s and `balance`s of all of our users. 

Việc viết các truy vấn chỉ trả về những phần dữ liệu cụ thể từ một bảng là điều rất phổ biến. Nhóm nhân sự của chúng tôi đã yêu cầu một báo cáo yêu cầu tất cả `name` và `balance` số dư của tất cả người dùng `users` của chúng tôi.

Write a query that retrieves all of the `name`s and `balance`s from the `users` table.

Viết một truy vấn truy xuất tất cả `name` và `balance` từ bảng `users`.

```SQL
SELECT name, balance from users;
```
| name          | balance |
| ------------- | ------- |
| John Smith    | 450     |
| Darren Walker | 200     |
| Jane Morris   | 496.24  |
