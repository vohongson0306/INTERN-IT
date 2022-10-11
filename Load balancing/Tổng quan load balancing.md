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
# 4.Các thuật toán Load Balancing
## Thuật toán Load Balancing – Round Robin
- `Round Robin` là thuật toán lựa chọn các máy chủ theo trình tự. Theo đó, Load Balancer sẽ bắt đầu đi từ máy chủ số 1 trong danh sách của nó ứng với yêu cầu đầu tiên. Tiếp đó, nó sẽ di chuyển dần xuống trong danh sách theo thứ tự và bắt đầu lại ở đầu trang khi đến máy chủ cuối cùng.
- Nhược điểm thuật toán Load Balancing – Round Robin 
  - Khi có 2 yêu cầu liên tục từ phía người dùng sẽ có thể được gửi vào 2 server khác nhau. Điều này làm tốn thời gian tạo thêm kết nối với server thứ 2 trong khi đó server thứ nhất cũng có thể trả lời được thông tin mà người dùng đang cần. Để giải quyết điều này, round robin thường được cài đặt cùng với các phương pháp duy trì session như sử dụng cookie.
## Thuật toán Load Balancing – Weighted Round Robin
- Tương tự như kỹ thuật Round Robin nhưng WRR còn có khả năng xử lý theo cấu hình của từng server đích. Mỗi máy chủ được đánh giá bằng một số nguyên (giá trị trọng số Weight – mặc định giá trị là 1). Một server có khả năng xử lý gấp đôi server khác sẽ được đánh số lớn hơn và nhận được số request gấp đôi từ bộ cân bằng tải.
- Nhược điểm thuật toán Load Balancing – Weighted Round Robin
- Weighted Round Robin gây mất cân bằng tải động nếu như tải của các request liên tục thay đổi trong một khoảng thời gian rộng.
## Thuật toán Load Balancing – Dynamic Round Robin (DRR)
- Thuật toán DRR hoạt động gần giống với thuật toán WRR. Điểm khác biệt là trọng số ở đây dựa trên sự kiểm tra server một cách liên tục. Do đó trọng số liên tục thay đổi.
- Việc chọn server sẽ dựa trên rất nhiều khía cạnh trong việc phân tích hiệu năng của server trên thời gia thực. Ví dụ: số kết nối hiện đang có trên các server hoặc server trả lời nhanh nhất, …
- Thuật toán này thường không được cài đặt trong các bộ cân bằng tài đơn giản. Nó thường được sử dụng trong các sản phẩm cân bằng tải của F5 Network.
## Thuật toán Load Balancing – Fastest 
- Đây là thuật toán dựa trên tính toán thời gian đáp ứng của mỗi server (response time). Thuật toán này sẽ chọn server nào có thời gian đáp ứng nhanh nhất. Thời gian đáp ứng được xác định bởi khoảng thời gian giữa thời điểm gửi một gói tin đến server và thời điểm nhận được gói tin trả lời.
- Việc gửi và nhận này sẽ được bộ cân bằng tải đảm nhiệm. Dựa trên thời gian đáp ứng, bộ cân bằng tải sẽ biết chuyển yêu cầu tiếp theo đến server nào.
- Thuật toán Fastest thường được dùng khi các server ở các vị trí địa lý khác nhau. Như vậy người dùng ở gần server nào thì thời gian đáp ứng của server đó sẽ nhanh nhất. Cuối cùng server đó sẽ được chọn để phục vụ.
## Thuật toán Load Balancing – Least Connections
- Các request sẽ được chuyển vào server có ít kết nối nhất trong hệ thống. Thuật toán này được coi như thuật toán động, vì nó phải đếm số kết nối đang hoạt động của server.
- Least Connections có khả năng hoạt động tốt. Ngay cả khi tải của các kết nối biến thiên trong một khoảng lớn. Do đó nếu sử dụng RC sẽ khắc phục được nhược điểm của Round Robin.

