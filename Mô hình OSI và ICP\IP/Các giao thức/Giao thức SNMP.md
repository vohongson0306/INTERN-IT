<img src="https://vietnix.vn/wp-content/uploads/2021/06/snmp-la-gi.webp">

# 1.khái niệm
SNMP (Simple Network Management Protocol) là một giao thức tầng ứng dụng được Hội đồng Kiến trúc Internet (IAB) xác định trong RFC1157 để trao đổi thông tin quản lý giữa các thiết bị mạng. Nó là một phần của Transmission Control Protocol/Internet Protocol (TCP/IP).

Giao thức SNMP là một trong những giao thức mạng được chấp nhận rộng rãi để quản lý và giám sát các phần tử mạng. Hầu hết các thiết bị mạng được cung cấp đi kèm với SNMP agent. Các agent này phải được kích hoạt và cấu hình để giao tiếp với các công cụ giám sát mạng hoặc hệ thống quản lý mạng (NMS).


# 2.Cách giao thức SNMP hoạt động
SNMP sử dụng một số command cơ bản để giao tiếp giữa manager và agent.
<img src="https://vietnix.vn/wp-content/uploads/2021/06/giao-thuc-snmp.webp">

## 2.1.GET: Yêu cầu thông tin bất cứ lúc nào
Để nhận thông tin trạng thái từ agent, manager có thể đưa ra message Get và GetNext để yêu cầu thông tin cho một biến cụ thể. Sau khi nhận được message Get hoặc GetNext, agent sẽ gửi message GetResponse cho manager. Nó sẽ chứa thông tin được yêu cầu hoặc lỗi giải thích tại sao không thể xử lý request.
## 2.2.SET: Điều khiển thiết bị từ xa 
Message SET cho phép manager yêu cầu thực hiện thay đổi đối với đối tượng được quản lý (tức là rơle điều khiển). Sau đó, agent sẽ trả lời bằng message Set-response nếu thay đổi đã được thực hiện hoặc lỗi giải thích tại sao không thể thực hiện thay đổi.
## 2.3.TRAP: SNMP message phổ biến nhất
Message TRAP được khởi xướng bởi agent và gửi đến manager khi một sự kiện quan trọng xảy ra. Trap dùng để cảnh báo cho manager – thay vì đợi request trạng thái từ manager khi cần thăm dò ý kiến ​​của agent.
## 2.4.INFORM: Một loại message có giá trị khác
Message INFORM rất giống với TRAP, nhưng chúng đáng tin cậy hơn. Các message INFORM được khởi tạo bởi agent và khi manager nhận được nó, nó sẽ gửi response đến agent cho biết message đã được nhận. Nếu agent không nhận được response từ manager thì agent sẽ gửi lại message INFORM.
## 2.5.SNMPWALK: Nhận tất cả dữ liệu
SNMPWALK sử dụng nhiều request Get-Next để truy xuất toàn bộ cây dữ liệu mạng từ một đối tượng được quản lý. Công cụ iReasoning MIB Browser sẽ rất hữu ích để xem tất cả các OID mà một agent cung cấp.
# 3.Cấu trúc của SNMP
<img src="https://vietnix.vn/wp-content/uploads/2021/06/snmp-port.webp">

Để gửi thông tin, SNMP sử dụng mô hình truyền thông phân lớp.
- Layer 1 – Lớp ứng dụng (SNMP)
- Layer 2 – Lớp vận chuyển (UDP)
- Layer 3 – Lớp Internet (IP)
- Layer 4 – Lớp Network interface
# 4.Lợi ích của SNMP
- Sử dụng SNMP cho phép bạn quản lý các asset mạng không có hệ điều hành, nhưng là các thành phần quan trọng của cơ sở hạ tầng. 
- Nó đơn giản hóa nhiệm vụ và giúp bạn có thể tập trung mạng. Nó còn cho phép kiểm soát hiệu quả hơn, ngay cả đối với thiết bị không có hệ điều hành như máy in.
- Một ưu điểm khác của SNMP là nó có một ngôn ngữ duy nhất cho phép người dùng tương tác với tất cả các thiết bị từ các nhà sản xuất khác nhau.
- Vì vậy, nó tương thích với hầu hết mọi asset và dịch vụ mạng, chẳng hạn như Windows, Linux, Mac và máy ảo Java.
- SNMP không chỉ hữu ích để cung cấp hỗ trợ chủ động mà còn để cải thiện trải nghiệm khách hàng, cho phép bạn dự đoán nhu cầu.
## Các lợi ích chính khác của SNMP:
- Ưu điểm chính của việc sử dụng SNMP là thiết kế đơn giản. Dễ dàng triển khai nó trên mạng, vì nó không yêu cầu cấu hình lâu.
- Hơn nữa, SNMP rất phổ biến ngày nay. Hầu hết tất cả các nhà sản xuất thiết bị phần cứng liên mạng lớn, như switch hoặc router, đều triển khai hỗ trợ SNMP trong các sản phẩm của họ.
- Mở rộng là một ưu thế khác của SNMP. Do thiết kế đơn giản, dễ dàng cập nhật giao thức để đáp ứng nhu cầu của user trong tương lai.
- SNMP dựa trên giao thức truyền tải UDP, yêu cầu ít tài nguyên hơn và kết nối đồng thời hơn với TCP

