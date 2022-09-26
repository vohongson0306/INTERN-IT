# Bước 1:Cập nhật hệ thống
` yum update `

![image](https://user-images.githubusercontent.com/110179869/192211383-da72fa2f-007c-481e-b604-bdbecc1894b7.png)

# Bước 2:Tải về từ kho lưu trữ:
`wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm`

![image](https://user-images.githubusercontent.com/110179869/192211567-465cb264-fe4f-4fa3-878f-548cc1c6a012.png)

# Bước 3:Thêm kho lưu trữ và cập nhật lại:
`rpm -ivh mysql-community-release-el7-5.noarch.rpm`

![image](https://user-images.githubusercontent.com/110179869/192212026-04dda010-20dd-4706-a06b-a05a3f47cece.png)

# Bước 3:Cài đặt MySQL:
`yum install mysql-server`

![image](https://user-images.githubusercontent.com/110179869/192212395-e7925645-344c-4cc5-aa60-356d5ccc7765.png)

# Bước 4:Khởi động MySQL:
`systemctl start mysqld`

![image](https://user-images.githubusercontent.com/110179869/192212682-e4497418-d183-4f39-bd47-22592068091d.png)

# Bước 5:Cài đặt hệ thống:
`mysql_secure_installation`

![image](https://user-images.githubusercontent.com/110179869/192212972-30bcf886-2d72-4af2-bbfb-07a803e74b2c.png)

- Đặt lại mật khẩu:

![image](https://user-images.githubusercontent.com/110179869/192213744-a382e966-84d9-4214-a4a9-0cb39a24358e.png)

- Xoá người dùng ẩn danh:

![image](https://user-images.githubusercontent.com/110179869/192213670-92a05b25-7b8c-4eac-af88-a1ae17af839f.png)

- Không cho phép đăng nhập từ xa:

![image](https://user-images.githubusercontent.com/110179869/192213599-c4908bd5-0c3e-4711-9fed-c35992c656ac.png)

- Loại bỏ cơ sở dữ liệu kiểm tra và truy cập vào nó?

![image](https://user-images.githubusercontent.com/110179869/192213526-cf490854-9559-4ac9-8353-d4daf9ec6eda.png)

- Tải lại các bảng đặc quyền ngay bây giờ?

![image](https://user-images.githubusercontent.com/110179869/192213446-49c4cb33-f7a4-4d3b-8a21-d1878bd9123f.png)

# Bước 6:Đăng nhập vào MySQL:
`mysql -u root -p`

![image](https://user-images.githubusercontent.com/110179869/192214455-64505649-abc1-4da8-80b8-d9182f1c8376.png)





























