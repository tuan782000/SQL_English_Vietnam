# HAVING vs WHERE in SQL

It's fairly common for developers to get confused about the difference between the `HAVING` and the `WHERE` clauses - they're pretty similar after all.

The difference is fairly simple in actuality:

* A `WHERE` condition is applied to *all* the data in a query *before* it's grouped by a `GROUP BY` clause.
* A `HAVING` condition is only applied to the *grouped rows* that are returned *after* a `GROUP BY` is applied.

This means that if you want to filter on the result of an aggregation, you need to use `HAVING`. If you want to filter on a value that's present in the raw data, you should use a simple `WHERE` clause.


Các nhà phát triển thường nhầm lẫn về sự khác biệt giữa mệnh đề `HAVING` và `WHERE` - xét cho cùng thì chúng khá giống nhau.

Sự khác biệt khá đơn giản trong thực tế:

* Điều kiện `WHERE` được áp dụng cho *tất cả* dữ liệu trong truy vấn *trước khi* nó được nhóm theo mệnh đề `GROUP BY`.
* Điều kiện `HAVING` chỉ được áp dụng cho *các hàng được nhóm* được trả về *sau khi* áp dụng `GROUP BY`.

Điều này có nghĩa là nếu bạn muốn lọc kết quả của một phép tổng hợp, bạn cần sử dụng `HAVING`. Nếu bạn muốn lọc một giá trị có trong dữ liệu thô, bạn nên sử dụng mệnh đề `WHERE` đơn giản.

## Example for the questions

```sql
SELECT class_id, count(id) as count
FROM students
WHERE ...
GROUP BY class_id
HAVING ...
```
