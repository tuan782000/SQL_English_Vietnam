# Order By

SQL also offers us the ability to sort the results of a query using `ORDER BY`. By default, the `ORDER BY` keyword sorts records by the given field in ascending order, or `ASC` for short. However, `ORDER BY` does support descending order as well with the keyword `DESC`.

SQL cũng cung cấp cho chúng ta khả năng sắp xếp kết quả của truy vấn bằng cách sử dụng `ORDER BY`. Theo mặc định, từ khóa `ORDER BY` sắp xếp các bản ghi theo trường nhất định theo thứ tự tăng dần hoặc viết tắt là `ASC`. Tuy nhiên, `ORDER BY` cũng hỗ trợ thứ tự giảm dần với từ khóa `DESC`.

## Examples

This query returns the `name`, `price`, and `quantity` fields from the `products` table sorted by `price` in *ascending* order:

Truy vấn này trả về các trường `name`, `price` và `quantity` từ bảng `products` được sắp xếp theo `price` theo thứ tự *tăng dần*:

```SQL
SELECT name, price, quantity FROM products
    ORDER BY price;
```

This query returns the `name`, `price`, and `quantity` of the products ordered by the quantity in *descending* order:

Truy vấn này trả về `tên`, `giá` và `số lượng` của các sản phẩm được sắp xếp theo số lượng theo thứ tự *giảm dần*:

```SQL
SELECT name, price, quantity FROM products
    ORDER BY quantity desc;
```

## Assignment

Write a query that lists all the records in the `transactions` table where:

* `amount` is `BETWEEN` 10 and 80 dollars.
* The results are sorted by `amount` in *descending* order.

```SQL
SELECT * FROM transactions 
WHERE amount BETWEEN 10 AND 80
ORDER BY amount DESC;
```
