# Bước 1: Tạo MongoDB repository
- Để thêm kho lưu trữ MongoDB vào hệ thống của bạn, hãy tạo file mongodb-org.repo trong thư mục /etc/yum.repos.d/:

    `nano /etc/yum.repos.d/mongodb-org.repo`

![image](https://user-images.githubusercontent.com/110179869/191468225-259a52dd-9fe3-4a51-ba77-87553ce3e563.png)

Dán nội dung sau vào:
```
    [mongodb-org-4.2]
    name=MongoDB Repository
    baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/
    gpgcheck=1
    enabled=1
    gpgkey=https://www.mongodb.org/static/pgp/server-4.2.asc
```
![image](https://user-images.githubusercontent.com/110179869/191468573-2c5ace83-b62e-4257-ba3e-53d4e8191a40.png)

# Bước 2: Cài đặt MongoDB
- Bây giờ kho lưu trữ đã được thêm, bạn có thể cài đặt gói mongodb-org bằng lệnh sau:

   ` yum install mongodb-org -y`
   
![image](https://user-images.githubusercontent.com/110179869/191468948-62bec0ab-956f-4d2e-9be7-ecff04f1d530.png)

- Các gói sau sẽ được cài đặt trên hệ thống của bạn như là một phần của gói mongodb-org:
```
    mongodb-org-server – Trình nền mongod, và các tập lệnh và cấu hình init tương ứng.
    mongodb-org-mongos – Daemon mongos.
    mongodb-org-shell – Shell mongo, giao diện JavaScript tương tác với MongoDB, được sử dụng để thực hiện các tác vụ quản trị dòng lệnh.
    mongodb-org-tools – Chứa một số công cụ MongoDB để nhập và xuất dữ liệu, số liệu thống kê, cũng như các tiện ích khác.
```
![image](https://user-images.githubusercontent.com/110179869/191469156-fa32af27-22f0-4886-b73d-0aa630dbe630.png)


# Bước 3: Khởi động MongoDB
- Sau khi cài đặt hoàn tất, hãy khởi động MongoDB bằng các lệnh sau:
```
    systemctl start mongod
    systemctl enable mongod
```
![image](https://user-images.githubusercontent.com/110179869/191469335-21cfa038-b723-43ba-832f-23d21ca7777d.png)

- Xem trang thai của mongodb
```
   systemctl status mongod
```
![image](https://user-images.githubusercontent.com/110179869/191469403-e4e50446-48ff-4c56-af14-7c54051d8f21.png)

# Bước 4: Xác minh cài đặt MongoDB
- Để xác minh cài đặt, hãy chạy lệnh sau:

     `mongo`
     
![image](https://user-images.githubusercontent.com/110179869/191469550-7a0df8b6-8bdc-4abc-b5dd-3b2b5b6e7c95.png)

- Tiếp theo, hãy gõ lệnh sau sẽ hiển thị phiên bản MongoDB:

     ` db.version()`
 
 ![image](https://user-images.githubusercontent.com/110179869/191469647-ddf86333-9df9-4076-9901-15aab391dd0d.png)
    
     
     
     
