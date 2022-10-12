# 1.Khái niệm
- CSF (ConfigServer & Firewall) là 1 gói ứng dụng hoạt động trên Linux như 1 Firewall được phát hành miễn phí để tăng tính bảo mật cho server (VPS và Dedicated). CSF hoạt động dựa trên iptables và tiến trình ldf để quyét các file log để phát hiện các dấu hiệu tấn công bất thường.
- CSF sẽ giúp server của bạn:
  - Chống DoS các loại
  - Chống Scan Port
  - Đưa ra các lời khuyên về việc cấu hình server (VD: Nên nâng cấp MySQL lên bản mới hơn)
  - Chống BruteForce Attack vào ftp server, web server, mail server,directadmin,cPanel…
  - Chống Syn Flood
  - Chống Ping Flood
  - Cho phép ngăn chặn truy cập từ 1 quốc gia nào đó bằng cách chỉ định Country Code chuẫn ISO
  - Hỗ trợ IPv6 và IPv4
  - CHo phép khóa IP tạm thời và vĩnh viễn ở tầng mạng (An toàn hơn ở tầng ứng dụng ) nên webserver ko phải mệt nhọc xử lý yêu cầu từ các IP bị cấm nữa
  - Cho phép bạn chuyến hướng yêu cầu từ các IP bị khóa sang 1 file html để thông báo cho người dùng biết IP của họ bị khóa







