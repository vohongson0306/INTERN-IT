<img src="https://mga.vn/wp-content/uploads/2019/09/pop3-2@4x.png">

# Tìm hiểu giao thức nhận email POP3
- POP3 là viết tắt của Post Office Protocol version 3 là một giao thức tầng ứng dụng, dùng để lấy thư điện tử từ server mail, thông qua kết nối TCP/IP. POP3 được sử dụng để kết nối tới server email và tải email xuống máy tính cá nhân thông qua ứng dụng email client như Outlook, Thunderbird, Windows Mail, Mac Mail…
- POP là một giao thức nhận mail có lịch sử lâu đời. Nó ra đời từ máy tính còn bị giới hạn bởi tốc độ, băng thông, vậy nên các kỹ sư đã tạo ra POP, một nỗ lực để làm đơn giản nhất có thể để tải các bản copy của email để đọc khi offline, sau đó xóa những email này từ remote server.
## Cơ chế hoạt động của POP:
- Kết nối đến server.
- Nhận toàn bộ mail.
- Lưu cục bộ như mail mới.
- Xóa mail trên server.
- Ngắt kết nối với server.
## Mặc định, port POP3 là:
 - Port 110 – port không mã hóa
 - Port 995 – SSL/TLS port, cũng có thể được gọi là POP3S
## Nhược điểm của POP3:
Mỗi lần nhận mail, POP sẽ download email đó về máy local (và mặc định xóa mail trên server đi) nên bạn sẽ không thể sử dụng nhiều thiết bị để quản lý cùng một tài khoản email qua giao thức POP. Tuy nhiên, bạn có thể cấu hình email client để POP3 không xóa email trên server mà chỉ “mask as read” – đánh dấu đã đọc với những email đó.
## Ưu điểm của POP3:
- Mail được lưu cục bộ, tức luôn có thể truy cập ngay cả khi không có kết nối Internet.
- Kết nối Internet chỉ dùng để gửi và nhận mail.
- Tiết kiệm không gian lưu trữ trên server.
- Được lựa chọn để lại bản sao mail trên server.
- Hợp nhất nhiều tài khoản email và nhiều server vào một hộp thư đến.

<img src="https://mga.vn/wp-content/uploads/2019/09/imap-3@4x.png">

# Tìm hiểu giao thức nhận email IMAP
- IMAP là viết tắt của Internet Message Access Protocol, là giao thức chuẩn Internet được sử dụng bởi các ứng dụng email để truy xuất thư email từ máy chủ thư qua kết nối TCP/IP. IMAP được tạo ra vào năm 1986 nhưng nó vẫn phù hợp với công nghệ hiện đại thời nay. Ý tưởng của nó là thay vì người dùng cứ phải ràng buộc vào một email client nào đó, mà người dùng có thể check mail ngay trên đám mây internet từ bất kỳ thiết bị, ứng dụng nào.
## Cơ chế hoạt động của IMAP:
- Kết nối đến server.
- Lấy nội dung được yêu cầu từ người dùng và lưu đệm cục bộ (chẳng hạn như danh sách mail mới, tổng kết tin nhắn hay nội dung của những email được chọn lựa kỹ càng)
- Xử lý các biên tập từ người dùng, ví dụ như đánh dấu email là mail để đọc hay xóa…
- Ngắt kết nối với server.
## Mặc định, port IMAP là:
- Port 143 – port không mã hóa
- Port 993 – SSL/TLS port, cũng có thể được gọi là IMAPS
## Nhược điểm của IMAP:
- Vì IMAP lưu các email trên mail server, nên dung lượng hòm thư của bạn sẽ bị giới hạn bởi các nhà cung cấp dịch vụ mail. Nếu bạn có một lượng lớn email cần lưu trữ, bạn sẽ gặp nhiều vấn đề khi gửi nhận mail khi hòm thư bị đầy. Nhiều người giải quyết vấn đề này bằng cách tạo một bản sao copy của các email đó thông qua mail client, sau đó xóa bỏ email gốc trên server. Ngoài ra nếu bạn sử dụng Gmail theo tên miền và vượt quá giới hạn dung lượng mặc định là 15GB/tài khoản, bạn có thể mua thêm dung lượng tài khoản với giá từ 700k / năm.

- Ngoài ra, nếu sử dụng IMAP thì bạn cần phải có kết nối Internet nếu muốn truy cập email (IMAP chỉ kéo email headers về, nội dung email vẫn còn trên server).

## Ưu điểm của IMAP:

- Mail được lưu trên server đầu xa, tức có thể truy cập từ nhiều địa điểm khác nhau.
- Xem nhanh hơn khi chỉ có các tiêu đề mail được tải về đến khi nội dung được yêu cầu rõ ràng.
- Mail được dự phòng tự động trên server.
- Tiết kiệm không gian lưu trữ cục bộ.
- Vẫn cho phép lưu mail cục bộ (nếu bạn cấu hình).

# Tìm hiểu giao thức SMTP:























