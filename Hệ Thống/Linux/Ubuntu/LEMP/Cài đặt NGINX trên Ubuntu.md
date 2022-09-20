# Bước 1: Cài đặt Nginx. Vì Nginx có sẵn trong kho lưu trữ của Ubuntu nên ta có thể trực tiếp cài đặt Nginx bằng hệ thống cài đặt và quản lý gói apt.
## Đầu tiên, tiến hành update các gói trong hệ thống :

`sudo apt install -y update`

## Cài đặt Nginx cho máy chủ Ubuntu của bạn :

`sudo apt install -y nginx`

Kiểm tra phiên bản Nginx:

`sudo nginx -v`

nginx version: nginx/1.17.10 (Ubuntu)
Cho phép Nginx khởi động cùng hệ thống :

`sudo systemctl enable nginx`

Khởi động và kiểm tra trạng thái của dịch vụ Nginx :
```
systemctl start nginx 
systemctl status nginx
```

