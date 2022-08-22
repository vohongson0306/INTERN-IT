# 1. SSL là gì?
- SSL là viết tắt của từ Secure Sockets Layer. Đây là một tiêu chuẩn an ninh công nghệ toàn cầu tạo ra một liên kết giữa máy chủ web và trình duyệt. Liên kết này đảm bảo tất cả dữ liệu trao đổi giữa máy chủ web và trình duyệt luôn được bảo mật và an toàn.
- SSL đảm bảo rằng tất cả các dữ liệu được truyền giữa các máy chủ web và các trình duyệt được mang tính riêng tư, tách rời. SSL là một chuẩn công nghệ được sử dụng bởi hàng triệu trang web trong việc bảo vệ các giao dịch trực tuyến với khách hàng của họ.
- a. SSL làm việc như thế nào?
- b. Những gì xảy ra khi một máy tính kết nối với một Website đã được chứng thực ?
- c. Trình duyệt làm thế nào để kiểm tra một SSL là có thực hay không ?
  - Khi Website gửi cho trình duyệt một chứng chỉ SSL, trình duyệt sẽ gửi chứng chỉ này đến một máy chủ lưu trữ các chứng chỉ số đã được phê duyệt.
  - Về mặt kỹ thuật, SSL sử dụng mã hóa công khai. Kỹ thuật này giúp cho Website và trình duyệt tự thỏa thuận (bước 4 ở hình trên) một bộ khóa sẽ dùng trong suốt quá trình trao đổi thông tin sau đó. Bộ khóa sẽ thay đổi theo mỗi trong lần giao dịch kế tiếp, một người khác sẽ không thể giải mã ngay cả khi có được dữ liệu của máy chủ lưu trữ chứng chỉ số nói trên.

# 2. Tại sao nên sử dụng SSL?
- Bạn đăng ký domain để sử dụng các dịch vụ website, email v.v... -> luôn có những lỗ hổng bảo mật -> hacker tấn công -> SSL bảo vệ website và khách hàng của bạn.
- Bảo mật dữ liệu: dữ liệu được mã hóa và chỉ người nhận đích thực mới có thể giải mã.
- Toàn vẹn dữ liệu: dữ liệu không bị thay đổi bởi tin tặc.
- Chống chối bỏ: đối tượng thực hiện gửi dữ liệu không thể phủ nhận dữ liệu của mình.
# 3. Lợi ích khi sử dụng SSL?
- Bạn đăng ký domain để sử dụng các dịch vụ website, email v.v… -> luôn có những lỗ hổng bảo mật -> hacker tấn công -> SSL bảo vệ website và khách hàng của bạn.
- Bảo mật và mã hóa các thông điệp trao đổi giữa trình duyệt và server.
- Bảo mật các giao dịch giữa khách hàng và doanh nghiệp, các dịch vụ truy nhập hệ thống.
- Bảo mật webmail và các ứng dụng như Outlook Web Acess, Exchange, và Office Communication Server.
- Bảo mật các ứng dụng ảo hóa như Citrix Delivery Platform hoặc các ứng dụng điện toán mây.
- Bảo mật dịch vụ FTP.
- Bảo mật truy cập Control panel
- Bảo mật các dịch vụ truyền dữ liệu trong mạng nội bộ, file sharing, extranet.
- Bảo mật VPN Access Servers, Citrix Access Gateway.
- Nâng cao hình ảnh, thương hiệu và uy tín doanh nghiệp
- Nâng cao thứ hạng website trên kết quả tìm kiếm Google (SEO)
- Tạo lợi thế cạnh tranh, tăng niềm tin của khách hàng đối với website, tăng số lượng giao dịch, giá trị giao dịch trực tuyến của khách hàng. Website không được xác thực và bảo mật sẽ luôn ẩn chứa nguy cơ bị xâm nhập dữ liệu, dẫn đến hậu quả khách hàng không tin tưởng sử dụng dịch vụ.
# 4. DV-SSL
Domain Validation (DV): chứng thư số SSL chứng thực cho Domain Name - Website . Khi 1 Website sử dụng DV SSL thì sẽ được xác thực tên domain , website đã được mã hoá an toàn khi trao đổi dữ liệu
# 5. OV-SSL
Organization Validation (OV): chứng thư số SSL chứng thực cho Website và xác thực doanh nghiệp đang sở hữu website đó
# 6. EV-SSL
- Extended Validation (EV): cho khách hàng của bạn thấy Website đang sử dụng chứng thư SSL có độ bảo mật cao nhất và được rà soát pháp lý kỹ càng.
- Với thanh đại chỉ sang màu xanh với hiển thị đầy đủ thông tin của công ty, cung cấp một cấp độ cao hơn tin tưởng vào website của bạn.
# 7. Wildcard SSL
(Wildcard SSL Certificate): sản phẩm lý tưởng dành cho các cổng thương mại điện tử. Các website dạng này thường có thể tạo ra các trang e-store dành cho các chủ cửa hàng trực tuyến, mỗi e-store là một sub domains và được chia sẻ trên một địa chỉ IP duy nhất. Khi đó, để triển khai giải pháp bảo bảo mật giao dịch trực tuyến (khi đặt hàng, thanh toán, đăng ký & đăng nhập tài khoản,...) bằng SSL, chúng ta có thể dùng duy nhất một chứng chỉ số Wildcard cho tên miền chính của website và dùng chung một địa chỉ IP duy nhất để chia sẻ cho tất cả mọi sub domains.
