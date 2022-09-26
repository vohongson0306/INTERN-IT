<img src="https://phanmemgoc.vn/wp-content/uploads/2020/04/Sql-server.png">

# 1.Khái niệm
Phần mềm được Microsoft phát triển dựa trên RDBMS(hệ quản lý cơ sở dữ liệu quan hệ).
Cũng là một ORDBMS (Hệ quản trị cơ sở dữ liệu quan hệ đối tượng).
Một nền tảng độc lập.
Phần mềm sử dụng cả giao diện dòng lệnh và giao diện GUI.
Hỗ trợ ngôn ngữ SQL (trước đây là SEQUEL - ngôn ngữ truy vấn tiếng Anh có cấu trúc) - vốn là sản phẩm của IBM.

# 2.Mục đích sử dụng
- Tạo cơ sở dữ liệu.
- Duy trì cơ sở dữ liệu.
- Phân tích dữ liệu bằng SSAS - SQL Server Analysis Services.
- Tạo báo cáo bằng SSRS - SQL Server Reporting Services.
- Thực hiện quá trình ETL (Extract-Transform-Load) bằng SSIS SQL Server Integration Services.

# 3.Các thành phần cơ bản trong Sql Server
- Database Engine: Đây là một engine có khả năng chứa dữ liệu ở các quy mô dưới dạng support và table. Ngoài ra, nó còn có khả năng tự điều chỉnh ví dụ: trả lại tài nguyên cho hệ điều hành khi một user log off và sử dụng thêm các tài nguyên của máy khi cần.
- Integration Services: là tập hợp các đối tượng lập trình và các công cụ đồ họa cho việc sao chép, di chuyển và chuyển đổi dữ liệu.  Khi bạn làm việc trong một công ty lớn thì dữ liệu được lưu trữ ở nhiều nơi khác nhau như được chứa trong: Oracle, SQL Server, DB2, Microsoft Access,… và bạn chắc chắn sẽ có nhu cầu di chuyển dữ liệu giữa các server này. Ngoài ra, bạn còn muốn định dạng dữ liệu trước khi lưu vào database. Chắc chắn Integration Services sẽ giúp bạn giải quyết được công việc này dễ dàng.
- Analysis Services: Đây là một dịch vụ phân tích dữ liệu rất hay của Microsoft. Dữ liệu khi được lưu trữ vào trong database mà bạn không thể lấy được những thông tin bổ ích thì coi như không có ý nghĩa gì. Chính vì thế, công cụ này ra đời giúp bạn trong việc phân tích dữ liệu một cách hiệu quả và dễ dàng bằng cách dùng kỹ thuật khai thác dữ liệu – datamining và khái niệm hình khối nhiều chiều – multi dimendion cubes.
- Notification Services: Dịch vụ thông báo này là nền tảng cho sự phát triển và triển khai các ứng dụng soạn và gửi thông báo. Ngoài ra, dịch vụ này còn có chức năng gửi thông báo theo dịch thời đến hàng ngàn người dăng ký sử dụng trên nhiều loại thiết bị khác nhau.
- Reporting  Services: là một công cụ tạo, quản lý và triển khai báo cáo bao gồm: server và client. Ngoài ra, nó còn là nền tảng cho việc phát triển và xây dựng các ứng dụng báo cáo.
- Full Text Search Service: là một thành phần đặc biệt trong việc truy vấn và đánh chỉ mục dữ liệu văn bản không cấu trúc được lưu trữ trong các cơ sở dữ liệu SQL Server.+ Service Broker: là một môi trường lập trình cho việc tạo ra các ứng dụng trong việc nhảy qua các Instance.
