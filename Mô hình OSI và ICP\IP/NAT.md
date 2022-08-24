<img src="https://wiki.matbao.net/wp-content/uploads/2019/11/nat-la-gi-1-nat-cho-phep-chuyen-doi-dia-chi-ip-cuc-bo-thanh-dia-chi-ip-ngoai-mien-1200x700.jpg">

# 1.Khái niệm
NAT (Network Address Translation) là một kỹ thuật cho phép chuyển đổi từ một địa chỉ IP này thành một địa chỉ IP khác. Thông thường NAT được sử dụng phổ biến trong mạng sử dụng địa chỉ cục bộ, cần truy cập đến mạng công cộng (Internet). Vị trí thực hiện NAT là Router biên kết nối giữa 2 mạng.

NAT cũng có thể được coi như là một firewall cơ bản. Để thực hiện được công việc đó, NAT duy trì một bảng thông tin về mỗi gói tin được gửi qua. Khi một PC trên mạng kết nối đến một Website trên Internet header của địa chỉ IP nguồn được thay đổi và thay thế bằng địa chỉ public mà đã được cấu hình sẵn trên NAT Server, sau khi có gói tin trở về NAT dựa vào bảng record mà nó đã lưu về các gói tin, thay đổi địa chỉ IP đích thành địa chỉ của PC trong mạng và chuyển tiếp đi. Thông qua cơ chế đó quản trị mạng có khả năng lọc các gói tin được gửi đến hay gửi từ một địa chỉ IP và cho phép hay cấm truy cập đến một port cụ thể

# 2.Ưu điểm và nhược điểm của NAT
- Về ưu điểm
  - Tiết kiệm địa chỉ IPv4: Lượng người dùng truy cập internet ngày càng tăng cao. Điều này dẫn đến nguy cơ thiếu hụt địa chỉ IPv4. Kỹ thuật NAT sẽ giúp giảm thiểu được số lượng địa chỉ IP cần sử dụng
  - Giúp che giấu IP bên trong mạng LAN
  - NAT có thể chia sẻ kết nối internet cho nhiều máy tính, thiết bị di động khác nhau trong mạng LAN chỉ với một địa chỉ IP public duy nhất
  - NAT giúp nhà quản trị mạng lọc được các gói tin đến và xét duyệt quyền truy cập của IP public đến 1 port bất kỳ

- Về nhược điểm
  -  Khi dùng kỹ thuật NAT, CPU sẽ phải kiểm tra và tốn thời gian để thay đổi địa chỉ IP. Điều này làm tăng độ trễ trong quá trình switching. Làm ảnh hưởng đến tốc độ đường truyền của mạng internet
  -  NAT có khả năng che giấu địa chỉ IP trong mạng LAN nên kỹ thuật viên sẽ gặp khó khăn khi cần kiểm tra nguồn gốc IP hoặc truy tìm dấu vết của gói tin
  -  NAT giấu địa chỉ IP nên sẽ khiến cho 1 vài ứng dụng cần sử dụng IP không thể hoạt động được

# 3. Phân loại NAT
- NAT tĩnh - Static NAT
  - NAT tĩnh hay còn gọi là Static NAT là phương thức NAT một đổi một. Nghĩa là một địa chỉ IP cố định trong LAN sẽ được ánh xạ ra một địa chỉ IP Public cố định trước khi gói tin đi ra Internet. Phương pháp này không nhằm tiết kiệm địa chỉ IP mà chỉ có mục đích ánh xạ một IP trong LAN ra một IP Public để ẩn IP nguồn trước khi đi ra Internet làm giảm nguy cơ bị tấn công trên mạng
  - Kỹ thuật này thường được sử dụng để chuyển đổi từ địa chỉ IP này sang địa chỉ khác một cách cố định, và thường là từ một địa chỉ private sang một địa chỉ public. Toàn bộ quá trình này được cài đặt thủ công, địa chỉ IP được ánh xạ tĩnh với nhau thông qua các lệnh cấu hình
- NAT động - Dynamic NAT
  - NAT được thực hiện 1 cách tự động. Trên Router, người quản trị cấu hình 1 danh sách các địa chỉ bên trong cần đi ra ngoài Internet và 1 danh sách các địa chỉ bên ngoài đại diện cho các địa chỉ bên trong. Tiếp theo, người quản trị cấu hình yêu cầu Router NAT danh sách bên trong thành danh sách bên ngoài. Bảng NAT của Router sẽ không có bất kỳ 1 dòng thông tin NAT nào được tạo sẵn mà các dòng thông tin NAT sẽ chỉ được tạo ra khi có gói tin đến Router ra Internet
  - Dynamic NAT phức tạp hơn so với Static, chúng phải lưu giữ các thông tin kết nối và thậm chí phải tìm thông tin của TCP trong packet. Do mức độ phức tạp cao hơn, nên Dynamic NAT chỉ dùng thay Static NAT với mục đích bảo mật. Những người bên ngoài không thể tìm ra IP kết nối với host chỉ định vì tại thời điểm tiếp theo host này có thể nhận một IP hoàn toàn khác
- NAT Overload - PAT
  - NAT Overload - PAT là giải pháp được dùng nhiều nhất đặc biệt là trong các Modem ADSL, đây là giải pháp mang lại cả hai ưu điểm của NAT đó là: ẩn địa chỉ IP trong hệ thống mạng nội bộ trước khi gói tin đi ra Integiằm giảm thiểu nguy cơ tấn công trên mạng tiết kiệm không gian địa chỉ IP. Bản chất PAT là kết hợp IP Public và số hiệu cổng (port) trước khi đi ra Internet. Lúc này mỗi IP trong LAN khi đi ra Internet sẽ được ánh xạ ra một IP Public kết hợp với số hiệu cổng
 # 3.Cơ chế hoạt động của NAT
 <img src="https://wikimaytinh.com/wp-content/uploads/nat-la-gi-nat-hoat-dong-nhu-the-nao-trong-mang-mp.jpg">

Cơ chế hoạt động của NAT giống như một Router, nó chuyển tiếp các gói tin giữa những lớp mạng khác nhau trên một mạng lớn. NAT dịch hay thay đổi một hoặc cả hai địa chỉ bên trong một gói tin khi gói tin đó đi qua một Router, hay một số thiết bị khác. Thông thường, NAT thường thay đổi địa chỉ Private của một kết nối mạng thành địa chỉ Public.

Trong giai đoạn gói tin được truyền từ mạng internet (public) quay trở lại NAT, NAT sẽ thực hiện nhiệm vụ thay đổi địa chỉ đích đến thành địa chỉ IP bên trong hệ thống mạng cục bộ và chuyển đi.

NAT có thể đóng vai trò như là bức tường lửa. Nó giúp người dùng bảo mật được thông tin IP máy tính. Cụ thể, nếu máy tính gặp sự cố khi đang kết nối internet thì địa chỉ IP public (đã cấu hình trước đó) sẽ được hiển thị thay thế cho IP mạng cục bộ.

