# Many to many

A many-to-many relationship occurs when multiple records in one table can be related to multiple records in another table.

Mối quan hệ nhiều-nhiều xảy ra khi nhiều bản ghi trong một bảng có thể liên quan đến nhiều bản ghi trong một bảng khác.

## Examples of many-to-many relationships - Ví dụ về mối quan hệ nhiều nhiều

* A `products` table and a `suppliers` table - Products may have `0` to many suppliers, and suppliers can supply `0` to many products.
* A `classes` table and a `students` table - Students can take potentially many classes and classes can have many students enrolled.

* Bảng `sản phẩm` và bảng `nhà cung cấp` - Sản phẩm có thể có `0` cho nhiều nhà cung cấp và nhà cung cấp có thể cung cấp `0` cho nhiều sản phẩm.
* Bảng `lớp` và bảng `sinh viên` - Học sinh có thể học nhiều lớp và lớp có thể có nhiều học sinh đăng ký.

1 sản phẩm có nhiều nhà cung cấp, 1 nhà cung cấp có thể cung cấp nhiều sản phẩm

1 lớp có nhiều sinh viên và 1 sinh viên có thể tham gia nhiều lớp học

Ta có thể thấy được mối tương quan giữa các bản

## Joining table

Joining tables help define many-to-many relationships between data in a database. As an example when defining the relationship above between products and suppliers, we would define a joining table called `products_suppliers` that contains the primary keys from the tables to be joined.

Then, when we want to see if a supplier supplies a specific product, we can look in the joining table to see if the ids share a row.

Việc nối các bảng giúp xác định mối quan hệ nhiều-nhiều giữa dữ liệu trong cơ sở dữ liệu. Ví dụ: khi xác định mối quan hệ ở trên giữa sản phẩm và nhà cung cấp, chúng tôi sẽ xác định một bảng nối có tên là `products_suppliers` chứa các khóa chính từ các bảng được nối.

Sau đó, khi chúng tôi muốn xem liệu nhà cung cấp có cung cấp một sản phẩm cụ thể hay không, chúng tôi có thể xem trong bảng nối để xem các id có chia sẻ một hàng hay không.

## Unique Constraint across 2 fields - Ràng buộc duy nhất trên 2 trường

When enforcing specific schema constraints we may need to enforce the `UNIQUE` constraint across two different fields.

Khi thực thi các ràng buộc lược đồ cụ thể, chúng ta có thể cần thực thi ràng buộc `UNIQUE` trên hai trường khác nhau.

```SQL
CREATE TABLE product_suppliers (
  product_id INTEGER,
  supplier_id INTEGER,
  UNIQUE(product_id, supplier_id)
);
```

This ensures that we *can* have multiple rows with the same `product_id` or `supplier_id`, but we can't have two rows where *both* the `product_id` and `supplier_id` are the same.

Điều này đảm bảo rằng chúng tôi *có thể - can* có nhiều hàng có cùng `product_id` hoặc `supplier_id`, nhưng chúng tôi không thể có hai hàng trong đó *cả hai- both* `product_id` và `supplier_id` đều giống nhau.

## Assignment

We have *another* issue with our current user<->country relationship! In the current schema, a user can have many countries associated with it, but there are duplicate records! If two user's are associated with the United States, we're creating two `countries` records.

It would be better if each country only had a single record. That way, when a country changes its metadata (for example, it decides to rename itself) we only have to update *one* record.

Use a joining table to de-deduplicate country data.

* Remove the `user_id` field from the `countries` table
* Create a new table called `users_countries`. It should have two fields:
  * `country_id`
  * `user_id`
* Add a "unique together" constraint on those id fields


Chúng tôi có *một vấn đề khác* với mối quan hệ quốc gia<->người dùng hiện tại của chúng tôi! Trong lược đồ hiện tại, một người dùng có thể có nhiều quốc gia được liên kết với nó, nhưng có những bản ghi trùng lặp! Nếu hai người dùng được liên kết với Hoa Kỳ, chúng tôi sẽ tạo hai bản ghi `quốc gia`.

Sẽ tốt hơn nếu mỗi quốc gia chỉ có một kỷ lục duy nhất. Bằng cách đó, khi một quốc gia thay đổi siêu dữ liệu của mình (ví dụ: quốc gia đó quyết định đổi tên chính mình), chúng tôi chỉ phải cập nhật bản ghi *một*.

Sử dụng bảng nối để loại bỏ dữ liệu quốc gia trùng lặp.

* Xóa trường `user_id` khỏi bảng `countries`
* Tạo một bảng mới tên là `users_countries`. Nó phải có hai trường:
   * `country_id`
   * `user_id`
* Thêm ràng buộc "duy nhất cùng nhau" trên các trường id đó

Tham khảo:

```SQL
CREATE TABLE users (
  id INTEGER PRIMARY KEY,
  name TEXT NOT NULL,
  age INTEGER NOT NULL,
  username TEXT UNIQUE,
  password TEXT NOT NULL,
  is_admin BOOLEAN
);

CREATE TABLE countries (
  id INTEGER PRIMARY KEY,
  country_code TEXT,
  name TEXT,
);

CREATE TABLE users_countries (
  country_id INTEGER,
  user_id INTEGER
  
  FOREIGN KEY (country_id) REFERENCES users(id), 
  FOREIGN KEY (user_id) REFERENCES countries(id),

  UNIQUE (country_id, user_id)
)
```

Lời giải:

```SQL
CREATE TABLE users (
  id INTEGER PRIMARY KEY,
  name TEXT NOT NULL,
  age INTEGER NOT NULL,
  username TEXT UNIQUE,
  password TEXT NOT NULL,
  is_admin BOOLEAN
);

CREATE TABLE users_countries (
  country_id INTEGER,
  user_id INTEGER,
  UNIQUE(country_id, user_id)
);

CREATE TABLE countries (
  id INTEGER PRIMARY KEY,
  country_code TEXT,
  name TEXT
);
```