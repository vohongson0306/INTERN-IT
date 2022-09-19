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
