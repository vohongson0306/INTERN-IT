# Bước 1: Cài đặt Nginx. Vì Nginx có sẵn trong kho lưu trữ của Ubuntu nên ta có thể trực tiếp cài đặt Nginx bằng hệ thống cài đặt và quản lý gói apt.
## Đầu tiên, tiến hành update các gói trong hệ thống :

`sudo apt install -y update`

![image](https://user-images.githubusercontent.com/110179869/191151628-18f418af-0503-4461-97e7-ba6e17beeaf9.png)

## Cài đặt Nginx cho máy chủ Ubuntu của bạn :

`sudo apt install -y nginx`

![image](https://user-images.githubusercontent.com/110179869/191151709-76096435-88f9-42f5-bfbe-84edbe87e13b.png)

Kiểm tra phiên bản Nginx:

`sudo nginx -v`

![image](https://user-images.githubusercontent.com/110179869/191151774-4dec190f-450b-442b-abf9-4493afc0d5c6.png)

nginx version: nginx/1.18.0 (Ubuntu)
Cho phép Nginx khởi động cùng hệ thống :

`sudo systemctl enable nginx`

![image](https://user-images.githubusercontent.com/110179869/191151860-42057a74-07b0-44d1-a802-2d429c3088f6.png)

Khởi động và kiểm tra trạng thái của dịch vụ Nginx :
```
systemctl start nginx 
systemctl status nginx
```
![image](https://user-images.githubusercontent.com/110179869/191151952-f886896d-6412-42a8-8416-afaa1821b669.png)

# Bước 2: Cấu hình tường lửa
## Sử dụng ufw để biết cách sử dụng cấu hình tường lửa cho Nginx :

`sudo ufw app list `

![image](https://user-images.githubusercontent.com/110179869/191152329-453729e0-12c6-475d-845e-5658ce0a800a.png)

## Ta thấy rằng đối với nginx, có 3 cấu hình có thể để cấu hình cho nginx, nhưng hiện tại mình chưa có cấu hình sử dụng SSL đối với trang web nên mình chỉ cho lưu lượng đi qua port 80.

## Kích hoạt điều trên bằng cách sử dụng câu lệnh sau:

`sudo ufw allow 'Nginx HTTP'`

![image](https://user-images.githubusercontent.com/110179869/191152470-697f5657-56ec-4f84-875d-b3668b3e4a34.png)

## Sau đó kiểm tra lại thay đổi với lệnh sau:

`sudo ufw status`

![image](https://user-images.githubusercontent.com/110179869/191152552-370e878d-4781-430f-b254-87d3e83bd626.png)

# Bước 3: Kiểm tra trang web
## Để kiểm tra trang web, ta mở trình duyệt và nhập vào địa chỉ ip của máy chủ Nginx.
``` http://IP_address ```

![image](https://user-images.githubusercontent.com/110179869/191152700-9c473227-fb1b-4229-8c35-e244ed7a4c9d.png)

