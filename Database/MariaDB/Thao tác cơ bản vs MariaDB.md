# 1. Đăng nhập
- Đăng nhập vào MariaDB Server với lệnh mysql -u root -p và nhập mật khẩu root.

   ` mysql -u root -p`
   
 ![image](https://user-images.githubusercontent.com/110179869/191648879-bb6d2da3-14c7-40bd-8790-7bd0406ec21f.png)
  
- trong đó: Trong đó: root là user đăng nhập, bạn thay bằng tài khoản của bạn. Tùy chọn -p để bạn nhập mật khẩu

# 2.Thao tác với DB.
- create database :được dùng để tạo cơ sở dữ liệu mới, trống.

![image](https://user-images.githubusercontent.com/110179869/191649242-86043fa0-254c-4563-977a-2827b50ded94.png)

![image](https://user-images.githubusercontent.com/110179869/191649541-6d00fc6a-d404-483f-a244-02ae1caaf75a.png)

![image](https://user-images.githubusercontent.com/110179869/191649635-1f754558-8247-465b-933f-f2b0a1a1c5e9.png)

- drop database : được dùng để hủy hoàn toàn một cơ sở dữ liệu sẵn có.


- show databases: xem danh sách DB

![image](https://user-images.githubusercontent.com/110179869/191650020-7f39e6e0-4a74-47bb-854d-1fb5ffc55960.png)

- use : được dùng để lựa chọn một cơ sở dữ liệu làm mặc định.

![image](https://user-images.githubusercontent.com/110179869/191650078-9d550cf2-454c-4ec4-ad4c-45193eec78da.png)

# 3.Thao tác với bảng
## CREATE TABLE được dùng để tạo một bảng mới, nơi mà dữ liệu của bạn thực sự được lưu trữ.

![image](https://user-images.githubusercontent.com/110179869/191650409-06f1ecbd-2451-463d-9ae6-115c5ad2ed67.png)

- ALTER TABLE được dùng để sửa một định nghĩa bảng sẵn có.

- DROP TABLE :được sử dụng để hủy hoàn toàn một bảng sẵn có.

- DESCRIBE hiển thị cấu trúc của một bảng.

## show tables: hiển thị danh sách bảng trong DB.

![image](https://user-images.githubusercontent.com/110179869/191650503-801a2a84-a619-4853-b566-5d4b9486c09a.png)

# 4.Thao tác với Dữ liệu của bạn
## SELECT được dùng khi bạn muốn đọc (hoặc lựa chọn) dữ liệu của bạn.

- UPDATE được sử dụng khi bạn muốn thay đổi (hoặc cập nhật) dữ liệu sẵn có.

- DELETE được sử dụng khi bạn muốn loại bỏ (hoặc xóa) dữ liệu sẵn có.

- REPLACE được sử dụng khi bạn muốn thêm hoặc thay đổi (hoặc đổi chỗ) dữ liệu mới hoặc dữ liệu đã có.

- TRUNCATE được sử dụng khi bạn muốn làm trống (hoặc xóa) tất cả dữ liệu từ mẫu.

# 5.Thao tác với user.
- Hiển thị toàn bộ users:

 `select user,host,password from mysql.user;`

![image](https://user-images.githubusercontent.com/110179869/191650880-fdeb027d-0dc2-4fab-a71b-5c018babc706.png)

- tạo user mới:

` CREATE USER '[user name]'@'localhost' IDENTIFIED BY '[password user]';`

![image](https://user-images.githubusercontent.com/110179869/191651070-8373c221-5b74-4795-a5e1-6b4ae6ab4d81.png)

- Xóa null user:
`
              DELETE FROM mysql.user WHERE user = ' ';`
              
- Xóa tất cả user mà không phải root:

            `  DELETE FROM mysql.user WHERE NOT (host="localhost" AND user="root");`
            
- Đổi tên tài khoản root :

              ` UPDATE mysql.user SET user="toor" WHERE user="root";`
              
- Gán full quyền cho một user mới:

              ` GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'mypass' WITH GRANT OPTION;`
              
- Phân quyền chi tiết cho một user mới:

              ` GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, INDEX, ALTER, CREATE TEMPORARY TABLES, LOCK TABLES ON mydatabase.* TO 'username'@'localhost' IDENTIFIED BY 'mypass';`
              
- Gán full quyền cho một user mới trên một database nhất định:

             `  GRANT ALL PRIVILEGES ON mydatabase.* TO 'username'@'localhost' IDENTIFIED BY 'mypass' WITH GRANT OPTION;`
             
- Thay đổi mật khẩu user:

            `UPDATE mysql.user SET password=PASSWORD("newpass") WHERE User='username';`
            
- Xóa user:

           ` DELETE FROM mysql.user WHERE user="username";`
           
- reload user:

             `FLUSH PRIVILEGES;`
             
- Thoát khỏi MariaDB: 


`exit;`


