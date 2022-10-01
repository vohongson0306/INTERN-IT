# Bước 1: chuẩn bị trước khi cài đặt.
- Tải app nhân hòa, đăng ký tài khoản, mua 1 domain.
- Sau đó bạn muốn tạo một email server yêu cầu bạn cần có một VPS có IP public và một domain name. Các bạn có thể đăng kí các dịch vụ tại Nhân Hòa

![image](https://user-images.githubusercontent.com/110179869/192719766-399dc954-281c-4711-858b-a23097bdf51d.png)

- Domain name:xn--vhongson-e4a.vn
- truy cập vào https://zonedns.vn để thiết lập các bản ghi DNS cần thiết.

![image](https://user-images.githubusercontent.com/110179869/193379335-c014d1fe-a077-4e48-9c91-31b7498d6b31.png)

![image](https://user-images.githubusercontent.com/110179869/193396436-756ca028-1fcf-45c9-99aa-8ca3572a4a38.png)

# Bước 2: Chuẩn bị môi trường trên máy chủ mail
- Tắt SELinux
```
sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config && setenforce 0
```
- Update
```
yum update -y
```
- Postfix là một phầm mềm nguồn mở được dùng để gửi mail (Mail Transfer Agent-MTA). Được phát hành bởi IBM với mục tiêu thay thế trình gửi mail phổ biến là sendmail.
- Kiểm tra trạng thái của postfix:
```
systemctl status postfix
```
- Dừng dịch vụ postfix:
```
systemctl stop postfix
```
- Gỡ cài đặt postfix:
```
yum remove postfix -y
```
