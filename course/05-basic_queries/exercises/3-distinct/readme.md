# Distinct - Gộp các trùng thành 1

Sometimes we want to retrieve records from a table without getting back any duplicates.

For example, we may want to know all the different companies our employees have worked at previously, but we don't want to see the same company multiple times in the report.

Đôi khi chúng ta muốn truy xuất các bản ghi từ một bảng mà không lấy lại bất kỳ bản sao nào.

Ví dụ: chúng tôi có thể muốn biết tất cả các công ty khác nhau mà nhân viên của chúng tôi đã làm việc trước đây nhưng chúng tôi không muốn nhìn thấy cùng một công ty nhiều lần trong báo cáo.

## SELECT DISTINCT

SQL offers us the `DISTINCT` keyword that removes duplicate records from the resulting query.

```SQL
SELECT DISTINCT previous_company
    FROM employees;
```

This only returns one row for each unique `previous_company` value.

## Assignment

*CashPal* executives want to know how many countries we have customers in. We store `country_code` data as a column on the `users` table.

Run a `DISTINCT` query to get all the unique `country_code`s from the `users` table.

```SQL
-- Gộp các country_code bị trùng nhau trong bảng users thành 1
SELECT DISTINCT country_code FROM users
```
