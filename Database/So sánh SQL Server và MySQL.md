<img src="https://truonggiangit.com/wp-content/uploads/2019/01/mysql-sqlserver.png">

# 1.MySQL là gì?
- Được phát hành từ giữa thập niên 90s (sau đó bị thâu tóm bởi Oracle), MySQL ban đầu là một database mã nguồn mở và cũng vẫn mở cho tới tận bây giờ. Vì là mã nguồn mở, MySQL có rất nhiều phiên bản khác dựa trên nó. Sự khác biệt giữa các biến thể này là không lớn; cấu trúc và chức năng cơ bản tương đương nhau.
- Một điều đã trở thành đặc tính riêng của MySQL là nó cực kỳ phổ biến trong cộng đồng startup. Vì nó là mã nguồn mở và miễn phí, lập trình viên có thể dễ dàng bắt đầu với MySQL, và chỉnh sửa code nếu họ cần làm vậy. MySQL thường được dùng đồng thời với PHP và Apache Web Server, trên một bản Linux distribution, bộ tứ này đã trở thành một tên gọi nổi tiếng và quyền lực: LAMP (Linux, Apache, MySQL, PHP).
# 2.SQL Server là gì?
- SQL Server, cũng được gọi là Microsoft SQL Server, đã tồn tại thậm chí còn lâu hơn MySQL. Microsoft phát triển SQL Server từ giữa thập niên 80s, với lời hứa RDBMS cung cấp giải pháp đáng tin cậy và có thể mở rộng. Việc này trở thành đặc tính đáng giá của SQL Server cho tới tận bây giời, vì nó là một nền tảng được-chọn cho những phần mềm doanh nghiệp cần-mở-rộng-lớn theo thời gian.
- SQL Server được lập trình viên sử dung khi dùng với .NET, đối trọng của PHP và MySQL. Cả .NET và SQL server đều được bảo vệ dưới cái tên Microsoft.

# 3.Sự khác biệt giữa MySQL và SQL Server
| Đặc điểm | MySQL | SQL Server |
|----------|-------|------------|
| Tính Năng | Cung cấp nhiều loại storage engine hơn. | Intergate cho trọn bộ hệ thống và công cụ phát triển software chặt chẽ và tốt hơn. Ở mảng `.NET.` MSSQL còn hỗ trợ XML trực tiếp trong DB |
| Hiệu Suất | Không đòi hỏi nhiều như SQL Server. Có thể chạy trên các UNIX highend system và perform tốt hơn SQL Server trên Windows highend server trong nhiều trường hợp. | Perform kém hơn MySQL về nhiều mặt. Đòi hỏi tài nguyên rất lớn (CPU mạnh, nhiều RAM). |
| Bảo Mật | MySQL chỉ có thể set access đến row level là hết. | Tính bảo mật cao hơn MySQL ở column level. Hệ thống xác thực cũng cao hơn, chặt chẽ hơn MySQL. Tuy nhiên, dễ bị exploit hơn MySQL.|
| Khả năng nhân bản ( Replication) | MySQL nhanh hơn và ít sự cố hơn SQL Server vì tất cả các SQL statements dùng để thay đổi, cập nhật dữ liệu được lưu giữ trong binary log. | SQL Server cung cấp nhiều phương pháp replication cao cấp hơn, chi tiết hơn nên nó phức tạp và chậm hơn.|
| Khả năng phục hồi ( Recovery) | Nếu MySQL chạy với Innodb thì khả năng phục hồi không thua kém gì SQL Server.| Nếu MySQL chạy thuần túy với MyISAM storage engine thì khả năng phục hồi (sau khi bị crash) không thể so sánh được với SQL Server. SQL phục hồi dễ dàng hơn. | 
| Phí Tổn | MySQL bản community không mất phí nhưng phải tự thủ công. Tuy nhiên, cài đặt, sử dụng và tối ưu MySQL không khó vì tài liệu về nó rất đầy đủ và nhiều có thể tìm thấy trên internet. | Phải trả $1.5 cho một license SQL Server Standard và khi cần support, bạn phải trả thêm tiền support (tùy case). Bản enterprise thì phải trả tiền (khoảng $400) và bạn được support đầy đủ. SQL Server vẫn cung cấp bản miễn phí dành cho mục đích development.|
