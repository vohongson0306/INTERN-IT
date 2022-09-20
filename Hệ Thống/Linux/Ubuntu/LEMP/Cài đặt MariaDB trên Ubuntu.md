# Bước 1: Thiết lập kho lưu trữ
- thêm apt-keyi vào hệ thống của bạn bằng cách chạy các lệnh sau:
```
sudo apt install software-properties-common -y
sudo apt-key adv --fetch-keys 'https://mariadb.org/mariadb_release_signing_key.asc'
```

![image](https://user-images.githubusercontent.com/110179869/191154115-0e7e9e43-8233-444f-9404-63f1af1e1078.png)

Sau đó, tạo một tệp cấu hình apt trên hệ thống Ubuntu của bạn. Để tạo tệp sử dụng lệnh sau:

`sudo nano /etc/apt/sources.list.d/mariadb.list`

![image](https://user-images.githubusercontent.com/110179869/191154395-fedc136d-1ffa-4228-8846-072acbb956c9.png)

- Thêm nội dung dưới đây vào tập tin.
```
# MariaDB 10.4 Repository
deb [arch=amd64] http://nyc2.mirrors.digitalocean.com/mariadb/repo/10.4/ubuntu focal main
deb-src http://nyc2.mirrors.digitalocean.com/mariadb/repo/10.4/ubuntu focal main
```
# Bước 2: Cài đặt MariaDB trên Ubuntu

`sudo apt update`

![image](https://user-images.githubusercontent.com/110179869/191154581-c0e56740-d36b-445a-beec-974f27a4af71.png)

`sudo apt install mariadb-server -y`

![image](https://user-images.githubusercontent.com/110179869/191154671-13157b58-79c1-4f29-9699-e15c23e9902f.png)

# Bước 3: Bảo mật MariaDB
`sudo apt install mysql-server mysql-clients`
`sudo mysql_secure_installation`

![image](https://user-images.githubusercontent.com/110179869/191155695-21804165-1525-4e3e-b688-42fb04a57915.png)



