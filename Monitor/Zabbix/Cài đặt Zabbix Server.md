# Yêu cầu hệ thống:
- Đã cài đặt máy chủ web Apache.
- PHP và các extension cần thiết.
- Máy chủ Cơ sở dữ liệu MySQL/MariaDB.
# Bước 1: Cài đặt các gói cần thiết
- Cài đặt Zabbix repository
```
rpm -Uvh https://repo.zabbix.com/zabbix/5.0/rhel/7/x86_64/zabbix-release-5.0-1.el7.noarch.rpm
yum clean all
```
![image](https://user-images.githubusercontent.com/110179869/194791743-d336df79-65e3-420c-92a6-178d1ae49aee.png)

- Cài đặt Zabbix Server và Zabbix Agent
```
yum install zabbix-server-mysql zabbix-agent
```
![image](https://user-images.githubusercontent.com/110179869/194791943-6025fe0e-7247-453c-99cd-8f70750a50e8.png)

- Cài đặt Zabbix Frontend

Enable Red HAt Software Collections
```
yum install -y centos-release-scl
```
![image](https://user-images.githubusercontent.com/110179869/194792013-afab9fc5-7377-4f0c-aed3-f3f302b35ad3.png)

- Chỉnh sửa tập tin zabbix.repo để bật cho phép cài zabbix-frontend từ repository.
```
nano /etc/yum.repos.d/zabbix.repo
```
- Đặt giá trị `enable=1` vào `[zabbix-frontend]`

![image](https://user-images.githubusercontent.com/110179869/194792078-a9450e64-13b0-4462-8d33-462b81df2bb8.png)

- Cài đặt Zabbix frontend từ repository
```
yum install zabbix-web-mysql-scl zabbix-apache-conf-scl
```
![image](https://user-images.githubusercontent.com/110179869/194792171-f6ebc900-f534-474c-b28d-2bc4eb52b3aa.png)

# Bước 2: Tạo và thêm database Zabbix
- Khởi động MariaDB Service
```
systemctl enable mariadb
systemctl start mariadb
```
![image](https://user-images.githubusercontent.com/110179869/194792281-df817ddc-d181-4793-bec4-e11dc7e63a1d.png)

- Tạo database cho Zabbix
- Login vào MariaDB.
```
mysql -u root -p
```
![image](https://user-images.githubusercontent.com/110179869/194792335-ed4194f3-c751-411f-a791-05f50202fc40.png)

Tạo user và database cho Zabbix.
```
MariaDB [(none)]> create database zabbix character set utf8 collate utf8_bin;
MariaDB [(none)]> create user zabbix@localhost identified by 'password';
MariaDB [(none)]> grant all privileges on zabbix.* to zabbix@localhost;
MariaDB [(none)]> flush privileges;
MariaDB [(none)]> quit;
```
![image](https://user-images.githubusercontent.com/110179869/194792397-4201f19a-d76a-4dfa-980d-ed7340c4f155.png)

- Import database Zabbix
```
zcat /usr/share/doc/zabbix-server-mysql*/create.sql.gz | mysql -u zabbix -p zabbix
```
Nhập password đã tạo ở trên.

![image](https://user-images.githubusercontent.com/110179869/194792477-bf291f3e-2056-48b6-a526-02ef6e943de1.png)

# Bước 3: Cấu hình Zabbix server
Chỉnh sửa `file zabbix_server.conf`, thay đổi các thông số: `database host`, `database name`, `database username`, `database password`.
```
nano /etc/zabbix/zabbix_server.conf
```

![image](https://user-images.githubusercontent.com/110179869/194792859-449a8f13-80c6-49d7-80de-bda7d31e9e9b.png)

![image](https://user-images.githubusercontent.com/110179869/194792938-3c872c03-b96c-4f65-8de2-db1297492e9f.png)

# Bước 4: Cấu hình PHP
- Mở tập tin zabbix.conf
```
nano /etc/opt/rh/rh-php72/php-fpm.d/zabbix.conf
```
- nano ./conf/zabbix.conf.php
- Sửa `[date.timezone]` thành `Asia/Ho_Chi_Minh`

![image](https://user-images.githubusercontent.com/110179869/194793036-a55578f1-0f66-43a5-a151-01cf9f4200be.png)

# Bước 5: Khởi động Zabbix server và agent
```
systemctl restart zabbix-server zabbix-agent httpd rh-php72-php-fpm
systemctl enable zabbix-server zabbix-agent httpd rh-php72-php-fpm
```
![image](https://user-images.githubusercontent.com/110179869/194793129-c2bd1afc-2968-47c8-a843-1c22abf2d94f.png)

# Bước 6: Thiết lập firewall
```
firewall-cmd --add-service={http,https} --permanent
firewall-cmd --add-port={10051/tcp,10050/tcp} --permanent
firewall-cmd --reload
```
![image](https://user-images.githubusercontent.com/110179869/194793163-cd96043b-f9b4-4bb5-9e41-e826ea39b786.png)

# Bước 7: Thiết lập Zabbix Dashboard
- Sau khi cài đặt hoàn tất, mở trình duyệt và truy cập: `http://IP-VPS/zabbix.`

![image](https://user-images.githubusercontent.com/110179869/194793219-eb003754-9357-45d4-8c0a-87ff7c3bd229.png)

- Nhấn `Next Step`.

![image](https://user-images.githubusercontent.com/110179869/194793788-7ec2f324-4287-479b-867e-11e00c6f7991.png)

- Nhập tài khoản mật khẩu `database` đã thiết lập -> `Next Step`.

![image](https://user-images.githubusercontent.com/110179869/194793834-1e877101-3655-4fe1-b638-265fd4cbf1af.png)

- Đặt tên `Zabbix Server` -> `Next Step`.

![image](https://user-images.githubusercontent.com/110179869/194793878-0ab47632-44fa-4251-b3f2-384d21ea06d6.png)

- Kiểm tra lại thông tin đã nhập -> `Next Step`.

![image](https://user-images.githubusercontent.com/110179869/194793906-d68713d8-2cd5-410f-8603-55a82f16cba3.png)

- Nhấn `Finish`.

![image](https://user-images.githubusercontent.com/110179869/194793924-76a8bf73-90d4-43af-9723-7f3ae8260510.png)

- Sau khi thiết lập xong, bạn đăng nhập vào `Zabbix Dashboard` bằng tài khoản mặc định `Admin / zabbix`.

![image](https://user-images.githubusercontent.com/110179869/194794179-ba2f5279-7ef4-44b2-999d-3f0fe9e35d98.png)

- Giao diện `Zabbix Server`

![image](https://user-images.githubusercontent.com/110179869/194794121-57e22558-1631-4247-86e8-b97a7c4a0ea8.png)
