# No Tables

When working on a back-end application, this doesn't come up often, but it's important to remember that **SQL is a full programming language**. We usually use it to interact with data stored in tables, but it's quite flexible and powerful.

For example, you can `SELECT` information that's simply calculated, with no tables necessary.

Khi làm việc trên một ứng dụng back-end, điều này không thường xuyên xảy ra, nhưng điều quan trọng cần nhớ là **SQL là ngôn ngữ lập trình đầy đủ**. Chúng ta thường sử dụng nó để tương tác với dữ liệu được lưu trữ trong bảng, nhưng nó khá linh hoạt và mạnh mẽ.

Ví dụ: bạn có thể `CHỌN` thông tin được tính toán đơn giản mà không cần bảng.

```SQL
SELECT 5 + 10 as sum;
```

## Assignment

Finance has found that people who have lived longer than `40` years need to start thinking about retirement. Write a query that returns all the `users` who are more than `40` years old. Unfortunately, this table awkwardly stores age in *days* in the `age_in_days` field.

Use a subquery to convert `years` -> `days` and filter on that. Assume every year has `365` days.


Tài chính nhận thấy rằng những người sống lâu hơn 40 tuổi cần bắt đầu nghĩ đến việc nghỉ hưu. Viết một truy vấn trả về tất cả `users` trên `40` tuổi. Thật không may, bảng này lưu trữ tuổi theo *days* trong trường `age_in_days` một cách bất tiện.

Sử dụng truy vấn con để chuyển đổi `years` -> `days` và lọc theo đó. Giả sử mỗi năm có `365` ngày.

```SQL
SELECT * FROM users
WHERE age_in_days > (
  SELECT 365 * 40
)

```