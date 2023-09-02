# Subqueries

Sometimes a single query is not enough to retrieve the specific records we need.

It is possible to run a query on the *result set* of another query - a query within a query! This is called "query-ception"... erm... I mean a "subquery".

Subqueries can be very useful in a number of situations when trying to retrieve specific data that wouldn't be accessible by simply querying a single table.


Đôi khi một truy vấn duy nhất là không đủ để truy xuất các bản ghi cụ thể mà chúng ta cần.

Có thể chạy một truy vấn trên *tập kết quả* của một truy vấn khác - một truy vấn bên trong một truy vấn! Đây được gọi là "truy vấn-tiếp nhận"... ừm... ý tôi là "truy vấn phụ".

Truy vấn con có thể rất hữu ích trong một số trường hợp khi cố gắng truy xuất dữ liệu cụ thể mà không thể truy cập được bằng cách truy vấn một bảng duy nhất.

## Retrieving data from multiple tables - Lấy dữ liệu từ nhiều bảng

Here is an example of a subquery:

```SQL
SELECT id, song_name, artist_id
FROM songs
WHERE artist_id IN (
    SELECT id
    FROM artists
    WHERE artist_name LIKE 'Rick%'
);
```

In this hypothetical database, the query above selects all of the `song_id`s, `song_name`s, and `artist_id`s from the `songs` table that are written by artists whose name starts with "Rick". Notice that the subquery allows us to use information from a different table - in this case the `artists` table.

Trong cơ sở dữ liệu giả định này, truy vấn ở trên chọn tất cả các `song_id`, `song_name` và `artist_id` từ bảng `songs` được viết bởi các nghệ sĩ có tên bắt đầu bằng "Rick". Lưu ý rằng truy vấn con cho phép chúng ta sử dụng thông tin từ một bảng khác - trong trường hợp này là bảng `nghệ sĩ`.

## Subquery syntax - Cú pháp truy vấn con

The only syntax unique to a subquery is the parentheses surrounding the nested query. The `IN` operator could be different, for example, we could use the `=` operator if we expect a single value to be returned.

Cú pháp duy nhất duy nhất cho truy vấn con là dấu ngoặc đơn bao quanh truy vấn lồng nhau. Toán tử `IN` có thể khác, ví dụ: chúng ta có thể sử dụng toán tử `=` nếu chúng ta mong đợi một giá trị được trả về.

## Assignment

One of CashPal's customer service representatives needs us to pull all the transactions for a specific user. Trouble is, they only know the user's `name`, not their `id`.

Use a subquery to get all of "David"s transactions.

### Transactions Table Schema

| id  | user_id | recipient_id | sender_id | note | amount | was_successful |
| --- | ------- | ------------ | --------- | ---- | ------ | -------------- |

### Users Table Schema

| id  | name | age | country_code | username | password | is_admin |
| --- | ---- | --- | ------------ | -------- | -------- | -------- |

1 Transaction có - n Users

Lấy thông tất cả thông tin của transactions với điều kiện truy vấn con user có điều kiện là name là David

SELECT * from transactions
WHERE user_id = (
  SELECT id
  FROM users
  WHERE name = 'David'
)



