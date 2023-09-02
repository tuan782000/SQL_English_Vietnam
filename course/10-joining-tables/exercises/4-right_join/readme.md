# Right Join

A `RIGHT JOIN` is, as you may expect, the opposite of a `LEFT JOIN`. It returns all records from `table_b` regardless of matches, and all matching records between the two tables.

`RIGHT JOIN`, như bạn có thể mong đợi, trái ngược với `LEFT JOIN`. Nó trả về tất cả các bản ghi từ `table_b` bất kể kết quả khớp và tất cả các bản ghi khớp giữa hai bảng.

![right-join](https://i.imgur.com/LG6Y43j.png)

## SQLite Restriction

SQLite does *not* support right joins, but many dialects of SQL do! If you think about it, a `RIGHT JOIN` is just a `LEFT JOIN` with the order of the tables switched, so it's not a big deal that SQLite doesn't support the syntax.

SQLite *không* hỗ trợ nối phải, nhưng nhiều phương ngữ của SQL thì có! Nếu bạn nghĩ về điều đó, `RIGHT JOIN` chỉ là `LEFT JOIN` với thứ tự của các bảng được chuyển đổi, vì vậy việc SQLite không hỗ trợ cú pháp không phải là vấn đề lớn.


