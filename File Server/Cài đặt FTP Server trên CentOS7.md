# Cài đặt FTP server trên CentOS 7
- Cài đặt dịch vụ FTP với VSFTPD
- Cập nhật trình quản lý gói

 ` yum update -y`

![image](https://user-images.githubusercontent.com/110179869/192924169-aee95634-bffc-4c43-90c4-5a69d6ac9f87.png)

- Cài đặt VSFTPD

 ` yum install -y vsftpd`

![image](https://user-images.githubusercontent.com/110179869/192924133-06302aa3-9a15-47b9-972e-58a8a3969de7.png)

- Khởi động dịch vụ và cho phép nó khởi động cùng hệ thống
```
  systemctl start vsftpd
  systemctl enable vsftpd
``` 
![image](https://user-images.githubusercontent.com/110179869/192924285-cf0d14e8-7d66-46ae-8118-cffd96689e5a.png)

- Xem trạng thái
```
  systemctl status vsftpd
```
![image](https://user-images.githubusercontent.com/110179869/192924323-4aa6d493-85c4-43c2-b5d2-1835e96c1431.png)

- Cấu hình tường lửa cho dịch vụ FTP và port 21
```
  firewall-cmd --permanent --add-port=21/tcp
  firewall-cmd --permanent --add-service=ftp
  firewall-cmd --reload
```
![image](https://user-images.githubusercontent.com/110179869/192924434-c28cacdc-3bd3-4c4c-bc79-9957b279987b.png)







