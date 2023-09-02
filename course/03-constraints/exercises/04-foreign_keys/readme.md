# Foreign Keys

Foreign keys are what makes relational databases relational! Foreign keys define the relationships *between* tables. Simply put, a `FOREIGN KEY` is a field in one table that references another table's `PRIMARY KEY`.

Khóa ngoại là thứ làm cho cơ sở dữ liệu quan hệ trở nên quan hệ! Khóa ngoại xác định mối quan hệ *giữa* các bảng. Nói một cách đơn giản, `KHÓA NGOÀI` là một trường trong một bảng tham chiếu đến `KHÓA CHÍNH` của bảng khác.

## Creating a Foreign Key in SQLite - Tạo khóa ngoài

Creating a `FOREIGN KEY` in SQLite happens at table creation! After we define the table fields and constraints we add an additional `CONSTRAINT` where we define the `FOREIGN KEY` and its `REFERENCES`.

Việc tạo `KHÓA NGOÀI` trong SQLite xảy ra khi tạo bảng! Sau khi xác định các trường và ràng buộc của bảng, chúng tôi thêm một `CONSTRAINT` bổ sung trong đó chúng tôi xác định `KHÓA NGOÀI` và `REFERENCES` của nó.

Here's an example: - Đây là một ví dụ

```SQL
-- 1 departments có n employees => đặt khóa ngoại tại employees
CREATE TABLE departments (
    id INTEGER PRIMARY KEY,
    department_name TEXT NOT NULL
);

CREATE TABLE employees (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    department_id INTEGER,
    CONSTRAINT fk_departments
    FOREIGN KEY (department_id)
    REFERENCES departments(id)
);
```

In this example, an `employee` has a `department_id`. The `department_id` must be the same as the `id` field of a record from the `departments` table.

Trong ví dụ này, `employee` có `department_id`. `department_id` phải giống với trường `id` của bản ghi từ bảng `departments`.

## Assignment

Our `users` table stores the country our users are from in a `country_code` field. We need some additional data about countries like their name, but we don't want to bloat our `users` table with all that country data.

Bảng `users` của chúng tôi lưu trữ quốc gia mà người dùng của chúng tôi đến từ trường `country_code`. Chúng tôi cần một số dữ liệu bổ sung về các quốc gia như tên của họ, nhưng chúng tôi không muốn làm đầy bảng `users` của mình với tất cả dữ liệu quốc gia đó.

The "locations" team at CashPal has created a "countries" table, and we can link a user to their country by setting a foreign key in the `users` table.

Nhóm "locations" tại CashPal đã tạo bảng "countries" và chúng tôi có thể liên kết người dùng với quốc gia của họ bằng cách đặt khóa ngoại trong bảng `users`.

Take a look at the code. There's an issue with the `INSERT` statements again! Fix up the data so no foreign key constraints are violated. You'll need to reference the *setup* code below.

Hãy nhìn vào mã. Lại xảy ra sự cố với câu lệnh `INSERT`! Sửa dữ liệu để không có ràng buộc khóa ngoại nào bị vi phạm. Bạn sẽ cần tham khảo mã *setup* bên dưới.

```SQL

-- Thêm dữ liệu vào bảng users
-- Bổ sung "trường" country_code có "giá trị" US
-- Bổ sung "trường" country_code có "giá trị" IN

INSERT into users (
    id,
    name,
    country_code
) values (
    0,
    "Jerry",
    "US"
);

INSERT into users (
    id,
    name,
    country_code
) values (
    1,
    "Amit",
    "IN"
);

```

