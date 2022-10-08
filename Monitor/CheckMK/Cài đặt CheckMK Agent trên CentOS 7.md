# Bước 1: Lấy link tải
Đăng nhập `Checkmk Server` -> Vào `Setup` -> `Agent` -> `Linux.`

![image](https://user-images.githubusercontent.com/110179869/194687513-589826b0-ffe0-4706-9dc2-16bdff3b5bcd.png)

Ở đây có 2 link:

*.deb dùng cho các host sử dụng `debian.`
*.rpm dùng cho các host sử dụng `RHEL.`
Với client chạy hệ điều hành CentOS7 ta chọn `*.rpm`, copy đường link cài đặt.

![image](https://user-images.githubusercontent.com/110179869/194687560-ccbd4fcb-9646-4ad1-bfbf-acd0a737ee8d.png)

# Bước 2: Tải file cài đặt về máy client
```
yum install wget -y
wget http://192.168.239.150/hongson/check_mk/agents/check-mk-agent-2.1.0p13-1.noarch.rpm
```
![image](https://user-images.githubusercontent.com/110179869/194687592-1b03dc36-0bdd-4673-a572-5b7c460f7b7b.png)

# Bước 3: Cài đặt xinetd
```
yum install xinetd -y
```
![image](https://user-images.githubusercontent.com/110179869/194687606-7b686e18-f8f8-4fe9-b87d-0459d6942941.png)

Khởi động lại dịch vụ xinetd và cho phép khởi động cùng hệ thống:
```
systemctl start xinetd
systemctl enable xinetd
```
![image](https://user-images.githubusercontent.com/110179869/194687641-0beadca8-bc4b-4b4f-aae9-67f843b91784.png)

# Bước 4: Cài đặt agent
```
rpm -ivh check-mk-agent-2.1.0p13-1.noarch.rpm
```
![image](https://user-images.githubusercontent.com/110179869/194687660-0bdd40f6-74ab-47ea-ad48-260f1da39ee9.png)

# Bước 5: Cấu hình xinetd của checkmk
```
nano /etc/xinetd.d/check-mk-agent
```
- port: 6556

![image](https://user-images.githubusercontent.com/110179869/194687734-723383d4-28e5-498b-8198-65309226c6cc.png)

- only_from: Thêm địa chỉ IP server OMD của bạn

- disable: no (Có nghĩa cho phép dịch vụ chạy)

![image](https://user-images.githubusercontent.com/110179869/194687804-69dfc85b-7020-43dc-b593-6c7edac03b91.png)

# Bước 6: Khởi động lại xinetd
```
systemctl restart xinetd
```

# Bước 7: Cấu hình firewalld
```
firewall-cmd --add-port=6556/tcp --permanent
firewall-cmd --reload
```
![image](https://user-images.githubusercontent.com/110179869/194687830-502094e6-5891-4776-a119-945a09fa6a7c.png)

# Bước 8: Thêm host trên Checkmk Server
Vào `Setup` -> `Host` ->` Add host`-> Nhập thông tin: Hostname, IP, các cấu hình phù hợp -> `Save & go to service configuration.`

![image](https://user-images.githubusercontent.com/110179869/194688026-1b83e744-f3ba-4a71-9e25-db1320e5dee5.png)

![image](https://user-images.githubusercontent.com/110179869/194688053-4536a8a7-6612-4efc-a3bd-df8a0d17ccc5.png)

![image](https://user-images.githubusercontent.com/110179869/194688133-888ffc74-23ae-44be-b4ab-986193531e8f.png)

Kết quả:

![image](https://user-images.githubusercontent.com/110179869/194688182-197a3ca0-ec52-4bf1-ad7a-dad91ec185e0.png)
