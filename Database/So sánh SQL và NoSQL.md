# I.Tổng Quan
## 1.SQL
<img src="https://blog.kdata.vn/wp-content/uploads/2020/10/sql-va-nosql-so-sanh-loai-hinh-co-so-du-lieu-pho-bien-nhat-hien-nay-2-768x480.jpg">

- SQL (viết tắt của Structured Query Language) là ngôn ngữ truy vấn cấu trúc. Nó được dùng để xử lý cơ sở dữ liệu quan hệ. SQL được chia thành các mệnh đề, biểu thức, toán tử, truy vấn và truy vấn con.
- Lập trình SQL có thể được sử dụng hiệu quả để chèn, tìm kiếm, xóa bản ghi, cập nhật cơ sở dữ liệu. SQL có thể làm được rất nhiều thứ, không giới hạn các việc như tối ưu hóa và duy trì cơ sở dữ liệu. Các cơ sở dữ liệu quan hệ như cơ sở dữ iệu MysSQL, Oracle, MS SQL, Sybase,…
## 2.NoSQL
<img src="https://blog.kdata.vn/wp-content/uploads/2020/10/sql-va-nosql-so-sanh-loai-hinh-co-so-du-lieu-pho-bien-nhat-hien-nay-3-1-768x398.jpg">

- NoSQL (viết tắt của Non-Relationla SQL) được sử dụng với mục đích gần giống với SQL. Nhưng nó là đối với cơ sở dữ liệu không quan hệ, không yêu cầu một lược đồ cố định và dễ dàng mở rộng. Cơ sở dữ liệu NoSQL được sử dụng cho các kho dữ liệu phân tán với nhu cầu lưu trữ dữ liệu khổng lồ. NoSQL được sử dụng cho Big Data và các ứng dụng web thời gian thực.
- Một hệ thống cơ sở dữ liệu NoSQL bao gồm một loạt các công nghệ cơ sở dữ liệu có thể lưu trữ dữ liệu có cấu trúc, bán cấu trúc, không có cấu trúc và đa hình.

# II.So sánh sự khác nhau giữa SQL và NoSQL
<img src="https://blog.kdata.vn/wp-content/uploads/2020/10/so-sanh-sql-va-nosql-hai-loai-hinh-co-so-du-lieu-pho-bien-nhat-3-1-768x576.jpg">

## Loại hình
- SQL databases là cơ sở dữ liệu dựa trên bảng và các bảng này có quan hệ với nhau. Chẳng hạn thông tin books trong bảng được đặt tên books. Mỗi một row ứng với một record, mỗi column ứng với mỗi field dữ liệu.
- NoSQL databases có thể dựa trên cặp tài liệu, cặp khóa giá trị từng cặp một, cơ sở dữ liệu biểu đồ.
## Ngôn ngữ Query
- SQL: Structured Query Language.
- NoSQL: Không có ngôn ngữ Query.
## Khả năng mở rộng
- SQL: Có thể mở rộng theo chiều dọc. Trong SQL databases, bạn có thể thêm dữ liệu nếu tạo bảng và field types tương ứng được gọi là schema. Schema chứa những thông tin về database mà bạn đang sử dụng như: indexes, primary keys, relationships,… Do đó schema phải được design và implements đầu tiên. Tuy nhiên nó cũng có thể update sau nhưng những thay đổi lớn sẽ trở nên phức tạp hơn khi nhìn vào file schema.
- NoSQL: Có thể mở rộng theo chiều ngang. Dữ liệu có thể được add mọi nơi và bất kỳ lúc nào. Chính vì vậy mà nó phù hợp hơn cho các dự án mà yêu cầu dữ liệu ban đầu rất khó xác định.
## Lưu trữ dữ liệu phân cấp
- SQL: Không thích hợp cho việc lưu trữ dữ liệu phân cấp.
- NoSQL: Phù hợp cho kho lưu trữ dữ liệu phân cấp vì nó hỗ trợ phương thức cặp khóa – giá trị.
## Mục đích sử dụng
- SQL: Được thiết kế dành cho các ứng dụng xử lý giao dịch trực tuyến, trong giao dịch có độ ổn định cao và thích hợp để xử lý phân tích trực tuyến.
- NoSQL: Được thiết kế phục vụ cho việc phân tích dữ liệu có cấu trúc chưa hoàn chỉnh.
## Lựa chọn sử dụng
- SQL: Những dự án đã có yêu cầu dữ liệu rõ ràng xác định quan hệ logic có thể được xác định trước.
- NoSQL: Dự án yêu cầu dữ liệu không liên quan, khó xác định, đơn giản mềm dẻo khi đang phát triển.
## Mã nguồn
- SQL: Kết hợp của các mã nguồn mở như Postgres & MySQL và thương mại như Oracle Database.
- NoSQL: Open-source.
## Hiệu suất
- NoSQL thường được cho là nhanh hơn SQL. Điều này không đáng ngạc nhiên, NoSQL thì denormalized cho phép bạn lấy được tất cả thông tin về một item cụ thể với các codition mà không cần join liên quan hoặc truy vấn SQL phức tạp.
- Để hệ thống SQL hoạt động tốt và nhanh thì việc design tốt là cực kỳ quan trọng và ngược lại.
## Transactions
- SQL: Hai hoặc nhiều record update có thể được thực hiện trong một transaction. Đảm bảo tất cả update thành công hoặc nếu 1 record update fails thì sẽ rollback lại toàn bộ các record khác. Điều này đảm bảo tính đồng nhất cho dữ liệu.
- NoSQL: Việc sửa đổi document là riêng lẻ. Nếu bạn đang cập nhật ba giá trị trong một document, cả ba đều được cập nhật thành công hoặc nó vẫn không thay đổi. Tuy nhiên, không có transaction tương dương để update cho nhiều document. Có những option tương tự như transaction nhưng chúng phải được xử lý thủ công trong khi viết code.

## Lý do sử dụng SQL?
Khi nhắc đến công nghệ cơ sở dữ liệu, không có một lựa chọn phù hợp với tất cả các giải pháp. Đó là lý do tại sao nhiều doanh nghiệp dựa lựa chọn cơ sở dữ liệu quan hệ và không quan hệ cho các nhiệm vụ khác nhau. Ngay cả khi cơ sở dữ liệu NoSQL vốn nổi tiếng về tốc độ và khả năng mở rộng quan hệ thì vẫn có những tình huống mà cơ sở dữ liệu SQL có cấu trúc cao có thể thích hợp hơn.

Dữ liệu của bạn được cấu trúc và không thay đổi. Nếu doanh nghiệp của bạn không trải qua sự tăng trưởng to lớn đòi hỏi nhiều máy chủ hơn và bạn chỉ làm việc với dữ liệu phù hợp thì có thể không có lý do gì để sử dụng một hệ thống được thiết kế để hỗ trợ nhiều loại dữ liệu khác nhau và lưu lượng truy cập cao.

## Lý do sử dụng NoSQL?
Khi tất cả các thành phần khác của ứng dụng máy chủ của bạn được thiết kế nhanh chóng, liền mạch, cơ sở dữ liệu NoSQL ngăn chặn dữ liệu khỏi bị nút cổ chai. Dữ liệu lớn là động lực NoSQL thực sự ở đây, làm những việc mà cơ sở dữ liệu quan hệ truyền thống không thể. Nó thúc đẩy sự phổ biến của các cơ sở dữ liệu NoSQL như MongoDB, CouchDB, Cassandra và Hbase.

Bạn có thể chọn sử dụng NoSQL khi lưu trữ khối lượng lớn dữ liệu có ít hoặc không có cấu trúc. Cơ sở dữ liệu NoSQL không giới hạn các loại dữ liệu khi bạn có thể lưu trữ với nhau và cho phép bạn thêm các loại mới khác nhau khi nhu cầu thay đổi. Với cơ sở dữ liệu dựa trên tài liệu, bạn có thể lưu trữ dữ liệu ở một nơi mà không cần định nghĩa loại dữ liệu nào trước.

Tận dụng tối đa điện toán đám mây và lưu trữ. Lưu trữ cloud là giải pháp tiết kiệm chi phí tuyệt vời, nhưng yêu cầu dữ liệu được dễ dàng lây lan trên nhiều máy chủ để mở rộng quy mô. Cơ sở dữ liệu NoSQL như Cassandra được thiết kế mở rộng trên nhiều trung tâm dữ liệu mà không phải suy nghĩ nhiều.

