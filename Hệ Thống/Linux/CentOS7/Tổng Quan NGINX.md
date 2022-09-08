<img src="https://wiki.tino.org/wp-content/uploads/2019/04/what-is-nginx-750x375.png">

# 1.Khái niệm
NGINX hay còn được viết cách điệu là NGIИX, là một web server mã nguồn mở vô cùng mạnh mẽ và nổi tiếng phục vụ web HTTP. Với NGIИX sử dụng kiến thức đơn luồng, (event-driven) không đồng bộ (asynchronous) để có hiệu suất và sự ổn định tối đa và là lựa chọn ưa chuộng hơn Apache server. Nó có thể phục vụ các công việc như như load balancing, HTTP caching, hay sử dụng như một reverse reverse proxying, media streaming và email proxy như IMAP, POP3, và SMTP….  
# Những tính năng của máy chủ HTTP Nginx
- Có khả năng xử lý hơn 10.000 kết nối cùng lúc với bộ nhớ thấp.
- Phục vụ tập tin tĩnh (static files) và lập chỉ mục tập tin.
- Tăng tốc reverse proxy bằng bộ nhớ đệm (cache), cân bằng tải đơn giản và khả năng chịu lỗi.
- Hỗ trợ tăng tốc với bộ nhớ đệm của FastCGI, wsgi, SCGI, và các máy chủ memcached.
- Kiến trúc modular, tăng tốc độ nạp trang bằng nén gzip tự động.
- Hỗ trợ mã hoá SSL và TLS.
- Cấu hình linh hoạt; lưu lại nhật ký truy vấn
- Chuyển hướng lỗi 3XX-5XX
- Rewrite URL (URL rewriting) dùng regular expressions
- Hạn chế tỷ lệ đáp ứng truy vấn
- Giới hạn số kết nối đồng thời hoặc truy vấn từ 1 địa chỉ
- Khả năng nhúng mã PERL
- Hỗ trợ và tương thích với IPv6
- Hỗ trợ WebSockets
- Hỗ trợ truyền tải file FLV và MP4
# Những phương pháp xác thực máy chủ mail proxy của Nginx
- POP3: USER/PASS, APOP, AUTH LOGIN/PLAIN/CRAM-MD5;
- IMAP: LOGIN, AUTH LOGIN/PLAIN/CRAM-MD5;
- SMTP: AUTH LOGIN/PLAIN/CRAM-MD5;

Ngoài máy chủ mail proxy của Nginx còn hỗ trợ SSL, STARTTLS và STLS.

# Ưu điểm và nhược điểm của Nginx
## Ưu điểm của Nginx
- Nginx cung cấp cơ chế bộ nhớ đệm tốt hơn so với các máy chủ khác, giúp tăng hiệu suất của ứng dụng khi người dùng truy cập cùng một địa chỉ trong một khoảng thời gian ngắn.
- Nginx là máy chủ web trọng lượng nhẹ chuyển tiếp các yêu cầu người dùng đến máy chủ ứng dụng.
- Quy tắc ghi lại của Nginx mang lại sự linh hoạt hơn để định cấu hình chuyển hướng vĩnh viễn hoặc chuyển hướng tạm thời cho một số URL.
- Nginx hoạt động tốt nhất khi được làm máy chủ proxy giao diện người dùng cho bất kỳ ứng dụng nào.
- Nginx có thể dễ dàng tùy chỉnh, dễ dàng phân phối qua HTTPS, có thư mục tùy chỉnh hoặc máy chủ ngược dòng proxy.
## Nhược điểm của Nginx
- Cân bằng tải là thứ mà Nginx cần cải thiện nhiều hơn so với các máy chủ khác.
- Giám sát của Nginx được đánh giá là tốt, nhưng chưa phải tốt nhất. Tức là Nginx phải cung cấp tính linh hoạt hơn trong việc định cấu hình nhiều tình huống hơn.
- Nginx cần cải thiện cơ chế lưu trữ, cung cấp các lệnh để có được đầu ra mong muốn từ các bản ghi.
- Rất khó để điều hướng giữa trang chủ Nginx và bộ phận hỗ trợ khách hàng.

# Sự khác biệt giữa Nginx và Apache
- Apache là máy chủ HTTP mã nguồn mở, trong khi Nginx là máy chủ web không đồng bộ hiệu suất cao và máy chủ proxy ngược.
- Hỗ trợ, sửa lỗi và phát triển ứng dụng của Apache được quản lý và duy trì bởi cộng đồng người dùng trên khắp thế giới. Việc hỗ trợ và bảo trì của Nginx được thực hiện bởi một doanh nghiệp chủ quản.
- Sự khác biệt giữa cách xử lý yêu cầu khách hàng. Apache cung cấp nhiều Mô-đun đa xử lý các yêu cầu của máy khách và lưu lượng truy cập web, nhưng Nginx được thiết kế để xử lý nhiều yêu cầu của máy khách đồng thời với tài nguyên phần cứng tối thiểu
- Với Apache, một luồng chỉ được liên kết với một kết nối, trong khi Nginx có thể xử lý nhiều kết nối.
- Apache có kiến trúc đa luồng nhưng thiếu khả năng mở rộng. Mặt khác, Nginx tuân theo phương pháp tiếp cận hướng sự kiện không đồng bộ để xử lý nhiều yêu cầu của khách hàng.
- Apache cung cấp nội dung tĩnh bằng các phương pháp thông thường và xử lý nội dung động trong máy chủ web. Nginx thiếu khả năng xử lý nội dung trong nội bộ, dựa vào quy trình bên ngoài để thực thi.
- Hạn chế của Nginx Không hỗ trợ .htaccess
# Bảng so sánh giữa Nginx và Apache
|         | Nginx | Apache |
|---------|--------|------|
| Máy chủ | Máy chủ web không đồng bộ hiệu suất cao và máy chủ proxy ngược | Máy chủ HTTP mã nguồn mở |
| Hỗ trợ | Có đội ngũ chuyên nghiệp thực hiện | Do cộng đồng hỗ trợ |
| Đa Luồng | Khả năng tiếp cận không đồng bộ xử lý đa luồng | Có kiến trúc đa luồng nhưng khó có khả năng mở rộng |
| Cung cấp nội dung tĩnh | Dựa vào quy trình bên ngoài để thực thi và xử lý nội dung nội bộ kém | Cung cấp nội dung bằng phương pháp thông thường và xử lý nội bộ dựa trên máy chủ wed |
| Khả năng xử lý cùng lúc | Cùng lúc nhiều kết nối | Chỉ một kết nối |
| Khả năng xử lý yêu cầu của Client | xử lý nhiều yêu cầu của máy khách đồng thời với tài nguyên phần cứng tối thiểu | Cung cấp nhiều mo-dun đa xử lý các yêu cầu của máy khách và lưu lượng truy cập wed |
