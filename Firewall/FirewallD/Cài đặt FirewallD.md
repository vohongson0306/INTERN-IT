# Cài đặt FirewallD
– FirewallD được cài đặt mặc định trên CentOS 7. Cài đặt nếu chưa có:
```
yum install firewalld
```
![image](https://user-images.githubusercontent.com/110179869/195025716-76eaad38-e6c1-4cc2-b30f-1138b3cf5d90.png)

– Khởi động FirewallD:
```
systemctl start firewalld
```
– Kiểm tra tình trạng hoạt động
```
systemctl status firewalld
```
![image](https://user-images.githubusercontent.com/110179869/195025823-d7d6807d-a6d3-42ee-8608-23f0f3769488.png)

– Thiết lập FirewallD khởi động cùng hệ thống
```
systemctl enable firewalld
```
Kiểm tra lại :
```
systemctl is-enabled firewalld
```
![image](https://user-images.githubusercontent.com/110179869/195025928-31ffd7d1-27a6-471f-baa7-c4516ac6c0cb.png)

## Ban đầu, bạn không nên cho phép FirewallD khởi động cùng hệ thống cũng như thiết lập Permanent, tránh bị khóa khỏi hệ thống nếu thiết lập sai. Chỉ thiết lập như vậy khi bạn đã hoàn thành các quy tắc tường lửa cũng như test cẩn thận.
– Khởi động lại
```
systemctl restart firewalld
firewall-cmd --reload
```
![image](https://user-images.githubusercontent.com/110179869/195026045-545fbb08-f5c7-4474-8dd3-5327a592450b.png)

– Dừng và vô hiệu hóa FirewallD
```
systemctl stop firewalld
systemctl disable firewalld
```
