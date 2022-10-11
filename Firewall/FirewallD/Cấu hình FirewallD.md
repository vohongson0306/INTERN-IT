>> Cấu hình FirewallD
# 1.Thiết lập các Zone
– Liệt kê tất cả các zone trong hệ thống
```
firewall-cmd --get-zones
```
![image](https://user-images.githubusercontent.com/110179869/195026251-d4446c08-72dc-4a2a-a3e7-839062417f46.png)

– Kiểm tra zone mặc định
```
firewall-cmd --get-default-zone
```
![image](https://user-images.githubusercontent.com/110179869/195026330-f7e9b30a-dc83-4bb7-968e-d1fe012268da.png)

– Kiểm tra zone active (được sử dụng bởi giao diện mạng)
Vì FirewallD chưa được thiết lập bất kỳ quy tắc nào nên zone mặc định cũng đồng thời là zone duy nhất được kích hoạt, điều khiển mọi luồng dữ liệu.
```
firewall-cmd --get-active-zones
```
![image](https://user-images.githubusercontent.com/110179869/195026487-b7986957-b8fe-4c16-8aca-9dfe6cfb5bc1.png)

– Thay đổi zone mặc định, ví dụ thành home:
```
firewall-cmd --set-default-zone=home
```
![image](https://user-images.githubusercontent.com/110179869/195026751-b241dc1c-673c-40dd-9172-079f2e6a1877.png)

# 2.Các lệnh liệt kê
- Liệt kê toàn bộ các quy tắc của các zones:
```
firewall-cmd --list-all-zones
```
- Liệt kê toàn bộ các quy tắc trong zone mặc định và zone active
```
firewall-cmd --list-all
```
![image](https://user-images.githubusercontent.com/110179869/195027055-e10e3dba-49aa-49f5-affc-4a05225f570e.png)

- Liệt kê toàn bộ các quy tắc trong một zone cụ thể, ví dụ home
```
firewall-cmd --zone=home --list-all
```
![image](https://user-images.githubusercontent.com/110179869/195027236-c661195b-1780-4a52-ba4b-f6c2cb86629a.png)

- Liệt kê danh sách services/port được cho phép trong zone cụ thể:
```
firewall-cmd --zone=public --list-services
firewall-cmd --zone=public --list-ports
```
![image](https://user-images.githubusercontent.com/110179869/195027541-f73335ee-4f41-4775-b4b4-211920b082d0.png)

# 3.Thiết lập cho Service
- Đây chính là điểm khác biệt của FirewallD so với Iptables – quản lý thông qua các services. Việc thiết lập tường lửa đã trở nên dễ dàng hơn bao giờ hết – chỉ việc thêm các services vào zone đang sử dụng.
- Đầu tiên, xác định các services trên hệ thống:
```
firewall-cmd --get-services
```
![image](https://user-images.githubusercontent.com/110179869/195028002-f7879a11-2bf4-45a9-8a95-577a6f4c3ff5.png)

- Lưu ý: Biết thêm thông tin về service qua thông tin lưu tại `/usr/lib/firewalld/services/`.

- Hệ thống thông thường cần cho phép các services sau: `ssh(22/TCP)`, `http(80/TCP)`, `https(443/TCP)`, `smtp(25/TCP)`, `smtps(465/TCP)` và `smtp-submission(587/TCP)`

– Thiết lập cho phép services trên FirewallD, sử dụng –add-service:
```
firewall-cmd --zone=public --add-service=http
success
firewall-cmd --zone=public --add-service=http --permanent
success
```
![image](https://user-images.githubusercontent.com/110179869/195028172-7d3f32ff-3c49-4e28-acbe-3073ef2c61e8.png)

- Ngay lập tức, zone “public” cho phép kết nối HTTP trên cổng 80. Kiểm tra lại
```
firewall-cmd --zone=public --list-services
```
![image](https://user-images.githubusercontent.com/110179869/195028441-90111b87-adfa-4eb7-8fe2-8e2006b47076.png)

– Vô hiệu hóa services trên FirewallD, sử dụng –remove-service:
```
firewall-cmd --zone=public --remove-service=http
firewall-cmd --zone=public --remove-service=http --permanent
```
![image](https://user-images.githubusercontent.com/110179869/195028608-a57901e6-eb30-43b1-adfb-3bcc7f157224.png)

# 4 Thiết lập cho Port
Trong trường hợp bạn thích quản lý theo cách truyền thống qua Port, FirewallD cũng hỗ trợ bạn điều đó.

– Mở Port với tham số –add-port:
```
firewall-cmd --zone=public --add-port=9999/tcp
firewall-cmd --zone=public --add-port=9999/tcp --permanent
```
![image](https://user-images.githubusercontent.com/110179869/195028745-20d1b9e1-aa4d-4215-a262-0016f9f50ddd.png)

– Mở 1 dải port:
```
firewall-cmd --zone=public --add-port=4990-5000/tcp
firewall-cmd --zone=public --add-port=4990-5000/tcp --permanent
```
![image](https://user-images.githubusercontent.com/110179869/195028895-7d1cf29d-111c-44c4-ae45-ee432079887c.png)

- Kiểm tra lại
```
firewall-cmd --zone=public --list-ports
```
![image](https://user-images.githubusercontent.com/110179869/195029144-3458e821-2b1b-4e70-9ea6-f043b220ee82.png)

– Đóng Port với tham số –remove-port:
```
firewall-cmd --zone=public --remove-port=9999/tcp
firewall-cmd --zone=public --remove-port=9999/tcp --permanent
```
![image](https://user-images.githubusercontent.com/110179869/195029276-e56678a1-c813-4148-bbba-cc716de53a63.png)
