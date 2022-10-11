>> Cấu hình FirewallD
# 1.Thiết lập các Zone
– Liệt kê tất cả các zone trong hệ thống
```
firewall-cmd --get-zones
```
– Kiểm tra zone mặc định
```
firewall-cmd --get-default-zone
```
– Kiểm tra zone active (được sử dụng bởi giao diện mạng)
Vì FirewallD chưa được thiết lập bất kỳ quy tắc nào nên zone mặc định cũng đồng thời là zone duy nhất được kích hoạt, điều khiển mọi luồng dữ liệu.
```
firewall-cmd --get-active-zones
```
– Thay đổi zone mặc định, ví dụ thành home:
```
firewall-cmd --set-default-zone=home
```
# 2.Các lệnh liệt kê
- Liệt kê toàn bộ các quy tắc của các zones:
```
firewall-cmd --list-all-zones
```
- Liệt kê toàn bộ các quy tắc trong zone mặc định và zone active
```
firewall-cmd --list-all
```
- Liệt kê toàn bộ các quy tắc trong một zone cụ thể, ví dụ home
```
firewall-cmd --zone=home --list-all
```
- Liệt kê danh sách services/port được cho phép trong zone cụ thể:
```
firewall-cmd --zone=public --list-services
firewall-cmd --zone=public --list-ports
```
# 3.Thiết lập cho Service
- Đây chính là điểm khác biệt của FirewallD so với Iptables – quản lý thông qua các services. Việc thiết lập tường lửa đã trở nên dễ dàng hơn bao giờ hết – chỉ việc thêm các services vào zone đang sử dụng.
- Đầu tiên, xác định các services trên hệ thống:
```
firewall-cmd --get-services
```
- Lưu ý: Biết thêm thông tin về service qua thông tin lưu tại `/usr/lib/firewalld/services/`.

- Hệ thống thông thường cần cho phép các services sau: `ssh(22/TCP)`, `http(80/TCP)`, `https(443/TCP)`, `smtp(25/TCP)`, `smtps(465/TCP)` và `smtp-submission(587/TCP)`

– Thiết lập cho phép services trên FirewallD, sử dụng –add-service:
```
firewall-cmd --zone=public --add-service=http
success
firewall-cmd --zone=public --add-service=http --permanent
success
```
- Ngay lập tức, zone “public” cho phép kết nối HTTP trên cổng 80. Kiểm tra lại
```
firewall-cmd --zone=public --list-services
ssh dhcpv6-client http
```
– Vô hiệu hóa services trên FirewallD, sử dụng –remove-service:
```
firewall-cmd --zone=public --remove-service=http
firewall-cmd --zone=public --remove-service=http --permanent
```
# 4 Thiết lập cho Port
Trong trường hợp bạn thích quản lý theo cách truyền thống qua Port, FirewallD cũng hỗ trợ bạn điều đó.

– Mở Port với tham số –add-port:
```
# firewall-cmd --zone=public --add-port=9999/tcp
# firewall-cmd --zone=public --add-port=9999/tcp --permanent
```
– Mở 1 dải port:
```
# firewall-cmd --zone=public --add-port=4990-5000/tcp
# firewall-cmd --zone=public --add-port=4990-5000/tcp --permanent
```
- Kiểm tra lại
```
# firewall-cmd --zone=public --list-ports
9999/tcp 4990-5000/tcp
```
– Đóng Port với tham số –remove-port:
```
# firewall-cmd --zone=public --remove-port=9999/tcp
# firewall-cmd --zone=public --remove-port=9999/tcp --permanent
```
