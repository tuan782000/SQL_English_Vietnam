# What is SQL?

Structured Query Language, is the primary programming language used to manage and interact with relational databases. SQL can perform various operations such as creating, updating, reading, and deleting records within a database.

SQL là viết tắt của "Structured Query Language" (Ngôn ngữ truy vấn có cấu trúc), là ngôn ngữ lập trình chính được sử dụng để quản lý và tương tác với các cơ sở dữ liệu quan hệ. SQL có thể thực hiện các thao tác khác nhau như tạo, cập nhật, đọc và xóa bản ghi trong cơ sở dữ liệu.

## CashPal

In this course, we will be building the database for a pretend PayPal clone called *CashPal*! Storing information related to people's money, transactions, and identity is very important! So we will need to make sure we use proper conventions to build a safe, and reliable database architecture that our users can rely on.


Trong khóa học này, chúng ta sẽ xây dựng cơ sở dữ liệu cho một phiên bản giả của PayPal được gọi là CashPal! Việc lưu trữ thông tin liên quan đến tiền của mọi người, giao dịch và danh tính là rất quan trọng! Vì vậy, chúng ta cần đảm bảo sử dụng các quy ước đúng để xây dựng một kiến trúc cơ sở dữ liệu an toàn và đáng tin cậy mà người dùng của chúng ta có thể tin tưởng.


## Assignment

I have provided a simple SQL statement for you that retrieves some records from a table. However there isn't a `people` table, the table in our database is called `users`. Fix the bug by changing `people` to `users` within the `SELECT` statement.

Tôi đã cung cấp một câu lệnh SQL đơn giản cho bạn để truy xuất một số bản ghi từ một bảng. Tuy nhiên, không có bảng people, bảng trong cơ sở dữ liệu của chúng ta được gọi là users. Sửa lỗi bằng cách thay đổi people thành users trong câu lệnh SELECT.

```SQL
SELECT * from people;
```

```SQL
SELECT * from users;
```

```SQL
CREATE TABLE users (id INTEGER, name TEXT, age INTEGER, is_admin BOOLEAN);
INSERT into users (id, name, age, is_admin) values (1, 'John Doe', 27, false);
INSERT into users (id, name, age, is_admin) values (2, 'Sally Rae', 18, true);
```


