# Khởi tạo User FTP:
```
useradd tên-user
passwd tên-user
```
![image](https://user-images.githubusercontent.com/110179869/192928552-c560fa6d-2ba5-4dfd-91a9-2bd2b4ff5369.png)

# Sau khi tạo user thì thư mục mặc định của tài khoản này sẽ ở /home/son1
- Cấp quyền truy cập đến FTP server
  - Tạo file chroot_list trong /etc/vsftpd
  - Thêm user son1 vào file /etc/vsftpd/chroot_list để có thể truy cập vào server

![image](https://user-images.githubusercontent.com/110179869/192929057-3935f343-4b94-4727-a288-17136b333528.png)

# Chỉ định thư mục home khi người dùng đăng nhập vào hệ thống
- Tạo thư mục user_conf
` mkdir /etc/vsftpd/user_conf`
- Chỉ định thư mục home cho user son1 và thêm các dòng lệnh tương ứng với mỗi file
 ```
 vi /etc/vsftpd/user_conf/son1
 local_root=/var/www/son1
```
![image](https://user-images.githubusercontent.com/110179869/192929350-9914b9c4-17f3-4b25-8158-59bb5d0d036d.png)

# Sau đó restart lại dịch vụ vsftpd
`systemctl restart vsftpd`

Mở WinSCP đăng nhập vào user son1 chọn giao thức FTP, port 21, Nhập user và password

![image](https://user-images.githubusercontent.com/110179869/192929587-2da69053-7878-4241-bdea-f934690e259c.png)

![image](https://user-images.githubusercontent.com/110179869/192929616-384f1988-b892-453e-94ba-36b90183c9c4.png)





