# HTTP CRUD Database lifecycle

It's important to understand how data *flows* through a typical web application.

Điều quan trọng là phải hiểu cách dữ liệu *dòng chảy* qua một ứng dụng web thông thường.

![database flow](https://i.imgur.com/hli3crD.png)

Luồng cơ sở dữ liệu

1. The front-end processes some data from user input - maybe a form is submitted.
2. The front-end sends that data to the server through an HTTP request - maybe a `POST`.
3. The server makes a SQL query to it's database to create an associated record - Probably using an `INSERT` statement.
4. Once the server has processed that the database query was successful, it responds to the front-end with a status code! Hopefully a 200-level code (success)!

1. Giao diện người dùng xử lý một số dữ liệu từ đầu vào của người dùng - có thể một biểu mẫu được gửi.
2. Giao diện người dùng gửi dữ liệu đó đến máy chủ thông qua yêu cầu HTTP - có thể là `POST`.
3. Máy chủ thực hiện một truy vấn SQL tới cơ sở dữ liệu của nó để tạo bản ghi liên quan - Có thể sử dụng câu lệnh `INSERT`.
4. Khi máy chủ đã xử lý rằng truy vấn cơ sở dữ liệu thành công, nó sẽ phản hồi giao diện người dùng bằng mã trạng thái! Hy vọng mã 200 cấp (thành công)!