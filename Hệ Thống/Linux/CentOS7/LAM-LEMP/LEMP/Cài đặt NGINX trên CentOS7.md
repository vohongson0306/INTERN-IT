# Cài đặt Nginx
## Bước 1: Cài đặt các gói cần thiết:
`yum install yum-utils -y`

![image](https://user-images.githubusercontent.com/110179869/191394774-e54b9354-b578-40ef-92cc-27fe23657343.png)

# Bước 2:Thêm yum repository
`nano /etc/yum.repos.d/nginx.repo`

![image](https://user-images.githubusercontent.com/110179869/191394908-ea487632-7565-4548-a92f-018dbf4811a1.png)

Dán nội dung dưới đây vào
```
[nginx-stable]
name=nginx stable repo
baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
gpgcheck=1
enabled=1
gpgkey=https://nginx.org/keys/nginx_signing.key
module_hotfixes=true
```
![image](https://user-images.githubusercontent.com/110179869/191395028-bb1acae0-5e6a-4c1e-b97f-48df630d2ab2.png)

# Bước 3: Cài đặt Nginx

`yum install nginx -y`

![image](https://user-images.githubusercontent.com/110179869/191394958-0dc19b80-3151-43c7-bfa0-0226cf70cb45.png)


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

- Kiểm tra, hãy truy cập http://IP-VPS bằng trình duyệt sẽ thấy trang chào mừng của Nginx

![image](https://user-images.githubusercontent.com/110179869/191394117-4decc309-8dda-440d-a8bf-91b6ef35be5f.png)
