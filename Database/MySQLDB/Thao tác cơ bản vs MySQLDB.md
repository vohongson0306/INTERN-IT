![image](https://user-images.githubusercontent.com/110179869/192216308-43b7e330-74b7-48a3-a70a-8968f892de76.png)

![image](https://user-images.githubusercontent.com/110179869/192228264-9ec0e241-fb65-4ea0-a559-fff48a7634e3.png)

# 1.DATABASE
- Tạo cơ sở dữ liệu
` CREATE database tên-database;`

![image](https://user-images.githubusercontent.com/110179869/192229002-2fc19fb6-ac4f-4a81-a6a9-6ee9515066f7.png)

- Xem cơ sở dữ liệu
 
` show database; `

![image](https://user-images.githubusercontent.com/110179869/192229038-883f78ff-e34d-42cf-8f1b-103d35315ae0.png)

- Xoá 1 database
 
`DROP databases tên database;`

![image](https://user-images.githubusercontent.com/110179869/192229622-999bae26-8347-4f50-8ea5-1c6ee0ee689d.png)

- Để làm việc với 1 cơ sở dữ liệu
 
`USE tên-database;`

![image](https://user-images.githubusercontent.com/110179869/192230183-16ec94b3-cc77-4e49-bec1-01883a30b0d0.png)

# 2.USER
- Tạo USER
`create user 'user-name'@'IP' identified by 'password';

![image](https://user-images.githubusercontent.com/110179869/192230667-98954572-9da8-4dc2-8936-991a67d6b2c3.png)

- Hiển thị toàn bộ user
      mysql> SELECT * FROM mysql.user;
- Xóa một user
      mysql> DELETE FROM mysql.user WHERE user = ' ';
- Xóa tất cả user mà không phải root
      mysql> DELETE FROM mysql.user WHERE NOT (host="localhost" AND user="root");
- Đổi tên tài khoản root
      mysql> UPDATE mysql.user SET user="mydbadmin" WHERE user="root";
- Gán quyền cho một user
      mysql> GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost'
- Đổi mật khẩu cho một user
      mysql> UPDATE mysql.user SET password=PASSWORD("newpass") WHERE User='username';
# 3. Các thao tác với table
Trong một trường thì có kiểu dữ liệu sẽ được phân ra thì một số kiểu của trường là:
```
    Kiểu số : int; float;...
    date time: yyyy-mm-dd : ngày tháng năm ; HH:MM:SS (giờ phút giây)
    Kiểu chuỗi: char; varchar
```
- Tạo bảng table

       ` CREATE TABLES name(trường trong bảng );`
- Hiển thị tất cả các bảng

`show tables;`

- Đổi tên bảng

`rename table (tên bảng 1) to (tên bảng 2);`

-  Xóa bảng

`drop table (tên bảng);`

- Hiển thị dữ liệu trong bảng

`SELECT * FROM tablename;`

# 4.Thao tác với cột và hàng
- Hiển thị các cột trong bảng

`  mysql> DESC mytable;`

hoặc

`  mysql> SHOW COLUMNS FROM mytable;`

- Thêm cột cho bảng

` alter table tablename add column varchar(40) first;`

ta kiểm tra lại bằng show tables

Xóa một cột tương tự thêm thay add bằng drop

- Thay đôi tên của cột

`alter table sinhvien change columnold columnnew (thuộc tính của trường);`

- Giải thích đọc bảng
```
        filed : tên cột
        Type : Kiểu của trường
        NULL : có được để giá trị null không
        key : có là key chính hay không
        default : mặc định của cột là
```

