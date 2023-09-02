# Order By and Limit

When using both `ORDER BY` and `LIMIT`, the `ORDER BY` clause must come *first*.

Khi sử dụng cả `ORDER BY` và `LIMIT`, mệnh đề `ORDER BY` phải xuất hiện *đầu tiên*.

## Assignment

An HR employee got into the Git repository where we store all the queries and tried to update one himself.

Fix the bug in the SQL query.

```SQL
SELECT * from transactions
WHERE amount BETWEEN 10 and 80
ORDER BY amount desc
LIMIT 4;

```





