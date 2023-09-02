# MAX

As you may expect, the `max` function retrieves the *largest* value from a set of values. For example:

```SQL
SELECT max(price)
FROM products
```

This query looks through all of the prices in the `products` table and returns the price with the largest price value. Remember it only returns the `price`, not the rest of the record! You always need to specify each field you want a query to return.

## Assignment

Use a `max` aggregation to find the largest amount of money *received* by a Jill (`user_id` of 4). Return her `user_id` and that amount.

Table name: `transactions`

Column names:

* `id`
* `user_id`
* `recipient_id`
* `sender_id`
* `note`
* `amount`
* `was_successful`

## A note on schema

* The `sender_id` will be present for any transactions where the user in question (`user_id`) is *receiving* money (from the sender).
* The `recipient_id` will be present for any transactions where the user in question (`user_id`) is *sending* money (to the recipient).

In other words, a transaction can only have a `sender_id` *or* a `recipient_id` - not *both*. The presence of one or the other indicates whether money is going *into* or *out of* the user's account.

This `user_id`, `recipient_id`, `sender_id` schema we've designed is only *one* way to design a transactions database - there are other valid ways to do it! It's the one we're using, and later we'll talk more about the tradeoffs in different database design options.

`sender_id` sẽ hiển thị cho mọi giao dịch mà người dùng được đề cập (`user_id`) đang *nhận* tiền (từ người gửi).
`recipient_id` sẽ hiển thị cho mọi giao dịch mà người dùng được đề cập (`user_id`) đang *gửi* tiền (cho người nhận).

Nói cách khác, một giao dịch chỉ có thể có `sender_id` *hoặc* `recipient_id` - không phải *cả hai*. Sự hiện diện của cái này hay cái kia cho biết tiền đang *vào* hay *ra khỏi* tài khoản của người dùng.

Lược đồ `user_id`, `recipient_id`, `sender_id` mà chúng tôi thiết kế này chỉ là *một* cách để thiết kế cơ sở dữ liệu giao dịch - có nhiều cách hợp lệ khác để thực hiện điều đó! Đó là cái chúng tôi đang sử dụng và sau này chúng tôi sẽ nói nhiều hơn về sự cân bằng trong các tùy chọn thiết kế cơ sở dữ liệu khác nhau.

```SQL
select user_id, max(amount)
from transactions
where user_id = 4 and sender_id is NOT NULL;
```