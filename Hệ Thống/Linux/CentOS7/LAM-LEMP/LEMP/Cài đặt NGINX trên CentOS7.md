# Cài đặt Nginx
## Bước 1: Cài đặt EPEL repository
`yum install epel-release -y`

![image](https://user-images.githubusercontent.com/110179869/191187245-adfdc5be-98d8-4368-9ebd-1fa3d6858a5a.png)

# Bước 2: Cài đặt Nginx

`yum install nginx -y`

![image](https://user-images.githubusercontent.com/110179869/191187315-077183cd-82f1-4961-b9da-97e92be13621.png)

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

![image](https://user-images.githubusercontent.com/110179869/191187565-280c893e-a7c6-43e5-a962-285c469b7639.png)

# Bước 4: Mở dịch vụ trên Firewalld
```
firewall-cmd --permanent --add=service=http
firewall-cmd --permanent --add=service=https
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/110179869/191188054-8b756cc0-f300-4cb5-bfe3-fbfd6d671ba3.png)

- Kiểm tra


- Cấu hình file Vhost: Để duy trì quản lý dễ dàng, ta nên tạo một file cấu hình riêng cho mỗi miền. Các file cấu hình phải kết thúc bằng .conf và được lưu trữ tại /etc/nginx/conf.d/

`vi /etc/nginx/conf.d/son.xyz.conf`

- Thêm vào file tubui.xyz.conf nội dung sau
```
server {
    listen 80;
    server_name www.son.xyz son.xyz;
    access_log /usr/share/nginx/html/access.log;
    error_log /usr/share/nginx/html/error.log;
    root /usr/share/nginx/html;
    index index.php index.html index.htm;
}
```

![image](https://user-images.githubusercontent.com/110179869/191188354-1c1c3b9b-0e3d-44a6-b661-1751e41f4bc5.png)

