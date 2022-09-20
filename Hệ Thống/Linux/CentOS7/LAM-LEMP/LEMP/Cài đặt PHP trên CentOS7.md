# Cài đặt kho lưu trữ Remi để có thể sử dụng các phiên bản PHP mới nhất
## Bước 1: Cài đặt kho Remi
```
yum -y install yum-utils
rpm -Uvh http://rpms.remirepo.net/enterprise/remi-release-7.rpm
```
![image](https://user-images.githubusercontent.com/110179869/191193331-9b5a149d-273a-4848-9e34-ce32ca0c3d71.png)

## Bước 2: Sau khi cài đặt gói Remi xong, cần chọn phiên bản PHP mà mình cần cài đặt và kích hoạt gói chứa phiên bản PHP đó
`yum-config-manager --enable remi-php80`

![image](https://user-images.githubusercontent.com/110179869/191193434-8c8fc235-34dd-4844-86ae-bf3e436a7400.png)


## Bước 3: Cài đặt các module của PHP 8.0
```
yum install -y php php-fpm php-ldap php-zip php-embedded php-cli php-mysql php-common php-gd php-xml php-mbstring php-mcrypt php-pdo php-soap php-json php-simplexml php-process php-curl php-bcmath php-snmp php-pspell php-gmp php-intl php-imap perl-LWP-Protocol-https php-pear-Net-SMTP php-enchant php-pear php-devel php-zlib php-xmlrpc php-tidy php-opcache php-cli php-pecl-zip unzip gcc
```
![image](https://user-images.githubusercontent.com/110179869/191193915-ece457e3-6537-4458-87a4-19f1302b1c4c.png)

## Bước 4: Sau khi cài đặt thành công ta có thể kiểm tra phiên bản PHP bằng lệnh
`php -v`

![image](https://user-images.githubusercontent.com/110179869/191193996-7868b114-f82c-4366-bb6a-481c2ddb0e49.png)

## Bước 5: Khởi động lại Nginx để đảm bảo rằng nó hoạt động với PHP mới được cài đặt
`systemctl restart nginx`

![image](https://user-images.githubusercontent.com/110179869/191194080-489a951d-7e36-435c-b03e-4af2aebc607a.png)

- Mặc định PHP sẽ thực thi file PHP gần nhất nếu không tìm thấy file PHP được request. Để ngăn chặn việc thực thi PHP không mong muốn ta làm như sau

`vi /etc/php.ini`

- Tìm dòng và thay thế bằng dòng sau

`cgi.fix_pathinfo=1  =>  cgi.fix_pathinfo=0`

- Điều chỉnh lại file cấu hình /etc/php-fpm.d/www.conf. Tìm các dòng sau và sửa lại
```
;listen = 127.0.0.1:9000   => listen = /var/run/php_fpm.sock
;listen.owner = nobody     => listen.owner = nginx
;listen.group = nobody     => listen.group = nginx
user = apache              => user = nginx
group = apache             => group = nginx
```

Phần quyền cho php_fpm.sock
```
chmod 666 /var/run/php_fpm.sock
chown nginx:nginx /var/run/php_fpm.sock
```
Khởi động PHP-FPM
```
systemctl start php-fpm
systemctl enable php-fpm
```
