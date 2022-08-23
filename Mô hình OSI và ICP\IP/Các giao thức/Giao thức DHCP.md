<img src="https://vsudo.net/blog/wp-content/uploads/2020/02/dhcp-la-gi-696x460.jpg">

# 1.Khái niệm
DHCP (Dynamic Host Configuration Protocol) là giao thức được sử dụng để cấu hình địa chỉ IP cho thiết bị máy tính. Mỗi thiết bị của người dùng đều cần phải có ít nhất 1 địa chỉ IP để tham gia vào mạng – để kết nối tới các dịch vụ khác. Khi máy tính lần đầu tiên kết nối tới mạng nội bộ bằng dây cáp hoặc truy cập Wifi, điều đầu tiên nó làm chính là tìm địa chỉ IP, netmask, default gateway và DNS servers.
- DHCP server có thể có 3 phương thức cấp phát địa chỉ IP như sau:
  - **Cấp phát tĩnh:** DHCP server cấp phát một địa chỉ IP dựa trên một bảng với cặp địa chỉ MAC/ địa chỉ IP tương ứng, được điền thủ công và chỉ khi có yêu cầu từ client với địa chỉ MAC được liệt kê bên trong bảng mới được cấp IP.
  - **Cấp phát động:** người quản trị mạng sẽ gán một dãy (range) địa chỉ IP tới DHCP, và mỗi máy tính client trong mạng LAN được cấu hình để request một địa chỉ IP từ DHCP server trong quá trình khởi tạo mạng.
  - **Cấp phát tự động:** DHCP server gán vĩnh viễn địa chỉ IP tới request client từ dãy địa chỉ IP được quy định bởi người quản trị. Tương tự như cấp phát động, nhưng DHCP server giữ lại bảng chứa các địa chỉ IP được gán trước đó, để nó có thể gán cho client cùng địa chỉ IP mà họ đã request trước đó.

Trong số 3 phương thức trên, phương thức cấp phát động và cấp phát tĩnh là phương thức cấp phát IP phổ biến nhất hiện nay.
# 2.Cách DHCP hoạt động
DHCP cung cấp một cách tự động để phân phối, cập nhật địa chỉ IP và một số thông tin cấu hình khác trên mạng. Một DHCP server cung cấp thông tin này tới DHCP client thông qua việc trao đổi hàng loạt các thông điệp với nhau, bao gồm 4 bước.
<img src="https://vsudo.net/blog/wp-content/uploads/2020/02/how-does-dhcp-work-800x365.jpg">

## 2.1.Bước 1: DHCP Discovery
Máy tính client sẽ gửi thông điệp broadcast trên physical subnet để tìm server DHCP khả dụng. Máy tính client tạo ra một gói tin UDP (User Datagram Protocol) với đích đến mặc định 255.255.255.255 hoặc địa chỉ broadcast subnet cụ thể nếu được cấu hình.
## 2.2.Bước 2: DHCP Offer
Khi DHCP server nhận được truy vấn cần cấp phát IP từ một client, nó sẽ bảo lưu địa chỉ IP cho client và mở rộng địa chỉ IP sẽ cấp phát bằng cách gửi cho client message DHCPOFFER. Thông điệp này chứa địa chỉ MAC của client, địa chỉ IP mà server sẽ cung cấp, subnet mask, thời gian được cấp phát và địa chỉ IP của DHCP server cung cấp.
## 2.3.Bước 3: DHCP Request
Trong hầu hết các công ty hiện nay, thường hay sử dụng hai DHCP servers để giúp hệ thống cung cấp khả năng chịu lỗi cao nếu như có một server bị lỗi hoặc được bảo trì. Vậy nên client có thể nhận được DHCP offer từ nhiều server khác nhau, nhưng nó sẽ chỉ chấp nhận duy nhất một DHCP offer mà thôi. Client trả lời DHCP request, nó sẽ gửi tin unicast tới server mà thông tin địa chỉ nằm trong DHCP offser mà nó nhận được. Dựa trên trường **Transaction ID** trong request, khi đó servers sẽ nhận được thông báo những offer mà client chấp nhận. Khi các DHCP server khác nhận thông điệp này, chúng sẽ loạt bỏ bất kỳ offer nào nó đã gửi tới client và lấy lại các địa chỉ IP offer này đưa vào danh sách các địa chỉ IP có sẵn.
## 2.4.Bước 4: DHCP Acknowledgement
Khi DHCP server nhận được thông điệp DHCPREQUEST từ client, quá trình cấu bước vào giai đoạn cuôí cùng.
<img src="https://vsudo.net/blog/wp-content/uploads/2020/02/giao-thuc-dhcp.jpg">

Giai đoạn chấp nhận liên quan đến việc gửi một gói DHCPACK tới client. Gói tin này bao gồm thời gian được sử dụng và thông tin cấu hình khác mà client có thể đã truy vấn. Tại điểm này, quá trình cấu hình IP đã được hoàn thành.

# 3.Ưu điểm khi sử dụng DHCP
- Tập trung quản trị thông tin cấu hình host
- Cấu hình động các máy
- Cấu hình IP cho các máy một cách liền mạch.
- Sự linh hoạt
- Đơn giản hóa vài trò quản trị của việc cauas hình địa chỉ IP của client.
- Sự linh hoạt
