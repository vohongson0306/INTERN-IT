# Bước 1: Cài đặt PHP 8.1 trên CentOS 7
## Cài đặt và kích hoạt kho Remi trên CentOS 7, các bạn cần chạy các lệnh sau:
`yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm`

`yum -y install https://rpms.remirepo.net/enterprise/remi-release-7.rpm`

![image](https://user-images.githubusercontent.com/110179869/189570571-2b68515a-0038-4ecc-ab7d-0cbb8ad2cc16.png)

![image](https://user-images.githubusercontent.com/110179869/189570776-ffb47d31-ebad-4c5d-b515-7cc4f1443eda.png)

## Cài đặt các gói PHP 8.1 và kích hoạt vĩnh viễn, các bạn cần chạy các lệnh sau:
`yum -y install yum-utils`

![image](https://user-images.githubusercontent.com/110179869/189570904-e46c8083-e000-4581-9809-cc16b5b59308.png)

`yum-config-manager --disable 'remi-php*'`

![image](https://user-images.githubusercontent.com/110179869/189570968-b8102056-4fb6-49ce-b74f-4447acec3bc2.png)

`yum-config-manager --enable remi-php81`

![image](https://user-images.githubusercontent.com/110179869/189571045-4076dab8-49e9-4c83-b9fc-203b2dd64196.png)

`yum repolist`

![image](https://user-images.githubusercontent.com/110179869/189571103-8e23f328-22fa-4f9c-aab8-edd99da19654.png)

`yum -y install php php-{cli,fpm,mysqlnd,zip,devel,gd,mbstring,curl,xml,pear,bcmath,json,opcache,redis,memcache}`

![image](https://user-images.githubusercontent.com/110179869/189571204-f3b17908-dcbd-4b8f-bd7b-8d7b3943e6c0.png)

# Bước 2: Kiểm tra phiên bản PHP sau khi cài đặt ` php -v `

![image](https://user-images.githubusercontent.com/110179869/189571286-3420947a-1b2a-4b3a-a150-33bba796b970.png)

# Bước 3: Kiểm tra PHP hoạt động với máy chủ web Apache

`#vi /var/www/html/info.php`

![image](https://user-images.githubusercontent.com/110179869/189571569-8bc6b517-35b9-4788-aa18-8c20a0bbdf82.png)

![image](https://user-images.githubusercontent.com/110179869/189571524-53be31d7-76f3-4184-86aa-e72b9959425c.png)


## Sau khi cài đặt xong chúng ta cần khởi động lại máy chủ Apache:

`#systemctl restart httpd.service`

![image](https://user-images.githubusercontent.com/110179869/189571884-95cf67fc-3cf7-4097-a947-de330becf7e7.png)


Bây giờ các bạn mở trình duyệt lên và gõ địa chỉ:http://192.168.239.131/info.php, nếu kết quả hiển thị như hình dưới là việc cài đặt của chúng ta đã thành công

![image](https://user-images.githubusercontent.com/110179869/189571941-8bbf26cc-e16b-4813-b37f-733d17781194.png)


