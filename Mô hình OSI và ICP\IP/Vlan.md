<img src="https://wikihoidap.org/Upload/root/vlan-la-gi-1.jpg">

# 1.Khái niệm
VLAN là ᴠiết tắt của Virtual Local Area Netᴡork haу còn gọi là mạng LAN ảo. Một VLAN được định nghĩa là một nhóm logic các thiết bị mạng ᴠà được thiết lập dựa trên các уếu tố như chức năng, bộ phận, ứng dụng… của công tу. Về mặt kỹ thuật, VLAN là một miền quảng bá được tạo bởi các ѕᴡitch. Bình thường thì router đóng ᴠai trò tạo ra miền quảng bá. Đối ᴠới VLAN, ѕᴡitch có thể tạo ra miền quảng bá.

# 2.Cách hoạt động của VLAN
Vậy cách hoạt động của VLAN là gì? Dưới đây là chi tiết về cách thức hoạt động của mạng Virtual LAN:
- Các Virtual LAN ở trong mạng được xác định bằng một con số cụ thể
- Phạm vi giá trị hợp lệ là 1- 4094. Trên một switch VLAN, ta có thể chỉ định các cổng với số VLAN thích hợp.
- Tiếp đến, switch sẽ cho phép dữ liệu cần được gửi giữa các port khác nhau có cùng một Virtual LAN.
- Vì hầu hết các mạng đều có nhiều hơn là chỉ một switch duy nhất. Vì vậy, cần có một cách nào đó để có thể gửi lưu lượng giữa hai switch trong mạng. Cách đơn giản nhất chính là gán một port trên mỗi switch của Virtual LAN và chạy một cable giữa chúng.

# 3.Ưu điểm của VLAN
- Giải quyết các vấn đề điển hình liên quan đến broadcast
- Giảm kích thước của broadcast domain
- Cho phép tạo thêm một lớp bảo mật bổ sung
- Giúp việc quản lý thiết bị trở nên đơn giản, dễ dàng hơn
- Cho phép tạo một nhóm logic các thiết bị, phân loại theo chức năng
- Có thể tạo các nhóm thiết bị được kết nối logic, có thể hoạt động như trên mạng riêng của mình
- Cho phép phân đoạn mạng dựa trên nhóm, hay chức năng
- Có thể cấu trúc mạng theo vị trí địa lý
- Đem lại hiệu suất cao hơn, độ trễ (latency) thấp hơn
- Người dùng có thể bảo vệ những thông tin nhạy cảm của mình
- Xóa bỏ ranh giới vật lý
- Tăng cường bảo mật mạng
- Phân tách các máy chủ
- Không cần thêm phần cứng, cáp, giúp tiết kiệm đáng kể chi phí
- Việc thay đổi IP subnet của người dùng sẽ nằm trong phần mềm
- Giảm số lượng thiết bị cho cấu trúc liên kết mạng
- Đơn giản hóa việc quản lý các thiết bị vật lý
# 4.Nhược điểm của VLAN
- Packet có thể bị rò rỉ giữa các VLAN
- Packet được inject có thể dẫn đến cyber attack
- Các mối đe dọa ở trong một hệ thống đơn lẻ có thể phát tán virus cho toàn bộ mạng
- Cần có một router bổ sung để kiểm soát workload trong những mạng lớn
- Khả năng tương tác có thể gặp vấn đề
- Một VLAN không thể chuyển tiếp lưu lượng mạng sang những VLAN khác
# 5.Ứng dụng của VLAN
<img src="https://vietnix.vn/wp-content/uploads/2021/06/ung-dung-cua-vlan.webp">

- Đối với những mạng LAN có quy mô lớn, khoảng 200 thiết bị trở lên, thì việc sử dụng mạng Virtual LAN sẽ đem lại lợi ích to lớn
- Lý tưởng cho những mạng có lưu lượng truy cập cao
- Hữu ích cho những nhóm người dùng cần tính bảo mật cao, hoặc không thích mạng bị chậm do số lượng broadcast lớn
- Có thể được ứng dụng khi mạng có nhiều người dùng, nhưng lại không ở trên cùng một broadcast domain
- Có thể “biến hóa” một switch đơn nhất thành nhiều switch

# 6.Cách thiết lập VLAN
<img src="https://vietnix.vn/wp-content/uploads/2021/06/cach-thiet-lap-vlan.webp">

- 1.Chọn một số VLAN hợp lệ
- 2.Chọn dải địa chỉ IP riêng cho để các thiết bị trên VLAN sử dụng
- 3.Cấu hình thiết bị switch – động (dynamic) hoặc tĩnh (static). Đối với cấu hình tĩnh, admin mạng cần gán một số VLAN cho từng switch. Còn trong cấu hình động, admin cần gán một danh sách các địa chỉ MAC hoặc username đến số VLAN
- 4.Cấu hình định tuyến giữa các Virtual LAN khi cần. Việc cấu hình hai hay nhiều Virtual LAN giao tiếp với nhau yêu cầu sử dụng một router nhận biết VLAN, hoặc một switch Layer 3.





