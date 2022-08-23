<img src ="https://wiki.matbao.net/wp-content/uploads/2019/08/tcp-ip-la-gi-co-su-khac-biet-nhat-dinh-trong-cau-truc-cua-osi-va-tcp-ip.jpg">

# I.Mô hình OSI
## 1.Khái niệm
Mô hình OSI (Open system interconnection – Mô hình kết nối các hệ thống mở) là một thiết kế dựa vào nguyên lý tầng cấp, lý giải một cách trừu tượng kỹ thuật kết nối truyền thông giữa các máy vi tính và thiết kế giao thức mạng giữa chúng. Mô hình này được phát triển thành một phần trong kế hoạch OSI (Open Systems Interconnection) do ISO và IUT-T khởi xướng. Nó còn được gọi là Mô hình bảy tầng của OSI.
## 2.Các giao thức trong mô hình OSI
Các giao thức trong mô hình OSI là yếu tố rất quan trọng, có 2 giao thức được sử dụng trong mô hình là giao thức hướng liên kết và giao thức không liên kết.
- Giao thức hướng liên kết (Connection Oriented)
  - Trước khi bắt đầu quá trình truyền dữ liệu, các thực thể trong cùng một tầng của 2 hệ thống khác nhau cần phải thiết lập một liên kết logic chung. Chúng tiến hành trao đổi, thương lượng với nhau về tập các tham số sẽ sử dụng trong quá trình truyền dữ liệu, có thể là cắt bớt hoặc hợp nhất dữ liệu, liên kết sẽ được hủy bỏ. Việc thiết lập liên kết logic này sễ giúp nâng cao độ tin cậy và an toàn.
- Giao thức không liên kết (Connectionless)
  - Với các giao thức không liên kết chỉ có giai đoạn duy nhất truyền dữ liệu và dữ liệu khi này được truyền độc lập trên cái tuyến khác nhau.
## 3.Các tầng trong mô hình OSI
Mô hình tham chiếu hệ thống mở OSI bao gồm 7 tầng:
<img src ="https://vietnix.vn/wp-content/uploads/2022/03/mo-hinh-osi-la-gi-1.webp">

### 3.1.Application Layer ( Tầng ứng dụng)
Là tầng duy nhất tương tác trực tiếp với tiến trình ứng dụng, có trách nhiệm cung cấp giao diện cũng như các thao tác dữ liệu giúp người dùng và phần mềm ứng dụng tương tác với nhau

Một số giao thức có trong tầng ứng dụng như: HTTP, FTP, POP, DHCP,…
### 3.2.Presentation Layer (Tầng trình bày)
Là tầng ngay dưới tầng ứng dụng, nó đáp ứng các nhu cầu của tầng ứng dụng như phiên dịch, mã hóa, giải mã, nén dữ liệu

Phiên dịch dữ liệu theo cú pháp mà ứng dụng có thể hiểu, mã hóa dữ liệu gửi đi cũng như giải mã dữ liệu nhận, nén dữ liệu trước khi truyền xuống tầng phiên
### 3.3.Session Layer (Tầng phiên)
Là tầng ngay dưới tầng trình bày, cung cấp các nhu cầu dịch vụ cho tầng trình diễn. Tầng phiên chịu trách nhiệm đóng và mở luồng giao tiếp giữa hai thiết bị, thời gian giữa mở và đóng được gọi là phiên. Nó đảm bảo phiên mở đủ lâu để dữ liệu có thể gửi đi và đóng đủ nhanh để tránh lãng phí tài nguyên

Ngoài ra, tầng phiên cung cấp dịch vụ đánh dấu điểm hoàn thành. Ví dụ khi bạn truyền một file dung lượng 10 GB, cứ sau mỗi 1GB lại đánh dấu điểm hoàn thành 1 lần thì khi bị mất kết nối hoặc tạm ngừng ở điểm 6GB rồi truyền lại thì chỉ cần truyền 4GB phần dữ liệu còn lại chưa được truyền
### 3.4.Transport Layer (Tầng vận chuyển)
Là tầng ngay dưới tầng phiên, nó đáp ứng các nhu cầu của tầng phiên. Tầng giao vận chịu trách nhiệm thiết lập kết nối giữa hai thiết bị, nó nhận dữ liệu từ tầng phiên rồi xử lý để gửi xuống tầng dưới cũng như nhận dữ liệu từ tầng dưới xử lý để chuyển lên tầng phiên

Tầng giao vận có thể cung cấp dịch vụ kiểm soát luồng và kiểm soát lỗi để đảm bảo dữ liệu được chuyển đi được chính xác và không quá tải bên nhận
### 3.5.Network Layer (Tầng mạng)
Đáp ứng các nhu cầu của tầng giao vận, chịu trách nhiệm giúp dữ liệu có thể truyền giữa các thiết bị ở các mạng khác nhau, nếu 2 thiết bị cùng trong một mạng thì ta không cần thiết phải có tầng này

Tầng mạng còn cung cấp các thuật toán dò đường cho các bộ định tuyến để xác định đường truyền vật lý tốt nhất cho dữ liệu
### 3.6.Data Link Layer (Tầng liên kết)
Đáp ứng các nhu cầu của tầng mạng, về cơ bản tầng này giống với tầng mạng nhưng nó hỗ trợ dữ liệu có thể được truyền đi giữa các thiết bị trong cùng một mạng
### 3.7.Physical Layer (Tầng vật lý)
Bao gồm các thiết bị phần cứng giúp truyền tải dữ liệu như cáp, bộ định tuyến,…. Ở tầng này dữ liệu được truyền tải dưới dạng bit 0 và 1

## 4.Ưu điểm và nhược điểm của mô hình OSI 
- Ưu điểm của mô hình OSI 
  -  Mỗi tầng có 1 cấu trúc và chức năng riêng nên dễ dàng xây dựng và sửa chữa

  -  Có thể tích hợp trong nhiều mạng lưới khác nhau

  -  Hỗ trợ kết nối có liên kết và kết nối phi liên kết

- Nhược điểm của mô hình OSI
  -  Tầng phiên và tầng trình diễn thường không được sử dụng nhiều so với các tầng khác vì chức năng hạn hẹp của nó

  -  Không hỗ trợ các giao thức, không định nghĩa bất kì giao thức nào

  -  Nhiều dịch vụ trùng lặp tại các tầng, ví dụ tầng mạng và tầng liên kết dữ liệu

  -  Các tầng không thể hoạt động song song, tầng dưới phải chờ dữ liệu từ tầng trên
# II.Mô hình TCP/IP
<img src="https://wiki.matbao.net/wp-content/uploads/2019/08/tcp-ip-la-gi-tcp-ip-hoat-dong-hieu-qua-tren-nhieu-he-thong-khac-nhau.png">

## 1.Khái niệm
TCP/IP là giao thức điều khiển truyền nhận/ giao thức liên mạng. Các máy tính có thể giao tiếp trên cùng một mạng như Internet thông qua một tập hợp các quy tắc của bộ giao thức trao đổi thông tin được tiêu chuẩn hóa. Bên cạnh đó, TCP/IP có khả năng phục hồi tự động.

Bạn có thể hiểu ngắn gọn, TCP/IP là tên viết tắt của cụm từ Transmission Control Protocol (TCP) và Internet Protocol (IP). Đây giao thức cài đặt truyền thông, chồng giao thức mà hầu hết các mạng máy tính ngày nay đều sử dụng để kết nối.
## 2.Ưu điểm của TCP/IP 
- Không chịu kiểm soát của tổ chức
  - Ưu điểm lớn nhất mà không thể phủ nhận đó là TCP/IP sẽ không chịu sự kiểm soát của bất kỳ tổ chức nào. Do đó, bạn có thể sử dụng tự do. 
- Tương thích với các hệ điều hành
  - Nói như vậy bởi TCP/IP có khả năng tương thích rất cao với tất cả phần cứng máy tính, mạng và các hệ điều hành. Vì vậy, mô hình này mang lại hoạt động hiệu quả với nhiều hệ thống khác nhau.
- Khả năng mở rộng cao
  - Với nhiều tính năng mở rộng cao, mô hình này có thể định tuyến và có thể xác định được đường dẫn hiệu quả nhất thông qua mạng. 
## 3.Các giao thức TCP/IP phổ biến
Hiện nay, TCP/IP có 3 giao thức luôn được dùng phổ biến đó là: HTTP, HTTPS, FTP.
- Giao thức HTTP
  - Các dữ liệu không an toàn giữa một web client và một web server sẽ được truyền nhờ giao thức HTTP.

  - Theo quy trình, web client (trình duyệt Internet trên máy tính) sẽ gửi một yêu cầu đến một web server để xem một website. Tiếp đó, khi server web nhận được yêu cầu và gửi thông tin website về cho web client.
- Giao thức HTTPS
  - Ngược lại với HTTP, giao thức HTTPS được dùng để truyền dữ liệu an toàn giữa một web client và một web server.
  - Giao thức HTTPS được sử dụng để gửi dữ liệu giao dịch của thẻ tín dụng hoặc dữ liệu cá nhân khác từ một web tới một web server.
- Giao thức FTP
  - Nhờ FTP, các máy tính có thể gửi và nhận dữ liệu đến nhau một các trực tiếp vì FTP là phương thức trao đổi file được sử dụng giữa hai hoặc nhiều máy tính thông qua Internet.
## 4.Các tầng trong mô hình TCP/IP
<img src="https://datech.vn/uploads/seo-traffic-gob/tcp-ip-la-gi-3.jpg">

### 4.1.Tầng 4: Application
Tầng Application hay còn gọi là tầng ứng dụng. Tầng ứng dụng đảm nhận vai trò giao tiếp dữ liệu giữa 2 máy khác nhau thông qua các dịch vụ mạng khác nhau (duyệt web, chay hay các giao thức trao đổi dữ liệu SMTP, SSH, FTP…). Dữ liệu khi đến được tầng 4 sẽ được định dạng để kết nối theo kiểu Byte nối Byte. Các thông tin định tuyến tại đây sẽ giúp xác định đường đi đúng của một gói tin

### 4.2.Tầng 3: Transport
Tầng dữ liệu hoạt động thông qua hai giao thức chính là TCP (Transmisson Control Protocol) và UDP (User Datagram Protocol).

TCP sẽ đảm bảo chất lượng truyền gửi gói tin, tuy nhiên lại mất thời gian khá lâu để thực hiện các thủ tục kiếm soát dữ liệu. Ngược lại, UDP lại cho tốc độ truyền tải nhanh nhưng lại không đảm bảo được chất lượng dữ liệu. Ở tầng này, TCP và UDP sẽ hỗ trợ nhau phân luồng dữ liệu.
### 4.3.Tầng 2: Internet
Tầng Internet đảm nhận việc truyền tải dữ liệu một cách hợp lý. Các giao thức của tầng này bao gồm IP (Internet Protocol), ICMP (Internet Control Message Protocol), IGMP (Internet Group Message Protocol).
### 4.4.Tầng 1: Physical
Tầng vật lý (còn được gọi là tầng liên kết dữ liệu) là tầng thấp nhất trong mô hình TCP/IP. Tầng này chịu trách nhiệm truyền dữ liệu giữa hai thiết bị trong cùng một mạng. Tại đây, các gói dữ liệu được đóng vào khung (gọi là Frame) và được định tuyến đi đến đích đã được chỉ định ban đầu.
# So sánh giữa 2 mô hình
– Giống nhau: Mô hình OSI và TCP/IP có một số điểm chung như sau:
  - OSI và TCP/IP đều có kiến trúc phân lớp.
  - OSI và TCP/IP đều có lớp Network và lớp Transport.
  - OSI và TCP/IP cùng sử dụng kỹ thuật chuyển Packet.

- Khác nhau

|  | Mô hình OSI | Mô hình TCP/IP| 
|--------------|-------|------|
| Độ tin cậy phổ biến | Nhiều người cho rằng đây là mô hình cũ, chỉ để tham khảo, số người sử dụng hạn chế hơn so với TCP/IP | Được chuẩn hóa, nhiều người tin cậy và sử dụng phổ biến trên toàn cầu |
| Phương pháp tiếp cận | Tiếp cận theo chiều dọc | Tiếp cận theo chiều ngang | 
|Sự kết hợp giữa các tầng|Mỗi tầng khác nhau sẽ thực hiện một nhiệm vụ khác nhau, không có sự kết hợp giữa bất cứ tầng nào|Trong tầng ứng dụng có tầng trình diễn và tầng phiên được kết hợp với nhau|
|Thiết kế |Phát triển mô hình trước sau đó sẽ phát triển giao thức|	Các giao thức được thiết kế trước sau đó phát triển mô hình|
|Số lớp (tầng)|7|4|
|Truyền thông|Hỗ trợ cả kết nối định tuyến và không dây|Hỗ trợ truyền thông không kết nối từ tầng mạng|
|Tính phục thuộc|Giao thức độc lập|Phụ thuộc vào giao thức|
