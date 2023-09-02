# Altering Tables - Chỉnh sửa Bảng

We often need to alter our database schema without deleting it and re-creating it. Imagine if Twitter deleted its database each time it needed to add a feature, that would be a *disaster*! Your account and all your tweets would be wiped out on a daily basis.

Chúng ta thường cần thay đổi lược đồ cơ sở dữ liệu của mình mà không xóa và tạo lại nó. Hãy tưởng tượng nếu Twitter xóa cơ sở dữ liệu của mình mỗi khi cần thêm một tính năng thì đó sẽ là một *thảm họa*! Tài khoản của bạn và tất cả các tweet của bạn sẽ bị xóa hàng ngày.

Instead, we can use use the `ALTER TABLE` statement to make changes in place without deleting any data.

Thay vào đó, chúng ta có thể sử dụng câu lệnh `ALTER TABLE` để thực hiện các thay đổi tại chỗ mà không xóa bất kỳ dữ liệu nào.

## ALTER TABLE

With SQLite an `ALTER TABLE` statement allows you to:

Với SQLite, câu lệnh `ALTER TABLE` cho phép bạn:

### 1. Rename a table or column - Thay đổi tên bảng hoặc column

```SQL
-- Câu lệnh này thay đổi tên của "bảng" employees thành contractors
ALTER TABLE employees
RENAME TO contractors;

-- Câu lệnh này thay đổi tên của "cột" salary thành invoice trong bảng contractors
ALTER TABLE contractors
RENAME COLUMN salary TO invoice;

```

### 2. ADD or DROP a column - Thêm hoặc Bỏ 1 cột

```SQL
-- Câu lệnh sau là thêm một cột hoàn toàn mới có tên là job_title vào trong bảng contractors
ALTER TABLE contractors
ADD COLUMN job_title TEXT;

-- Câu lệnh sau là xóa cột có tên là is_manager ra khỏi bảng contractors
ALTER TABLE contractors
DROP COLUMN is_manager;
```

## Assignment

We need to make some changes to the `people` table! At the moment, we have these five columns (shown as rows so we can display datatypes):

| CID | NAME     | TYPE    | NOTNULL | DFLT VALUE | PK  |
| --- | -------- | ------- | ------- | ---------- | --- |
| 0   | id       | INTEGER | 0       |            | 0   |
| 1   | handle   | TEXT    | 0       |            | 0   |
| 2   | name     | TEXT    | 0       |            | 0   |
| 3   | age      | INTEGER | 0       |            | 0   |
| 4   | balance  | INTEGER | 0       |            | 0   |
| 5   | is_admin | BOOLEAN | 0       |            | 0   |

1. Rename the table to `users`
2. Rename the `handle` column to `username`.
3. Add the `password` (TEXT) column. 

1. Đổi tên bảng hiện tại thành users
```SQL
ALTER TABLE people
RENAME TO users;
```

2. ĐỔi tên cột handle thành username của bảng users
```SQL
ALTER TABLE users
RENAME COLUMN handle TO username;
```

3. Thêm cột password có giá trị TEXT vào bảng.
```SQL
ALTER TABLE users
ADD COLUMN password TEXT;
```


