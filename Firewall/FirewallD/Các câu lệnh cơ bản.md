# 1. Một vài lệnh cơ bản của FirewallD:

          systemctl start firewalld         

- khởi động dịch vụ firewalld

          systemctl restart firewalld      

- khởi động lại

          systemctl enable firewalld       

- khởi động cùng hệ thống

          systemctl stop firewalld         

- tắt firewalld

          systemctl disable firewalld       

- vô hiệu hóa firewalld

          firewall-cmd --state             

- trạng thái hoạt động

          firewall-cmd --zone=public --list-ports    

- xem các danh sách cổng tương ứng với dịch vụ của zone cụ thể nào đó

# 2. Các lệnh để mở cổng.


        firewall-cmd --zone=public --add-port=22/tcp --permanent
        firewall-cmd --zone=public --add-port=80/tcp --permanent
        firewall-cmd --zone=public --add-port=443/tcp --permanent
        firewall-cmd --zone=public --add-port=3306/tcp --permanent


# 3. Mở cổng UDP

- Cũng giống như các cổng TCP, chúng ta có thể mở cổng UDP để truy cập công khai bằng lệnh dưới đây:

        firewall-cmd –zone = public –add-port = 443 / udp –permosystem

- Configuration file:

- Lưu cấu hình mặc định để tránh sửa đổi chúng.

        /usr/lib/firewalld  

- Lưu tệp cấu hình hệ thống, bạn sẽ ghi đè cấu hình mặc định.

        /etc/firewalld 

- Firewalld cung cấp các tệp cấu hình chín vùng theo mặc định: block.xml, dmz.xml, drop.xml, external.xml, home.xml, internal.xml, public.xml, trust.xml, work.xml
        
        /usr/lib/firewalld/zone/ 

- Hiển thị tất cả các lệnh tường lửa có sẵn

          firewall-cmd –help 

          firewall-cmd –version

          firewall-cmd –state

- Xem khu vực được sử dụng bởi giao diện mạng.

          firewall-cmd –get-active-zones 

- Hiển thị tất cả các cấu hình trong khu vực được chỉ định.

          firewall-cmd –zone=public –list-all 

- Liệt kê tất cả các cấu hình vùng

          firewall-cmd –list-all-zones 

- `firewall-cmd –get-default-zone` Xem khu vực mặc định

- `firewall-cmd –set-default-zone=internal` Đặt vùng mặc định

- `firewall-cmd –get-zone-of-interface=eth0` Xem khu vực mà giao diện được chỉ định thuộc về.

- `firewall-cmd –zone=public –add-interface=eth0` Thêm giao diện vào vùng, tất cả các giao diện mặc định đều là công khai, có giá trị vĩnh viễn cộng thêm –permanent sau đó reload


# 4.  Need to có giá trị vĩnh viễn, thêm –permanent

- `firewall-cmd –panic-on|off   ` reject | mở tất cả các gói

- `firewall-cmd –query-panic ` Xem có từ chối không

- `firewall-cmd –reload ` Cập nhật các quy tắc tường lửa mà không cần ngắt kết nối

- `firewall-cmd –complete-reload` tương tự để khởi động lại các quy tắc cập nhật

- `firewall-cmd –zone=dmz –list-ports` Xem tất cả các cổng đang mở

- `firewall-cmd –zone=dmz –add-port=8080/tcp `  Thêm một cổng vào khu vực

- `Firewall-cmd –get-services` Xem các dịch vụ có sẵn mặc định

- `Firewall-cmd –zone=zone –(add|remove)-service=http –permanent` Bật hoặc tắt vĩnh viễn dịch vụ HTTP

- `Firewall-cmd –zone=public –add-port=123456/tcp –permanent`  Thêm lưu lượng TCP cho cổng 123456

- `Firewall-cmd –zone=public –add-forward-port=port=80:proto=tcp:toport=123456` Lưu lượng đi từ cổng 80 đến cổng 123456
