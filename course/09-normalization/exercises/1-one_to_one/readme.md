# Table Relationships

Relational databases are powerful because of the relationships between the tables. These relationships help us to keep our databases clean and efficient. A relationship between tables assumes that one of these tables has a `foreign key` that references the `primary key` of another table.

Cơ sở dữ liệu quan hệ rất mạnh mẽ nhờ mối quan hệ giữa các bảng. Những mối quan hệ này giúp chúng tôi giữ cho cơ sở dữ liệu của mình sạch sẽ và hiệu quả. Mối quan hệ giữa các bảng giả định rằng một trong các bảng này có `khóa ngoại` tham chiếu đến `khóa chính` của bảng khác.

@[youtube](https://www.youtube.com/watch?v=WJTdg1AsSz0)

## Types of Relationships

There are 3 primary types of relationships in a relational database: - Có 3 loại mối quan hệ chính trong cơ sở dữ liệu quan hệ

1. One-to-one - 1-1
2. One-to-many - 1-n
3. Many-to-many - n-n

![relationships](https://i.imgur.com/u4i6XdL.png)

# One-to-one

A `one-to-one` relationship most often manifests as a field or set of fields on a row in a table. For example, a `user` will have exactly one `password`.

Settings fields might be another example of a one-to-one relationship. A user will have exactly one `email_preference` and exactly one `birthday`.


Mối quan hệ `một-một` thường được biểu hiện dưới dạng một trường hoặc tập hợp các trường trên một hàng trong bảng. Ví dụ: một `user` sẽ có chính xác một `password`.

Các trường cài đặt có thể là một ví dụ khác về mối quan hệ một-một. Một người dùng sẽ có chính xác một `email_preference` và chính xác một `birthday`.

