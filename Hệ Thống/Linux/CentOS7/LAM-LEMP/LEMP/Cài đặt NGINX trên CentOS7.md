# Cài đặt Nginx
## Bước 1: Cài đặt EPEL repository
`yum install epel-release -y`
# Bước 2: Cài đặt Nginx

`yum install nginx -y`

Sau khi hoàn tất ta có thể sử dụng các lệnh sau để quản lý Nginx
```sh
systemctl start nginx      // Khởi động dịch vụ Nginx
systemctl stop nginx       // Dừng dịch vụ Nginx
systemctl reload nginx     // Tải lại dịch vụ Nginx
systemctl restart nginx    // Khởi động lại dịch vụ Nginx
systemctl enable nginx     // Thiết lập Nginx khởi động cùng hệ thống
systemctl disable nginx    // Vô hiệu hoá Nginx khởi động cùng hệ thống
systemctl status nginx     // Xem trạng thái dịch vụ Nginx
```


# Bước 3: Khởi động dịch vụ
```
systemctl start nginx
systemctl enable nginx
```
# Bước 4: Mở dịch vụ trên Firewalld
```
firewall-cmd --permanent --add=service=http
firewall-cmd --permanent --add=service=https
firewall-cmd --reload
```

- Kiểm tra


- Cấu hình file Vhost: Để duy trì quản lý dễ dàng, ta nên tạo một file cấu hình riêng cho mỗi miền. Các file cấu hình phải kết thúc bằng .conf và được lưu trữ tại /etc/nginx/conf.d/

`vi /etc/nginx/conf.d/tubui.xyz.conf`

- Thêm vào file tubui.xyz.conf nội dung sau
```
server {
    listen 80;
    server_name www.tubui.xyz tubui.xyz;
    access_log /usr/share/nginx/html/access.log;
    error_log /usr/share/nginx/html/error.log;
    root /usr/share/nginx/html;
    index index.php index.html index.htm;
}
```


