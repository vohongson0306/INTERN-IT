# Giao diện chính
![image](https://user-images.githubusercontent.com/110179869/194837899-84a42fd6-4fe1-4e9f-82bd-be60885e17a8.png)

![image](https://user-images.githubusercontent.com/110179869/194975336-ad860811-cb4b-4e9f-aa3b-01c8af559171.png)

# Tab Monitoring
![image](https://user-images.githubusercontent.com/110179869/194975561-f3789634-8e3c-4511-ab93-018d9d9d10ea.png)

# Dashboard:
- Là giao diện hiển thị các dashboard trực quan để người quản trị nhìn trực tiếp, người quản trị có thể tạo ra rất nhiều các dashboard khác nhau, nhưng tại một tab screen chỉ có thể xem được 1 dashboard bất kỳ nào đó.
- Từ Dashboard có thể nhanh chống liên kết đến các thành phần như Graphs, Screens, Map bằng cách thêm các thành phần mong muốn vào mục Favourite graphs, Favourite Screen và Favourite map.

![image](https://user-images.githubusercontent.com/110179869/194975733-3a0870a1-f357-43dc-9303-8d334955f3be.png)

- Status of Zabbix: Bảng này hiển thị trạng thái của zabbix server, số lượng các host, trigger, item, số người đang đăng nhập và trạng thái của các thông số trên ở 2 cột value và Details.

![image](https://user-images.githubusercontent.com/110179869/194975868-c27407c6-e417-4a54-b10e-75324a4e3a7b.png)

- System status: Hiển thị mức độ cảnh báo của từ host trong từng group.

![image](https://user-images.githubusercontent.com/110179869/194975937-ddd25af0-80a0-4526-8f8e-60b3eee80c10.png)

- Host availability

![image](https://user-images.githubusercontent.com/110179869/194975993-851f1bee-3cb7-4071-8b7c-6bd51e185aef.png)

- Problems: Tất cả các vấn đề xảy ra với các host trong các group thống kê theo thời gian.

![image](https://user-images.githubusercontent.com/110179869/194976086-fb5b19e7-8eac-497e-b4d8-0327bda925c5.png)

# 1.2. Problems
![image](https://user-images.githubusercontent.com/110179869/194976239-3a972eac-ab0d-4080-8016-3c5ec53f573c.png)

# 1.3. Host
![image](https://user-images.githubusercontent.com/110179869/194976495-a830bfa7-3f4a-437e-8f4d-f37256c92b85.png)

# 1.4. Overview
![image](https://user-images.githubusercontent.com/110179869/194976979-bd21e0f2-9e34-4636-9a65-fe3fa35af6cb.png)

![image](https://user-images.githubusercontent.com/110179869/194977066-18a86536-fbda-4249-b4a9-fb17f66e7ad1.png)

# 1.5. Latest data
Dữ liệu mới nhất mà zabbix server thu thập được.

![image](https://user-images.githubusercontent.com/110179869/194977203-f4efb2cd-e591-4c15-82a0-cdbf007c69bc.png)

# 1.6. Screens
Là tập hợp các thông tin như Graphs, maps,data overview… vào chung một màn hình giám sát. Giúp người quản trị có thể lựa chọn các thông tin cần thiết hiển thị, giúp có cái nhìn tổng quát những thông tin mà người quản trọ mong muốn.

![image](https://user-images.githubusercontent.com/110179869/194977334-16315067-986e-4b3f-8124-b3a1c18ec28c.png)

![image](https://user-images.githubusercontent.com/110179869/194977391-2f2c34c1-6d0d-43d0-abec-e648c1c3778c.png)

![image](https://user-images.githubusercontent.com/110179869/194977465-cf0fed77-2062-4274-a241-5a3f4ec8ab8f.png)

# 1.7. Maps
Là thành phân cung cấp khả năng giám sát hệ thống dưới hình thức mô hình mạng. Giúp người quản trị có cái nhìn tổng quan về hệ thống sống mạng dưới dạng sơ đồ, trong trường hợp có sự cố sẽ giúp người quản trị đánh giá tầm ảnh hưởng của thiết bị gặp sự cố và đưa ra giải pháp phù hợp.

![image](https://user-images.githubusercontent.com/110179869/194977546-eb59c9d7-f01e-4dd8-a030-54dffd032dfe.png)

![image](https://user-images.githubusercontent.com/110179869/194977570-1ea61355-fc6c-4dd6-a1b2-d1a86984d310.png)

# 1.8. Discovery
Tính năng cho phép zabbix server tự động tìm kiếm các thiết bị được cài đặt zabbix agent đã cấu hình kết nối về zabbix server trong cùng mạng với zabbix server.

![image](https://user-images.githubusercontent.com/110179869/194977625-36ab0dc9-aa61-4c25-8e69-461549b40546.png)

# 1.9. Services
![image](https://user-images.githubusercontent.com/110179869/194977783-9cb504af-1b58-4dfa-9cc7-10d0e615da84.png)

# 2. Tab Configuration
![image](https://user-images.githubusercontent.com/110179869/194977844-6cbe304c-bb2d-418f-863e-bc4ae9230783.png)

# 2.1. Host group
Tập hợp lại các host có chung một mục đích sử dụng hoặc người quản trị tâp hợp lại để phục vụ một mục đích quản lý chung.

![image](https://user-images.githubusercontent.com/110179869/194978010-0bfd0a85-4c46-48ac-8e21-8a472bafc315.png)

# 2.2. Templates
- Đây là tập hợp các thực thể có thể áp dụng cho các Host, một Template sẽ chứa trong nó các tập lệnh để truy vấn lấy dữ liệu, hiển thị thông tin dữ liệu lấy được, thông tin tình trạng thiết bị, hiển thị và thông báo lỗi…
- Trong mỗi Template, các tệp lệnh được chia thành: items, triggers, graphs, applications, screens (có từ Zabbix 2.0),low-level discovery rules (có từ Zabbix 2.0), web scenarios (có từ Zabbix 2.2). Tùy theo giám sát thiết bị, dịch vụ, ứng dụng… nào thì các thành phần này được thiết lập khác nhau.
- Có thể import template tự viết vào.

![image](https://user-images.githubusercontent.com/110179869/194978099-66c6e690-c590-4e48-9cf9-5f882e3e9bdb.png)

# 2.3. Host
Là một máy tính, server, vps, chạy các hệ điều hành khác nhau hoặc một thực thể trong hệ thống mạng như là máy in, máy chấm công, máy photo, máy camera có hỗ trợ các giao thức mà monitor zabbix cung cấp.

![image](https://user-images.githubusercontent.com/110179869/194978172-bf63e17b-5f45-479f-9b57-6b4becb1689a.png)

# 2.4. Maintenance
- Có thể xác định thời gian bảo trì cho máy chủ và group trong Zabbix. Có hai loại Maintance - với thu thập dữ liệu và không thu thập dữ liệu.
- Ví dụ server của bạn off trong khoảng thời gian này để nâng cấp sửa chữa, thì maintance sẽ được lựa chọn cấu hình để không thu thập data trong khoảng thời gian đó.

![image](https://user-images.githubusercontent.com/110179869/194978219-86a3c514-b4d3-4ca3-9033-a13bde5e79e3.png)

# 2.5. Action
Nơi cấu hình, lựa chọn các kiểu thông báo khi có sự kiện xảy ra bởi cấu hình trigger. Người dùng phải tự định nghĩa các action theo mục đích.

![image](https://user-images.githubusercontent.com/110179869/194978293-aaa573b9-17d2-440a-aa6a-6f5609bf3ff3.png)

# 2.6. Event correlation
Cho phép cấu hình tương quan giữa các sự kiến với độ chính xác vào và tùy biến linh hoạt.

![image](https://user-images.githubusercontent.com/110179869/194978498-c1192c9a-5704-4f39-9299-dcf22fb93f30.png)

# 2.7. Discovery
Thiết lập range IP, nếu trong range có có thiết bị nào mà cài đặt các giao thức mà Zabbix server hỗ trợ thì sẽ tự động thu thập data về.

![image](https://user-images.githubusercontent.com/110179869/194978572-d5a98838-5476-47cd-b2f6-b9829044e73f.png)

![image](https://user-images.githubusercontent.com/110179869/194978777-d8090ecf-3c85-4b10-911b-0ec2270a9cf1.png)

# 3. Tab Administration
Chức năng của của tab Administrator là để cấu hình chung cho zabbix đối với user có quyền Admin.

![image](https://user-images.githubusercontent.com/110179869/194978813-27ec9782-4d7b-4d79-8b25-6f5ce864f241.png)

# 3.1. General
Mục này cho phép người quản trị cấu hình tùy chỉnh giao diện cho Zabbix Webinterface.

![image](https://user-images.githubusercontent.com/110179869/194978871-483262b8-a16a-4e77-87f0-d00d0ab3f0af.png)

Có thể tùy chỉnh rất nhiều giao diện như :

## GUI: Cung cấp một số tùy chỉnh mặc định liên quan đến giao diện người dùng.
![image](https://user-images.githubusercontent.com/110179869/194979090-e023d232-ac6a-4238-a547-4560d2fef454.png)

## HouseKeeping: quy định các thời gian định kì được thực hiện bởi Zabbix. Quá trình xóa thông tin hết hạn và thông tin được xóa bởi người dùng .Có thể tùy chỉnh các dữ liệu được lưu tối đa trong bao lâu trên Zabbix. Gồm các phần có thể cấu hình như Event and alerts, Services, Audit, User sessions, History, Trends.
![image](https://user-images.githubusercontent.com/110179869/194979121-8b30abe7-c71d-4d41-9681-0b857960c014.png)

## Images: Chứa tất cả các hình ảnh, icon, background được hiển thị trong Zabbix.
![image](https://user-images.githubusercontent.com/110179869/194979151-5b790483-1071-409e-9d30-42d7d573b49b.png)

## Icon mapping: Phần này cho phép tạo biểu tượng bản đồ của một host với các biểu tượng nhất định. Các thông tin trong các tùy chọn đều phục vụ cho việc tạo bản đồ.
![image](https://user-images.githubusercontent.com/110179869/194979176-5ba83d7c-4053-4a7c-baa1-b5811bd3b9f7.png)

## Regular expressions: Tạo và quy ước các biểu thức chính quy.
![image](https://user-images.githubusercontent.com/110179869/194979208-2fb0cdbb-caf6-4b0c-99e4-f985d792b531.png)

## Macros: Tạo các đoạn macro tương ứng với giá trị.
![image](https://user-images.githubusercontent.com/110179869/194979247-0d2cf7d6-274c-4214-ae2d-f5d0b17d7c7c.png)

## Value mapping: Tạo các giá trị tương ức với các mức.
![image](https://user-images.githubusercontent.com/110179869/194979269-8b1b85b2-8104-4396-b507-964600a4f5dc.png)

## Working time: Tham số toàn hệ thống xác định thời gian làm việc.
![image](https://user-images.githubusercontent.com/110179869/194979284-a45a0333-09bd-40c8-8701-9e50fb1247b4.png)

## Trigger severities: Cấu hình màu hiển thị đối với các mức của trigger.
![image](https://user-images.githubusercontent.com/110179869/194979303-1fab4e08-6f04-4345-9ffc-9f87b12f0dd3.png)

## Trigger displaying options: Mầu sắc, hiệu ứng iển thị khi có event.
![image](https://user-images.githubusercontent.com/110179869/194979330-00afcf68-16ac-448f-a2ee-129735c4c4b5.png)

## Other configuration parameters
![image](https://user-images.githubusercontent.com/110179869/194979380-d646f9b5-ef76-429e-be59-2706028bb074.png)

# 3.2. Proxies
Cho phép cấu hình các Proxy trên giao diện Zabbix.

![image](https://user-images.githubusercontent.com/110179869/194979488-25442d06-086b-4607-90f5-d5969c779d4f.png)

- Name: Tên của Proxy.
- Mode: Chế độc của Proxy (active hoặc passive).
- Encryption: Mã hóa kết nối từ Zabbix Server đến Proxy.
- Last seen (age): Thời gian tại thời điểm kết nối cuối cùng với Proxy.
- Host count: Số Host mà Proxy quản lý.
- Item count: Số lượng Item mà Proxy sử dụng.
- Required performance (vps): Hiệu suất Proxy.
- Host: Danh sách các host mà proxy quản lý.
# 3.3. Authentication
Phương pháp xác thực người dùng Zabbix : Thẩm định nội bộ, LDAP và HTTP

![image](https://user-images.githubusercontent.com/110179869/194979626-c242e8b3-058e-4976-9d26-8c3a5dc88218.png)

# 3.4. User groups
Quản lý các nhóm trong Zabbix

![image](https://user-images.githubusercontent.com/110179869/194979688-16f24643-69e1-401a-a5d2-9c3dd6507bc9.png)

# 3.5. Users
Tùy chỉnh các tài khoản user cho zabbix, có thể tạo thêm các user khác với việc phân quyền tương ứng.

![image](https://user-images.githubusercontent.com/110179869/194979729-40bbf366-87b4-4061-9d7a-e91c34ea6f0d.png)

# 3.6. Media types
Các kênh alert.

![image](https://user-images.githubusercontent.com/110179869/194979763-9de9e45c-26dc-4b92-8bce-e1b99ba40432.png)

# 3.7. Scripts
![image](https://user-images.githubusercontent.com/110179869/194979803-117068ff-afd1-440d-91cf-f9cf5f77d1cd.png)

# 3.8. Queue
Thông tin về hàng đợi trong quá trình cập nhật dữ liệu về từ các nguồn agent.

![image](https://user-images.githubusercontent.com/110179869/194979845-a0f89031-8bd6-4e3a-a558-ae93805cbf7c.png)






