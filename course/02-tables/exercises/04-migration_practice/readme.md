# Migration Practice

When writing *reversible* migrations, we use the terms "up" and "down" migrations. An "up" migration is simply the set of changes you want to make, like altering/removing/adding/editing a table in some way. A "down" migration includes the changes that would *revert* any of the "up" migration's changes.

Khi viết quá trình di chuyển *reversible*, chúng tôi sử dụng thuật ngữ di chuyển "up" và "down". Di chuyển "up" chỉ đơn giản là tập hợp các thay đổi bạn muốn thực hiện, như thay đổi/xóa/thêm/chỉnh sửa bảng theo một cách nào đó. Quá trình di chuyển "down" bao gồm các thay đổi sẽ *revert* bất kỳ thay đổi nào của quá trình di chuyển "lên".

## Assignment

Add additional columns to the `transactions` table. We want to know whether or not the transaction was successfully completed between two users. We also want our database to track the *type* of transaction.

Our `transactions` table looks like this at the moment:

| cid | name         | type    | notnull | dflt_value | pk  |
| --- | ------------ | ------- | ------- | ---------- | --- |
| 0   | id           | INTEGER | 0       |            | 0   |
| 1   | recipient_id | INTEGER | 0       |            | 0   |
| 2   | sender_id    | INTEGER | 0       |            | 0   |
| 3   | note         | TEXT    | 0       |            | 0   |
| 4   | amount       | INTEGER | 0       |            | 0   |

Complete the following `up` migration:

* Add the `boolean` `was_successful` column to the `transactions` table.
* Add the `TEXT` `transaction_type` column to the `transactions` table.

```SQL
ALTER TABLE transactions
ADD COLUMN was_successful BOOLEAN

ALTER TABLE transactions
ADD COLUMN transaction_type TEXT
```

