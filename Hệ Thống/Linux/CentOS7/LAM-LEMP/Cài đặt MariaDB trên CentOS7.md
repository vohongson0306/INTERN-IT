# Bước 1: Để cài đặt MariaDB, bạn cần thực hiện lệnh sau:
` yum install -y mariadb mariadb-server `

![image](https://user-images.githubusercontent.com/110179869/189565056-5a18ad36-e763-46f8-b9ac-05fd65e3d731.png)

## Bước 2: Sau khi cài đặt hoàn tất, bạn có thể sử dụng các lệnh sau để quản lý MariaDB:
` systemctl start mariadb      (Khởi động dịch vụ mariadb) `

` systemctl stop mariadb      (Dừng dịch vụ mariadb) `

` systemctl restart mariadb    (Khởi động lại  dịch vụ mariadb) `

` systemctl enable mariadb     (Thiết lập mariadb khởi động cùng hệ thống) `

` systemctl disable mariadb    (Vô hiệu hoá mariadb khởi động cùng hệ thống ) ` 

` systemctl status mariadb     (Xem trạng thái dịch vụ mariadb) `

![image](https://user-images.githubusercontent.com/110179869/189565156-d13b42d3-01d1-44b0-a0f8-05cb5845253d.png)

# Bước 3: Thiết lập bảo mật MariaDB Server
` mysql_secure_installation `

![image](https://user-images.githubusercontent.com/110179869/189565186-2f2e9d91-c1db-4c9b-a9e2-9dd4dfa7f0a6.png)

` Đặt mật khẩu mới`

![image](https://user-images.githubusercontent.com/110179869/189565267-ecc279e3-3035-4f5f-add5-82557b77ab78.png)

`Xóa người dùng ẩn danh?`

![image](https://user-images.githubusercontent.com/110179869/189565323-d595dfeb-4081-4c7a-91cf-8b83c66c093d.png)

`Không cho phép đăng nhập từ xa? `

![image](https://user-images.githubusercontent.com/110179869/189565363-597d4111-3c67-4591-8034-da0ebe397fbc.png)

`Xóa cơ sở dữ liệu thử nghiệm và truy cập vào nó?`

![image](https://user-images.githubusercontent.com/110179869/189565388-79055512-e9e1-40a8-8c30-f5050a73d946.png)

 `Tải lại bảng đặc quyền ngay bây giờ`
 
![image](https://user-images.githubusercontent.com/110179869/189565407-5c31b472-4ab7-4fa0-9368-2e36fb59ed02.png)

# Bước 4: Đăng nhập vào MariaDB Server với lệnh `mysql -u root -p` và nhập mật khẩu root vừa đổi:
![image](https://user-images.githubusercontent.com/110179869/189566631-ed2a46f9-66d4-4c88-a29b-26cf3a818b66.png)
