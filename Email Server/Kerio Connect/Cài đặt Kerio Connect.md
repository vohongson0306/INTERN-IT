# Bước 0: Chuẩn bị
Cấu hình time-zone cho hệ thống
`ln -sf /usr/share/zoneinfo/Asia/Ho_Chi_Minh /etc/localtime`

![image](https://user-images.githubusercontent.com/110179869/192667227-7de203ab-4d80-43fa-aaa3-6242ff1d5e4e.png)

# Bước 1: Kiểm tra trạng thái Selinux và cập nhật hệ thống
- Tắt Selinux:
`sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config && setenforce 0`

![image](https://user-images.githubusercontent.com/110179869/192669995-f1cfdcb4-e3c6-4e17-802d-a403ccfe88ef.png)

- Cập nhật những thay đổi mới nhất:
`yum -y update`

![image](https://user-images.githubusercontent.com/110179869/192670134-23a326a4-24ca-410f-aa9e-d877b4e898f6.png)

# Bước 2: Gỡ cài đặt postfix
Postfix là một phầm mềm nguồn mở được dùng để gửi mail (Mail Transfer Agent-MTA). Được phát hành bởi IBM với mục tiêu thay thế trình gửi mail phổ biến là sendmail.

- Kiểm tra trạng thái của postfix:
`systemctl status postfix`

![image](https://user-images.githubusercontent.com/110179869/192670488-015ed77d-4259-4e74-a560-b2bb924a4f17.png)

- Dừng dịch vụ postfix:
`systemctl stop postfix`

![image](https://user-images.githubusercontent.com/110179869/192670524-a329b01b-a6fc-4d8f-b281-8bfbd290b92b.png)

- Gỡ cài đặt postfix:
`yum remove postfix -y`

![image](https://user-images.githubusercontent.com/110179869/192670559-f1d0428b-ef0a-45d7-869a-39c9210df438.png)

- Reboot lại máy:
`reboot`

# Bước 3: Cài đặt Kerio Connect
- Tải file rpm Kerio Connect:
`wget http://cdn.kerio.com/dwn/connect/connect-9.2.9-4540/kerio-connect-9.2.9-4540-p1-linux-x86_64.rpm`

![image](https://user-images.githubusercontent.com/110179869/192670819-63db735c-967e-460b-8125-c69b381455e4.png)

- Cài đặt Kerio:
`rpm -i kerio-connect-9.2.9-4540-p1-linux-x86_64.rpm`

![image](https://user-images.githubusercontent.com/110179869/192672192-794fb7aa-459c-4a7d-9c45-be70e77fee6b.png)

- Kiểm tra trạng thái của dịch vụ Kerio:
`systemctl status kerio-connect`

![image](https://user-images.githubusercontent.com/110179869/192672379-f995be36-2d87-4faa-9e57-741282198759.png)

# Bước 4: Cấu hình firewalld
Nếu sử dụng Firewalld để có thể truy cập được website sẽ cần mở cổng (port) bằng các lệnh sau đây:
```
firewall-cmd --permanent --zone=public --add-service=http
firewall-cmd --permanent --zone=public --add-service=https
firewall-cmd --reload
```

# Bước 5: Đăng nhập Email Server trên trình duyệt
- Truy cập:
`https://IP-VPS:4040`

![image](https://user-images.githubusercontent.com/110179869/192672770-ebe79154-1143-4fd7-a91f-49a5ef708e38.png)

- Chọn Next, sau đó chọn I accept the terms in the License Agreement. Chọn Next.

![image](https://user-images.githubusercontent.com/110179869/192672927-4932601e-71c0-4de6-9275-33945292b5ce.png)

- Nhập Internet hostname và Email domain.
- 
![image](https://user-images.githubusercontent.com/110179869/192673159-078e2f42-f3e6-4d01-a987-b2af7e45620d.png)

- Nhập mật khẩu (Son0981241001)

![image](https://user-images.githubusercontent.com/110179869/192673298-4e526897-3a3b-4ce0-903e-6d84175c9811.png)


- Nhấn Next

![image](https://user-images.githubusercontent.com/110179869/192673337-e9e0107c-3bd6-4eaa-9fca-f6b137161907.png)

- Chọn thư mục lưu trữ mail

![image](https://user-images.githubusercontent.com/110179869/192673379-65885b26-8b8b-4f47-a7a4-6553c046f87c.png)


- Chọn mua bản quyền hoặc dùng thử 30 ngày.

![image](https://user-images.githubusercontent.com/110179869/192673418-8c795ae1-8484-4383-9af5-0d2366af06af.png)


- KEY BẢN QUYỀN: 10512-1XWX7-44R91

![image](https://user-images.githubusercontent.com/110179869/192673474-0c80b33f-a77e-4094-a15c-9d06d60e73bf.png)

![image](https://user-images.githubusercontent.com/110179869/192673529-76714b0b-5dfb-4d50-a035-ffc67ddc9b12.png)

![image](https://user-images.githubusercontent.com/110179869/192673562-a49f7aa2-3f0d-450a-ac71-34dc13f8ba59.png)

- Nhấn Finish để hoàn tất.

![image](https://user-images.githubusercontent.com/110179869/192673598-c21573a7-d9bb-4861-b523-b4c03d2b0ce8.png)

- Chờ hệ thống tự khởi động lại

![image](https://user-images.githubusercontent.com/110179869/192673626-78b7c1c5-c28e-412c-b0ca-883e548e2fa6.png)

- Đăng nhập vào trang quản trị

![image](https://user-images.githubusercontent.com/110179869/192673720-3f052621-0f9e-41dd-8576-8f5938223f8f.png)

![image](https://user-images.githubusercontent.com/110179869/192674030-c519d6ce-93fb-425d-9bf1-e438c20bedd0.png)

![image](https://user-images.githubusercontent.com/110179869/192674140-81ef714a-0168-44dd-a804-c0d2710be4e2.png)








