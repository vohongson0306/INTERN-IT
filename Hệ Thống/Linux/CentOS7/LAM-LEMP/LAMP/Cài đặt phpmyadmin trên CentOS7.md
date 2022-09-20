# Bước 1:Sử dụng lệnh sau để install epel-release CentOS:✔
 `yum install epel-release`
 
 ![image](https://user-images.githubusercontent.com/110179869/189573178-573eac1f-c11e-4c94-bb7c-c853a8cc3f5e.png)

# Bước 2:Cài đặt phpMyadmin

`yum install phpmyadmin`

![image](https://user-images.githubusercontent.com/110179869/189573310-0c4471f4-587a-4ede-acdd-5d6866a09da7.png)

# Bước 3:Cấu hình phpmyadmin, bạn vào file phpmyadmin.conf để thiết lập
`nano /etc/httpd/conf.d/phpMyAdmin.conf`

![image](https://user-images.githubusercontent.com/110179869/189573422-d7c112ad-35af-44c5-9cdf-fd23061132b0.png)

## Đây bạn sẽ thấy 4 chuỗi ip yêu cầu khác nhau, khớp với chuỗi IP dài. Giá trị mặc định là 127.0.0.1. Thay thế giá trị đó bằng IP máy bạn (192.168.239.131) sẽ sử dụng để truy cập phpMyAdmin

![image](https://user-images.githubusercontent.com/110179869/189573831-4188626f-8296-4d2f-84ad-dce638bfaf9a.png)

![image](https://user-images.githubusercontent.com/110179869/189573874-b19bf6cd-07cc-4a8d-87f0-8111d62b7abf.png)

![image](https://user-images.githubusercontent.com/110179869/189573904-3c81e433-e85c-4251-bb3e-4a5b90f110aa.png)

![image](https://user-images.githubusercontent.com/110179869/189573934-cdfdb682-8b82-45f2-8532-9a5c7fcc58a8.png)

# Bước 4:Khởi động lại Apache web server

![image](https://user-images.githubusercontent.com/110179869/189574006-96ab5b25-b5d8-4193-b442-326730d39193.png)

## Mở trình duyệt, vào đường dẫn sau để truy cập vào phpMyadmin: https://192.168.239.131/phpmyadmin

![image](https://user-images.githubusercontent.com/110179869/189572995-6b017a31-49cd-4c63-9d4e-292f3b015db1.png)

## đăng nhập vào bằng tài khoản root để kiểm tra:

![image](https://user-images.githubusercontent.com/110179869/189574139-31337dae-02a9-48ef-901f-5ed2385fe34e.png)

