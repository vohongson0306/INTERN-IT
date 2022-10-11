# Cài đặt FirewallD
– FirewallD được cài đặt mặc định trên CentOS 7. Cài đặt nếu chưa có:
```
yum install firewalld
```
– Khởi động FirewallD:
```
systemctl start firewalld
```
– Kiểm tra tình trạng hoạt động
```
systemctl status firewalld
```
– Thiết lập FirewallD khởi động cùng hệ thống
```
systemctl enable firewalld
```
Kiểm tra lại :
```
systemctl is-enabled firewalld
```
## Ban đầu, bạn không nên cho phép FirewallD khởi động cùng hệ thống cũng như thiết lập Permanent, tránh bị khóa khỏi hệ thống nếu thiết lập sai. Chỉ thiết lập như vậy khi bạn đã hoàn thành các quy tắc tường lửa cũng như test cẩn thận.
– Khởi động lại
```
systemctl restart firewalld
firewall-cmd --reload
```
– Dừng và vô hiệu hóa FirewallD
```
systemctl stop firewalld
systemctl disable firewalld
```
