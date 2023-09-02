# Primary Keys - Khóa chính.

A *key* defines and protects relationships between tables. A [`primary key`](https://en.wikipedia.org/wiki/Primary_key) is a special column that uniquely identifies records within a table. Each table can have one, and only one primary key.

*key* xác định và bảo vệ mối quan hệ giữa các bảng. [`khóa chính`] là một cột đặc biệt xác định duy nhất các bản ghi trong một bảng. Mỗi bảng có thể có một và chỉ một khóa chính.

## Your primary key will almost always be the "id" column - Khóa chính của bạn hầu như sẽ luôn là cột "id"

It's *very* common to have a column named `id` on each table in a database, and that `id` is the primary key for that table. No two rows in that table can share an `id`.

Việc có một cột có tên `id` trên mỗi bảng trong cơ sở dữ liệu là *rất* phổ biến và `id` là khóa chính cho bảng đó. Không có hai hàng nào trong bảng đó có thể chia sẻ `id`.

A `PRIMARY KEY` constraint can be explicitly specified on a column to ensure uniqueness, rejecting any inserts where you attempt to create a duplicate ID.

Ràng buộc `PRIMARY KEY` có thể được chỉ định rõ ràng trên một cột để đảm bảo tính duy nhất, từ chối mọi phần chèn mà bạn cố gắng tạo ID trùng lặp.

## Assignment

Run the code. Notice that there's a bug - there is a violation of a `PRIMARY KEY` constraint on the `id` column. *Fix the data that's being inserted.*

Chạy mã. Lưu ý rằng có một lỗi - có sự vi phạm ràng buộc `PRIMARY KEY` trên cột `id`. *Sửa dữ liệu đang được chèn.*

When working with integer ids, it's best practice to increment the `id` by `1` for each successive insert. Follow this convention when fixing the bug.

Khi làm việc với id số nguyên, cách tốt nhất là tăng `id` lên `1` cho mỗi lần chèn liên tiếp. Hãy tuân theo quy ước này khi sửa lỗi.

```SQL
INSERT into users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER NOT NULL,
    username TEXT UNIQUE,
    password TEXT NOT NULL,
    is_admin BOOLEAN
) values (
    0,
    "Rudolf",
    33,
    "rudolf1234",
    "thisisnotsecure",
    false
);

INSERT into users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER NOT NULL,
    username TEXT UNIQUE,
    password TEXT NOT NULL,
    is_admin BOOLEAN
) values (
    0,
    "Jerry",
    25,
    "jerrysmith",
    "mypasswordis1234",
    true
);

select * from users;

```