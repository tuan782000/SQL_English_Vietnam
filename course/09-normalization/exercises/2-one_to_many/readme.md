# One to many

When talking about the relationships between *tables*, a one-to-many relationship is probably the most commonly used relationship. 

A one-to-many relationship occurs when a single record in one table is related to potentially many records in another table. 

Note that the one->many relation only goes *one way*, a record in the second table can *not* be related to multiple records in the first table!


Khi nói về mối quan hệ giữa *tables*, mối quan hệ một-nhiều có lẽ là mối quan hệ được sử dụng phổ biến nhất.

Mối quan hệ một-nhiều xảy ra khi một bản ghi trong một bảng có liên quan đến nhiều bản ghi trong một bảng khác.

Lưu ý rằng mối quan hệ một->nhiều chỉ diễn ra *một chiều - one way*, một bản ghi trong bảng thứ hai có thể *không* liên quan đến nhiều bản ghi trong bảng đầu tiên!


## Examples of one-to-many relationships - Ví dụ mối quan hệ 1 nhiều

* A `customers` table and a `orders` table. Each customer has `0`, `1`, or many orders that they've placed.
* A `users` table and a `transactions` table. Each `user` has `0`, `1`, or many transactions that taken part in.

* Bảng `customers` và bảng `orders`. Mỗi khách hàng có `0`, `1` hoặc nhiều đơn hàng họ đã đặt.
* Bảng `users` và bảng `transactions`. Mỗi `user` có `0`, `1` hoặc nhiều giao dịch đã tham gia.

## Assignment

It turns out that when we originally designed the CashPal database schema we assumed that users would only have a *single* country they lived in. With digital nomads becoming a thing, it turns out many users have dual citizenship.

Hóa ra là khi thiết kế lược đồ cơ sở dữ liệu CashPal ban đầu, chúng tôi đã giả định rằng người dùng sẽ chỉ có một quốc gia *duy nhất* mà họ sinh sống. Với việc những người du mục kỹ thuật số trở thành xu hướng phổ biến, hóa ra nhiều người dùng có hai quốc tịch.

Instead of a single `users` table where each user has a single `country_code`, do the following:

* Remove the `country_code` field from the `users` table
* Create a new table called `countries` with 4 fields:
  * `id`: an integer
  * `country_code`: a string
  * `name`: a string
  * `user_id`: an integer foreign key to the `users` table's `id` field


```SQL
-- Xác định một 1 user có thể có nhiều quốc tịch, chính vì vậy tách trường country_code ra làm 1 bảng riêng

-- 1 users có - n countries 

-- bảng nhiều sẽ phải có khóa ngoại, từ khóa ngoại bảng "n" tham chiếu đến khóa chính của bảng "1"

CREATE TABLE users (
  id INTEGER PRIMARY KEY,
  name TEXT NOT NULL,
  age INTEGER NOT NULL,
  username TEXT UNIQUE,
  password TEXT NOT NULL,
  is_admin BOOLEAN
);

CREATE TABLE countries (
  id INTEGER PRIMARY KEY,
  country_code TEXT,
  name TEXT,
  
  -- Mối liên kết với bảng users
  user_id INTEGER,
  FOREIGN KEY (user_id)
  REFERENCES users (id)
);
```