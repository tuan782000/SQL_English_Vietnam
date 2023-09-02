# Create Table Practice - Luyện tập tạo bảng

In most relational databases a single table isn't enough to hold all the data we need! We *usually* create a table-per-entity. For example, a social media application might have the following tables:

Trong hầu hết các cơ sở dữ liệu quan hệ, một bảng không đủ để chứa tất cả dữ liệu chúng ta cần! Chúng tôi *usually* tạo một bảng cho mỗi thực thể. 
Ví dụ: một ứng dụng truyền thông xã hội có thể có các bảng sau:

* `users`
* `posts`
* `comments`
* `likes`

## Assignment

We need a table that tracks the transactions between our *CashPal* users.

Create the `transactions` table with the following fields:

1. id - `Integer`
2. recipient_id - `Integer`
3. sender_id - `Integer`
4. note - `Text`
5. amount - `Integer`

Do it

```SQL
CREATE TABLE transactions(
    id INTEGER,
    recipient_id INTEGER,
    sender_id INTEGER,
    note TEXT,
    amount INTEGER
);
```

Chúng ta có thể viết 1 cách liền mạch:

```SQL
CREATE TABLE transactions (id INTEGER, recipient_id INTEGER, sender_id INTEGER, note TEXT, amount INTEGER);
```

