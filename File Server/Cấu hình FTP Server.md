# Cấu hình VSFTPD
- File cấu hình vsftpd nằm tại `/etc/vsftpd/vsftpd.conf`

![image](https://user-images.githubusercontent.com/110179869/192925364-b2266705-6805-418d-a0ce-f4fda17deed3.png)

- Copy file cấu hình để backup
```
      cp /etc/vsftpd/vsftp.conf /etc/vsftpd/vsftpd.conf.backup
```      
- Chỉnh sửa file cấu hình vsftpd.conf
```
      vi /etc/vsftpd/vsftpd.conf
```
- FTP Access: Ta không cho kết nối nặc danh, mà chỉ cho kết nối cục bộ vào FTP server
```
      anonymous_enable=NO

      local_enable=YES
```      
- Cho phép người dùng nội bộ tải lên
```
      write_enable=YES
```      
![image](https://user-images.githubusercontent.com/110179869/192925525-a60603de-61e5-4d01-b81b-1378b59e3ecf.png)

- Giữ người dùng trong thư mục của họ. Tại đây ta sẽ chroot tất cả user trừ các user trong chroot_list
```
      chroot_local_user=YES

      allow_writeable_chroot=YES

      chroot_list_enable=YES

      chroot_list_file=/etc/vsftpd/chroot_list
```     
![image](https://user-images.githubusercontent.com/110179869/192926135-7b17ab2d-5956-41c3-bc73-170ac1d57687.png)

- Banner khi người dùng login vào FTP server
```
      ftpd_banner="Welcome FTP Server"
```     
![image](https://user-images.githubusercontent.com/110179869/192926376-a51fd61d-e5d3-4491-9f45-f031ba22e83b.png)

- Giới hạn khoảng các cổng cho FTP passive
```
      pasv_min_port=30000

      pasv_max_port=31000
```      
- Giới hạn User được phép truy cập vào hệ thống: Nếu muốn giới hạn các User local được đăng nhập vào hệ thống FTP server. Ta thêm vào các dòng sau. Khi đó, những User có trong file /etc/vsftpd/user_list mới được truy cập vào hệ thống
```
      userlist_enable=YES

      userlist_file=/etc/vsftpd/user_list

      userlist_deny=NO
```      
![image](https://user-images.githubusercontent.com/110179869/192926741-04366c44-e0f2-4008-8802-fe353a49a182.png)

- Thời gian hệ thống: Ta sử dụng thời gian local

      use_localtime=YES
- Khởi động lại dịch vụ và cho phép các cổng FTP passive đi qua tường lửa
```
      systemctl restart vsftpd

      firewall-cmd --permanent --add-port=30000-31000/tcp

      firewall-cmd --reload
```      
![image](https://user-images.githubusercontent.com/110179869/192927123-4eb43541-128a-48f7-8e98-d2548cd1fa6d.png)

      
      
      
      
      
      
      
      
      
      
