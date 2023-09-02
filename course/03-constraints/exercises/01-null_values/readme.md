# Null values - Giá trị Null

In SQL, a cell with a `NULL` value indicates that the value is *missing*. A `NULL` value is *very* different from a *zero* value.

Trong SQL, một ô có giá trị `NULL` cho biết giá trị đó *thiếu*. Giá trị `NULL` *rất* khác với giá trị *zero*.

## Constraints - Hạn chế

When creating a table we can define whether or not a field *can* or *cannot* be `NULL`, and that's a kind of `constraint`.

Khi tạo một bảng, chúng ta có thể xác định xem một trường *có thể* hay *không thể* là `NULL` hay không, và đó là một loại `ràng buộc`.

We will cover constraints in more detail soon, for now, let's focus on `NULL` values.

Chúng tôi sẽ sớm đề cập đến các ràng buộc chi tiết hơn, bây giờ, hãy tập trung vào các giá trị `NULL`.

## Assignment

We didn't force any constraints on our tables when we created them and it has allowed for `NULL` entries to make their way into our table! Let's take a look at our `transactions` table to see what those `NULL` values look like.

Chúng tôi đã không áp đặt bất kỳ ràng buộc nào trên các bảng của mình khi tạo chúng và nó đã cho phép các mục `NULL` đi vào bảng của chúng tôi! Chúng ta hãy xem bảng `transactions` của chúng tôi để xem các giá trị `NULL` đó trông như thế nào.

Write a query to `SELECT` all of the fields on all records of the `transactions` table.

Viết một truy vấn tới `SELECT` tất cả các trường trên tất cả các bản ghi của bảng `transactions`.

## Tip

Use the `*` (wildcard) syntax to select *all* fields.

Sử dụng `*` cú pháp chọn *all* các trường.

## Observe

Notice that both the `transaction_type` and `was_successful` fields have `NULL` values in all 3 records in the table (nulls are represented by blank cells in our system). That's because we ran our migration in the previous exercise *after* the 3 records were created!

```SQL
SELECT * FROM transactions;
```

Ngoài lề:

```SQL
CREATE TABLE transactions (
    id INTEGER, 
    recipient_id INTEGER, 
    sender_id INTEGER, 
    note TEXT, 
    amount INTEGER
);

INSERT INTO transactions (id, recipient_id, sender_id, note, amount)
VALUES (1, 14, 26, "Testing transaction!", 10.50);
```
