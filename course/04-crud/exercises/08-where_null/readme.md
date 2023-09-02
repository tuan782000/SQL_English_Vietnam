# Finding NULL values - Tìm giá trị NULL

You can use a `WHERE` clause to filter values by whether or not they're `NULL`.

## IS NULL - Hiển thị cột first_name kèm các giá trị bị NULL

```SQL
SELECT name FROM users WHERE first_name IS NULL;
```

## IS NOT NULL - Hiển thị cột first_name kèm các giá trị không bị NULL

```SQL
SELECT name FROM users WHERE first_name IS NOT NULL;
```

## Assignment

The way we store transactions at CashPal is interesting. We store a `user_id` field on the `transactions` table. That user is the "owner" of the transaction, and a `user_id` is never null.

Whenever the owner of the transaction *receives* money, the `sender_id` will not be null - it will be the user id of the sender. The `recipient_id` will be null.

Whenever the owner of the transaction *sends* money, the `recipient_id` will not be null - it will be the user id of the recipient. The `sender_id` will be null.

Cách chúng tôi lưu trữ các giao dịch tại CashPal rất thú vị. Chúng tôi lưu trữ trường `user_id` trên bảng `giao dịch`. Người dùng đó là "chủ sở hữu" của giao dịch và `user_id` không bao giờ có giá trị rỗng.

Bất cứ khi nào chủ sở hữu giao dịch *nhận* tiền, `sender_id` sẽ không có giá trị - nó sẽ là id người dùng của người gửi. `recipient_id` sẽ không có giá trị.

Bất cứ khi nào chủ sở hữu giao dịch *gửi* tiền, `recipient_id` sẽ không có giá trị rỗng - nó sẽ là id người dùng của người nhận. `sender_id` sẽ không có giá trị.

**Select all the rows from the transactions table where the owner of the transactions is receiving money.**

Chọn tất cả các hàng từ bảng giao dịch nơi chủ sở hữu giao dịch đang nhận tiền.

```SQL

SELECT * from transactions where sender_id IS NOT NULL;
```

