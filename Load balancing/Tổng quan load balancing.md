<img src="https://techvccloud.mediacdn.vn/280518386289090560/2021/11/16/load-balancer-la-gi-16370559099231247679408.jpg">

# 1. Load balancer là gì?
- Load balancing (Cân bằng tải) là việc phân phối hiệu quả lưu lượng truy cập đến trên một nhóm backend servers, hay còn được gọi là server farm hoặc server pool.
- Các website hiện đại có lưu lượng truy cập cao phải phục vụ hàng trăm nghìn, thậm chí hàng triệu các requests đồng thời từ người dùng hoặc khách hàng, đồng thời phải phản hồi chính xác lại các văn bản, hình ảnh, video hoặc dữ liệu ứng dụng, tất cả đều được thực hiện rất nhanh chóng và đáng tin cậy. Để đáp ứng hiệu quả khối lượng lớn các yêu cầu và phản hồi một cách tiết kiệm nhất, best practice tốt nhất thường sẽ là sử dụng thêm servers.
- Một load balancer (Cân bằng tải) hoạt động như "traffic cop" (cảnh sát giao thông) ở phía trước server và routing các request của client trên tất cả các servers có khả năng thực hiện các request đó, sao cho tối ưu về tốc độ và hiệu suất nhất và đảm bảo rằng không có server nào phải hoạt động quá mức. Nếu một server đơn lẻ bị hỏng, cân bằng tải (load balancer) sẽ chuyển hướng lưu lượng truy cập đến các server trực tuyến còn lại. Khi một server mới được thêm vào nhóm máy chủ, bộ cân bằng tải sẽ tự động bắt đầu gửi yêu cầu đến máy chủ mới thêm này.
- Tóm lại, một load balancer sẽ thực hiện các chức năng chính sau đây:
  - Phân phối các client requests hoặc network load một cách hiệu quả trên nhiều servers.
  - Đảm bảo tính khả dụng và độ tin cậy cao bằng cách chỉ gửi các yêu cầu đến các máy chủ trực tuyến.
# 2.Lợi ích khi có Load Balancing
## Uptime
- Với Load Balancing, khi máy chủ gặp sự cố, lưu lượng truy cập sẽ được tự động chuyển đến máy chủ còn lại. Nhờ đó, trong hầu hết mọi trường hợp, sự cố bất ngờ có thể được phát hiện và xử lý kịp thời, không làm gián đoạn các truy cập của người dùng.
## Datacenter linh hoạt
- Khả năng linh hoạt trong việc điều phối giữa các máy chủ cũng là một ưu điểm khác của Load Balancing. Tự động điều phối giữa các máy chủ cũ và mới để xử lý các yêu cầu dịch vụ mà không làm gián đoạn các hoạt động chung của hệ thống.
## Bảo mật cho Datacenter
- Bằng cách sử dụng Load Balancing, những yêu cầu từ người dùng sẽ được tiếp nhận và xử lý trước khi phân chia đến các máy chủ. Đồng thời, quá trình phản hồi cũng được thông qua Load Balancing, ngăn cản việc người dùng giao tiếp trực tiếp với máy chủ, ẩn đi thông tin và cấu trúc mạng nội bộ, từ đó chặn đứng những cuộc tấn công mạng hay truy cập trái phép…
# 3.Các giao thức mà Load Balancing có thể xử lý
## Có 4 loại giao thức chính mà quản trị Load Balancer có thể tạo quy định chuyển tiếp:
- HTTP: dựa trên cơ chế HTTP chuẩn, HTTP Balancing đưa ra yêu cầu tác vụ. Load Balancer đặt X-Forwarded-For, X-Forwarded-Proto và tiêu đề X-Forwarded-Port cung cấp các thông tin backends về những yêu cầu ban đầu.
- HTTPS: các chức năng tương tự HTTP Balancing. HTTPS Balancing được bổ sung mã hóa và nó được xử lý bằng 2 cách: passthrough SSL duy trì mã hóa tất cả con đường đến backend hoặc: chấm dứt SSL, đặt gánh nặng giải mã vào load balancer và gửi lưu lượng được mã hóa đến backend.
- TCP: trong một số trường hợp khi ứng dụng không sử dụng giao thức HTTP hoặc HTTPS, TCP sẽ là một giải pháp để cân bằng lưu lượng. Cụ thể, khi có một lượng truy cập vào một cụm cơ sở dữ liệu, TCP sẽ giúp lan truyền lưu lượng trên tất cả các máy chủ
- UDP: trong thời gian gần đây, Load Balancer đã bổ sung thêm hỗ trợ cho cân bằng tải giao thức internet lõi như DNS và syslogd sử dụng UDP.





