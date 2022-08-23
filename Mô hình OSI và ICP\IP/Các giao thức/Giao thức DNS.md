<img src="https://vietnix.vn/wp-content/uploads/2021/02/DNS-01.png">

# 1.Khái niệm
DNS viết tắt của Domain Name System có nghĩa là hệ thống phân giải tên miền. DNS là hệ thống cho phép thiết lập tương ứng giữa địa chỉ IP và tên miền trên Internet.
# 2.Cách thức hoạt động của DNS
- Quá trình phân giải DNS bao gồm chuyển đổi tên máy chủ (chẳng hạn như www.example.com) thành địa chỉ IP thân thiện với máy tính (chẳng hạn như 192.168.1.1). Một địa chỉ IP được cung cấp cho mỗi thiết bị trên Internet và địa chỉ đó là cần thiết để tìm thiết bị Internet phù hợp. Giống như một địa chỉ đường phố được sử dụng để tìm một ngôi nhà cụ thể.
- Khi người dùng muốn tải một trang web, một bản dịch phải xảy ra giữa những gì người dùng nhập vào trình duyệt web của họ (example.com) và địa chỉ thân thiện với máy cần thiết để định vị trang web example.com.
- Để hiểu quy trình đằng sau quá trình phân giải DNS, điều quan trọng là phải tìm hiểu về các thành phần khác nhau mà một truy vấn DNS phải vượt qua. Đối với trình duyệt web, việc tra cứu DNS diễn ra ở chế độ ẩn. Và không yêu cầu sự tương tác từ máy tính của người dùng ngoài yêu cầu ban đầu.
# 3.Các loại DNS bản ghi DNS thường sử dụng
- CNAME Record: Là một bản ghi tên quy chuẩn (Canonical Name Record). Đây là một dạng bản ghi tài nguyên trong hệ thống tên miền.
- A Record: Dùng để trỏ tên miền website tới một địa chỉ IP cụ thể. Đây được xem là bản ghi DNS đơn giản nhất.
- MX Record: Bản ghi này bạn có thể sử dụng để trỏ tên miền đến mail server. MX Record chỉ định server nào quản lý các dịch vụ Email của tên miền đó.
- AAAA Record: Dùng để trỏ tên miền đến địa chỉ IPv6 và cho phép thêm host mới, TTL và IPv6.
- TXT Record: Ngoài ra, có thể thêm giá trị TXT, Host mới, TTL và Point To để chứa các thông tin định dạng văn bản domain.
- SRV Record: Đây là bản ghi DNS đặc biệt, dùng để xác định chính xác dịch vụ nào đang chạy Port nào. Và thông qua bản ghi này bạn có thể thêm Priority, Port, Weight, TTL, Point to.
- NS Record: Bản ghi này có thể chỉ định Name Server cho từng tên miền phụ và bên cạnh đó có thể tạo tên Name Server, TTL hay host mới.
# 4.Các loại DNS Server
DNS Server gồm hai loại là Root Name Server và Local Name Server
## 4.1.Root Name Server
- Root Name Server là một dịch vụ phân giải tên miền gốc và trên thế giới có khoảng 12 DNS root Server.
- DNS root Server quản lý tất cả các tên miền Top-level. Khi có yêu cầu phân giải một Domain Name thành một địa chỉ IP, client sẽ gửi yêu cầu đến DNS gần nhất (DNS ISP). DNS ISP sẽ kết nối tới DNS root Server để hỏi địa chỉ của Domain Name.
- DNS root Server sẽ căn cứ và dựa vào các Top Level của tên miền và từ đó có những tài liệu hướng dẫn phù hợp để chuyển hướng cho khách hàng đến đúng địa chỉ cần truy vấn.
## 4.2.Local Name Server
- DNS Server này dùng để chứa thông tin để truy xuất và tìm kiếm máy chủ tên miền. Và thường được duy trì và phát triển bởi các doanh nghiệp hay các nhà cung cấp dịch vụ Internet.
# 5.Cách sử dụng DNS
Nếu bạn sử dụng DNS của nhà cung cấp mạng thì bạn sẽ không cần điền địa chỉ DNS. Nhưng neeys trường hợp bạn sử dụng DNS khác, thì bạn phải điền địa chỉ cụ thể của máy chủ đó để thay đổi DNS Server:
- Bước 1: Nhấn vào Start Menu > Gõ Control Panel > Chọn Control Panel.
- Bước 2: Truy cập vào View network status and task.
- Bước 3: Truy cập vào mạng Internet.
- Bước 4: Vào phần Properties để bắt đầu thay đổi DNS máy tính.
- Bước 5: Nhấp vào Internet Protocol Version 4 > Chọn Use the following DNS server addresses > Đổi DNS > OK.
# 6.Các loại truy vấn DNS
Trong một truy vấn DNS thông thường, ba loại truy vấn xảy ra. Bằng cách sử dụng kết hợp các truy vấn này. Một quy trình được tối ưu hóa cho quá trình phân giải DNS có thể giúp giảm khoảng cách di chuyển. Trong một tình huống lý tưởng, dữ liệu bản ghi được lưu trong bộ nhớ cache sẽ khả dụng, cho phép máy chủ định danh DNS trả về truy vấn không đệ quy.
## 3 loại truy vấn DNS
   - Recursive query: DNS client yêu cầu máy chủ DNS (thường là recursive DNS resolver). Sẽ trả lời máy khách bằng bản ghi tài nguyên được yêu cầu. Hoặc thông báo lỗi nếu resolver không thể tìm thấy bản ghi.
   - Iterative query: Trong tình huống này, DNS client sẽ cho phép máy chủ DNS trả về câu trả lời tốt nhất có thể. Nếu máy chủ DNS được truy vấn không có kết quả trùng khớp với tên truy vấn. Nó sẽ trả về một giới thiệu đến máy chủ DNS có thẩm quyền cho mức thấp hơn. DNS client sau đó sẽ thực hiện một truy vấn đến địa chỉ được giới thiệu. Quá trình này tiếp tục với các máy chủ DNS bổ sung trong chuỗi truy vấn cho đến khi xảy ra lỗi hoặc hết thời gian.
   - Non-recursive query: Thông thường điều này sẽ xảy ra khi DNS resolver client truy vấn máy chủ DNS một record mà server có quyền truy cập hoặc bản ghi tồn tại bên trong bộ đệm của server. Thông thường, một máy chủ DNS sẽ lưu các bản ghi DNS để ngăn chặn việc tiêu thụ thêm băng thông và giảm tải cho các máy chủ DNS khác.
