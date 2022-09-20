# Bước 1: Cài đặt mariadb và mariadb server ✔

`yum install mariadb mariadb-server -y`

![image](https://user-images.githubusercontent.com/110179869/191189545-201710d6-7f86-41ba-9221-98a862030eff.png)

- Sau khi hoàn tất, ta có thể sử dụng các lệnh sau để quản lý MariaDB
```
systemctl start mariadb      // Khởi động dịch vụ mariadb
systemctl stop mariadb       // Dừng dịch vụ mariadb
systemctl restart mariadb    // Khởi động lại dịch vụ mariadb
systemctl enable mariadb     // Thiết lập mariadb khởi động cùng hệ thống
systemctl disable mariadb    // Vô hiệu hoá mariadb khởi động cùng hệ thống
systemctl status mariadb     // Xem trạng thái dịch vụ mariadb
```

![image](https://user-images.githubusercontent.com/110179869/191189776-305979ac-9d73-40cd-8264-03f39823f2cf.png)

# Bước 2: Khởi động dịch vụ
```
systemctl start mariadb
systemctl enable mariadb
```

![image](https://user-images.githubusercontent.com/110179869/191189689-04cde1bb-5cb6-43fc-bc23-0881d6b54655.png)

# Bước 3: Cấu hình bảo mật MariaDB

`mysql_secure_installation`

- Khi được nhắc nhập mật khẩu, ta có thể nhấn Enter để trống hoặc cập nhật mật khẩu mới
- Sau đó làm các bước để thiết lập mật khẩu. Cuối cùng, tập lệnh sẽ yêu cầu định cấu hình một số biện pháp bảo mật, bao gồm:
  - Xóa người dùng ẩn danh?
  - Không cho phép đăng nhập từ xa?
  - Xóa cơ sở dữ liệu thử nghiệm và truy cập vào nó?
  - Tải lại bảng đặc quyền ngay bây giờ

![image](https://user-images.githubusercontent.com/110179869/191190949-23314ae5-7e24-4ec7-9033-af58627f9508.png)

![image](https://user-images.githubusercontent.com/110179869/191191275-ddc025c3-d7ae-43d3-a960-9edd252d8162.png)



