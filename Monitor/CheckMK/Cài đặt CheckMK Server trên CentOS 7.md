>> Truy cập link: https://checkmk.com/de/download để cập nhật phiên bản mới nhất.

# Bước 1: Tải và cài đặt các gói checkmk
```
yum install -y epel-release wget
```
![image](https://user-images.githubusercontent.com/110179869/194686927-8580ea2a-10eb-4f8b-b37d-af83efc4a1b5.png)

Tải file cài đặt:
```
wget https://download.checkmk.com/checkmk/2.1.0p13/check-mk-raw-2.1.0p13-el7-38.x86_64.rpm
```
![image](https://user-images.githubusercontent.com/110179869/194686945-2d4518fe-0fec-4727-8bbe-816730a64177.png)

Bước 2: Cài đặt checkmk
```
yum install -y check-mk-raw-2.1.0p13-el7-38.x86_64.rpm
```
![image](https://user-images.githubusercontent.com/110179869/194687127-24908d44-9867-4bdd-a179-9979983a86bb.png)

Bước 3: Tạo mới site
```
omd create hongson 
```
cmkadmin with password: SyY9iuGz

![image](https://user-images.githubusercontent.com/110179869/194687207-cef96946-a3ea-4fcb-8902-5c2d95773a11.png)

Cài mật khẩu cho site:
```
htpasswd -m /omd/sites/hongson/etc/htpasswd cmkadmin
```
![image](https://user-images.githubusercontent.com/110179869/194687244-3cf320de-5f35-4ba9-910d-25827c412263.png)

Khởi động site:
```
omd start hongson
```
![image](https://user-images.githubusercontent.com/110179869/194687256-eca0c97d-ac26-4ed0-a512-f73774e6fc22.png)

Bước 4: Truy cập checkmk server
Truy cập đường dẫn:
```
IP-VPS/hongson
```
![image](https://user-images.githubusercontent.com/110179869/194687273-8306b4e8-dcdd-41b2-a36e-9fb7a233a408.png)

Đăng nhập với tài khoản đã tạo.

![image](https://user-images.githubusercontent.com/110179869/194687293-17520d84-c249-4e75-a090-03b0d7c0036b.png)
