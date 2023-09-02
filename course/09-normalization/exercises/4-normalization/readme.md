# Database normalization

Database normalization is a method for structuring your database schema in a way that helps:

Chuẩn hóa cơ sở dữ liệu là một phương pháp cấu trúc lược đồ cơ sở dữ liệu của bạn theo cách giúp:

* Improve data integrity - Cải thiện tính toàn vẹn dữ liệu
* Reduce data redundancy - Giảm dư thừa dữ liệu

@[youtube](https://www.youtube.com/watch?v=Tkekmm1XEMQ)

## What is data integrity? Tính toàn vẹn dữ liệu là gì?

"Data integrity" refers to the accuracy and consistency of data. For example, if a user's *age* is stored in a database, rather than their *birthday*, that data becomes incorrect automatically with the passage of time.

It would be better to *store* a birthday and *calculate* the age as needed.

"Tính toàn vẹn của dữ liệu" đề cập đến tính chính xác và nhất quán của dữ liệu. Ví dụ: nếu *tuổi* của người dùng được lưu trữ trong cơ sở dữ liệu, thay vì *ngày sinh* của họ, thì dữ liệu đó sẽ tự động không chính xác theo thời gian.

Sẽ tốt hơn nếu *lưu trữ* ngày sinh và *tính* tuổi nếu cần.

- Có nghĩa lưu trữ tuổi thì nên lưu 1 cách tính tự động, thay vì lưu cứng tuổi, thì lưu ngày thánh năm sinh xong dùng hàm tính toán nào đó để tính toán ra tuổi hiện tại của họ.

## What is data redundancy? - Dự phòng dữ liệu là gì?

"Data redundancy" occurs when the same piece of data is stored in multiple places. For example: saving the same file multiple times to different hard drives.

Data redundancy can be problematic, especially when data in one place is changed such that the data is no longer consistent across all copies of that data.

"Dự phòng dữ liệu" xảy ra khi cùng một phần dữ liệu được lưu trữ ở nhiều nơi. Ví dụ: lưu cùng một tệp nhiều lần vào các ổ cứng khác nhau.

Dự phòng dữ liệu có thể có vấn đề, đặc biệt khi dữ liệu ở một nơi bị thay đổi khiến dữ liệu không còn nhất quán trên tất cả các bản sao của dữ liệu đó.


