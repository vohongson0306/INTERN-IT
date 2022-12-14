# 1.Đăng Nhập
## Có 2 chế độ xác thực chính là Windows Authentication và SQL Server Authentication
- Chế độ Windows Authentication: Là chế độ xác thực người dùng windows, chỉ cần có user vào windows là được, không cần nhập Password.
- Chế độ SQL Server Authentication: Là chế độ xác thực người dùng mức SQL Server, do SQL server quản lý user và password, người dùng phải có user và password mới có thể truy cập vào SQL Server - SQL Server có 1 user mặc định full quyền là security admin- viết tắt là sa. - Password của user sa do người dùng nhập vào khi cài đặt SQL Server

![image](https://user-images.githubusercontent.com/110179869/191637770-bb394580-c2a0-47f8-9774-9e856d0ed369.png)

## Khi đăng nhập vào thì sẽ có giao diện chính

![image](https://user-images.githubusercontent.com/110179869/191637812-ff1f5e98-a4b8-46dc-bcce-3278f06210b7.png)

# 2.Cách câu lệnh cơ bản:
## Trên cơ sở dữ liệu
- create database : Tạo cơ sở dữ liệu
- drop database : Xoá cơ sở dữ liệu
- alter database : sửa các thông tin của cơ sở dữ liệu
- exec sp_dboption: sửa các thông tin của cơ sở dữ liệu
- dbcc: Điều khiển cơ sở dữ liệu
- create table: tạo bảng
- drop table: xoá bảng
- alter table...add: thêm cột
- alter table...drop column:xoá cột
- alter table...alter column:thêm thuộc tính notnull
- alter table...add primary key:Thêm khoá chính
- alter table...add foreign key:thêm rằng buộc khoá ngoài
- alter table...add default: Thêm ràng buộc mặc định
- exec sp_help:xem thông tin bảng

## Trên bản ghi
- insert...values:thêm các bản ghi vào bảng
- insert...select:thêm các bản ghi từ bảng khác vào bảng
- select...into:đưa kết quả lựa chọn vào bảng mới 
- delete: xoá các bản ghi từ bản
- truncate: xoá toàn bộ bản ghi của bảng
- update: sửa các bản ghi trong bảng

# 3.Thao tác(Chọn new Query và bắt đầu thực hiện các câu lệnh cơ bản)
- Tạo 1 cơ sỡ dữ liệu mới
     ```
     create database son;
     ```
![image](https://user-images.githubusercontent.com/110179869/191639233-ff835f17-fcfb-4921-a14c-978b1e628212.png)

- Tạo bảng cho database và chèn dữ liệu vào bảng:

![image](https://user-images.githubusercontent.com/110179869/191641465-3b0da09b-5366-49cf-9c47-d267bf455d32.png)

![image](https://user-images.githubusercontent.com/110179869/191643642-883e74c7-038a-40d1-ab58-8c831e75bdfd.png)

- Dùng lệnh select để xem dữ kiệu trong bảng

![image](https://user-images.githubusercontent.com/110179869/191643716-3f9b997a-457b-468a-b516-64c64ef05b86.png)

- Dùng lệnh update để cập nhật dữ liệu trong bảng

![image](https://user-images.githubusercontent.com/110179869/191643890-b4e20413-0690-4be6-be76-8d89b62f8c77.png)

![image](https://user-images.githubusercontent.com/110179869/191643930-1bce4e2f-197a-4dc7-b22d-32b06c8fdf7f.png)

- Lệnh delete: chúng ta có thể xóa dữ liệu, xóa database

![image](https://user-images.githubusercontent.com/110179869/191644000-c9a6c9d3-8690-444f-9910-027a3fabffe3.png)

![image](https://user-images.githubusercontent.com/110179869/191644034-21336275-1158-4757-baa0-f97bc3fffb63.png)



