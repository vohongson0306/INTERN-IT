# Bước 1: Tạo MongoDB repository
- Để thêm kho lưu trữ MongoDB vào hệ thống của bạn, hãy tạo file mongodb-org.repo trong thư mục /etc/yum.repos.d/:

    `nano /etc/yum.repos.d/mongodb-org.repo`

Dán nội dung sau vào:
```
    [mongodb-org-4.2]
    name=MongoDB Repository
    baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/
    gpgcheck=1
    enabled=1
    gpgkey=https://www.mongodb.org/static/pgp/server-4.2.asc
```


# Bước 2: Cài đặt MongoDB
- Bây giờ kho lưu trữ đã được thêm, bạn có thể cài đặt gói mongodb-org bằng lệnh sau:

   ` yum install mongodb-org -y`
- Các gói sau sẽ được cài đặt trên hệ thống của bạn như là một phần của gói mongodb-org:
```
    mongodb-org-server – Trình nền mongod, và các tập lệnh và cấu hình init tương ứng.
    mongodb-org-mongos – Daemon mongos.
    mongodb-org-shell – Shell mongo, giao diện JavaScript tương tác với MongoDB, được sử dụng để thực hiện các tác vụ quản trị dòng lệnh.
    mongodb-org-tools – Chứa một số công cụ MongoDB để nhập và xuất dữ liệu, số liệu thống kê, cũng như các tiện ích khác.
```


# Bước 3: Khởi động MongoDB
- Sau khi cài đặt hoàn tất, hãy khởi động MongoDB bằng các lệnh sau:
```
    systemctl start mongod
    systemctl enable mongod
```
- Xem trang thai của mongodb
```
   systemctl status mongod
```

# Bước 4: Xác minh cài đặt MongoDB
- Để xác minh cài đặt, hãy chạy lệnh sau:

     `mongo`

- Tiếp theo, hãy gõ lệnh sau sẽ hiển thị phiên bản MongoDB:

     ` db.version()`
     
     
     
     
