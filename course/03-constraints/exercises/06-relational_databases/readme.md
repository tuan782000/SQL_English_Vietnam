# Relational Databases

We have been using the term *relational* quite a bit, it's time we actually go over what that means! A *relational* database is a type of database that stores data so that it can be easily related to other data. For example, a `user` can have many `tweets`. There's a relationship between a `user` and their `tweet`.

Chúng ta đã sử dụng thuật ngữ *relational* khá nhiều, đã đến lúc chúng ta thực sự tìm hiểu ý nghĩa của nó! Cơ sở dữ liệu *relational* là một loại cơ sở dữ liệu lưu trữ dữ liệu để có thể dễ dàng liên kết với dữ liệu khác. Ví dụ: một `user` có thể có nhiều `tweets`. Có một mối quan hệ giữa `user` và `tweet` của họ.

In a relational database: Trong một mối quan hệ database

1. Data is typically represented in "tables". - Dữ liệu thường được biểu diễn dưới dạng "bảng".

2. Each table has "columns" or "fields that hold attributes related to the record. - Mỗi bảng có "cột" hoặc "trường" có chứa thuộc tính liên quan đến bảng ghi.

3. Each row or entry in the table is called a [record](https://en.wikipedia.org/wiki/Record_(computer_science)). - Mỗi hàng hoặc mục trong bảng được gọi là một bảng ghi.

4. Typically, each record has a unique `Id` called the [primary key](https://en.wikipedia.org/wiki/Primary_key). - Thông thường, mỗi bản ghi có 1 `Id` duy nhất được gọi là khóa chính.

## Example Relational Database

![Relational Database](https://i.imgur.com/Ogx4ICa.jpg)

Here is an example of a small relational database. This database has 3 tables, `Students`, `Courses`, and `StudentCourses`. The `StudentCourses` table manages the relationship between the `Students` and the `Courses` tables. 

Ở đây một ví dụ nhỏ một mối quan hệ. Trong ví dụ có 3 bảng `Students`, `Courses`, và `StudentCourses`. Bảng `StudentCourses` mối quan hệ giữa `Students` và `Courses`.

## Example 1: Sam

* Sam has an `Id` of `1`
* We can find Sam's courses by looking in the `StudentCourses` for the records that match his `StudentId`.

Sam có 1 cột `Id` là `1`
Chúng ta có thể nhìn thấy khóa học trong bảng `StudentCourses` bằng cách đối chiếu `StudentId`.

## Example 2: MongoDB

* `MongoDB` has an `Id` of 3
* We can find all the students enrolled in the MongoDB course by checking the `StudentCourses` table


Bảng Students

Bảng StudentCourses (Mối quan hệ n-n)

Bảng Courses




