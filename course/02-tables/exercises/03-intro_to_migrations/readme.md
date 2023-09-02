# Intro to Migrations - Giới thiệu Migrations

A database [migration] is a set of changes to a relational database. In fact, the `ALTER TABLE` statements we did in the last exercise were examples of migrations!

Cơ sở dữ liệu [migration] là một tập hợp các thay đổi đối với cơ sở dữ liệu quan hệ. Trên thực tế, các câu lệnh `ALTER TABLE` mà chúng ta đã thực hiện trong bài tập trước là ví dụ về việc di chuyển!

Migrations are helpful when transitioning from one state to another, fixing mistakes, or adapting a database to changes. 

Migrations thì rất hữu ích khi chuyển từ trạng thái này sang trạng thái khác, sửa lỗi hoặc điều chỉnh cơ sở dữ liệu cho phù hợp với các thay đổi.

*Good* migrations are small, incremental and ideally *reversible* changes to a database. As you can imagine, when working with large databases, making changes can be scary! We have to be careful when writing database migrations so that we don't break any systems that depend on the old database schema.


*Good* migrations là những thay đổi nhỏ, tăng dần và lý tưởng *reversible* (đảo ngược) đối với cơ sở dữ liệu. Như bạn có thể tưởng tượng, khi làm việc với cơ sở dữ liệu lớn, việc thực hiện các thay đổi có thể rất đáng sợ! Chúng ta phải cẩn thận khi viết di chuyển cơ sở dữ liệu để không phá vỡ bất kỳ hệ thống nào phụ thuộc vào lược đồ cơ sở dữ liệu cũ.

## Example of a bad migration

If the CashPal backend periodically runs a query like `SELECT * FROM people`, and we execute a database migration that alters the table name from `people` to `users` *without updating the code*, the application will break! It will try to grab data from a table that no longer exists.

Nếu chương trình phụ trợ CashPal định kỳ chạy truy vấn như `SELECT * FROM people` và chúng tôi thực hiện di chuyển cơ sở dữ liệu để thay đổi tên bảng từ `people` thành `users` *mà không cập nhật code*, ứng dụng sẽ bị hỏng! Nó sẽ cố gắng lấy dữ liệu từ một bảng không còn tồn tại.

A simple solution to this problem would be to deploy new code that uses a new query:

Một giải pháp đơn giản cho vấn đề này là triển khai mã mới sử dụng truy vấn mới:

```sql
SELECT * FROM users;
```

And we would deploy that code to production *immediately* following the migration.
