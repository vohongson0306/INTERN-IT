# Bước 1: chuẩn bị trước khi cài đặt.
- Tải app nhân hòa, đăng ký tài khoản, mua 1 domain.
- Sau đó bạn muốn tạo một email server yêu cầu bạn cần có một VPS có IP public và một domain name. Các bạn có thể đăng kí các dịch vụ tại Nhân Hòa

![image](https://user-images.githubusercontent.com/110179869/192719766-399dc954-281c-4711-858b-a23097bdf51d.png)

- Domain name:xn--vhongson-e4a.vn
- truy cập vào https://zonedns.vn để thiết lập các bản ghi DNS cần thiết.

![image](https://user-images.githubusercontent.com/110179869/193379335-c014d1fe-a077-4e48-9c91-31b7498d6b31.png)

![image](https://user-images.githubusercontent.com/110179869/193397083-653fa400-89c9-43cb-9787-16b1fd411ae4.png)

# Bước 2: Chuẩn bị môi trường trên máy chủ mail
- Tắt SELinux
```
sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config && setenforce 0
```
- Update
```
yum update -y
```
![image](https://user-images.githubusercontent.com/110179869/193397426-b2ca4866-480c-43ef-bdb4-0ef5b1323a71.png)

- Postfix là một phầm mềm nguồn mở được dùng để gửi mail (Mail Transfer Agent-MTA). Được phát hành bởi IBM với mục tiêu thay thế trình gửi mail phổ biến là sendmail.
- Kiểm tra trạng thái của postfix:
```
systemctl status postfix
```
![image](https://user-images.githubusercontent.com/110179869/193397439-7b36ffc2-663b-4ed0-9674-20fb66233af9.png)

- Dừng dịch vụ postfix:
```
systemctl stop postfix
```
- Gỡ cài đặt postfix:
```
yum remove postfix -y
```
![image](https://user-images.githubusercontent.com/110179869/193397453-8a26ff6d-635a-47bb-b393-fb0f81a8a3c9.png)

- Reboot lại máy:
```
reboot
```
- Sửa hostname
```
hostnamectl set-hostname "xn--vhongson-e4a.vn"
exec bash
```
- Sửa file `/etc/hosts`
```
nano /etc/hosts
```
![image](https://user-images.githubusercontent.com/110179869/193397544-539d2f1b-452f-4238-8aa0-6e6be4cb8990.png)

- Kiểm tra xem có dịch vụ nào đang sử dụng port mà Zimbra sử dụng hay không.
```
yum -y install net-tools
```
![image](https://user-images.githubusercontent.com/110179869/193397567-fece718c-578d-410b-90a2-f4f348b321d0.png)

- Cài đặt netstat.
```
netstat -tulpn | grep -E -w '25|80|110|143|443|465|587|993|995|5222|5223|9071|7071'
```
![image](https://user-images.githubusercontent.com/110179869/193397581-225da965-84bb-4d78-b6d4-096aa093b63f.png)

Nếu có service nào đang chạy trên các port trên thì tìm cách tắt đi hoặc thay thế, nếu chưa có thì thực hiện cài đặt.
```
yum install bind-utils
```
![image](https://user-images.githubusercontent.com/110179869/193397597-f788bc98-6557-4684-9175-70491e644784.png)

Kiểm tra lại bản ghi
```
dig -t A mail.xn--vhongson-e4a.vn
```
![image](https://user-images.githubusercontent.com/110179869/193397713-b752dc46-da7b-47d7-9a52-99dd4af08607.png)
```
dig -t MX xn--vhongson-e4a.vn
```
![image](https://user-images.githubusercontent.com/110179869/193397727-fe0767ce-f2c5-47ea-9fc4-b0d2cbba9247.png)

# Bước 3: Cài đặt Zimbra
- Cài đặt các gói cần thiết
```
yum install unzip net-tools sysstat openssh-clients perl-core libaio nmap-ncat libstdc++.so.6 wget -y
```
![image](https://user-images.githubusercontent.com/110179869/193397982-56c6a7f2-3776-470b-8000-ed7d6d1e3aab.png)

- Cài đặt wget
```
yum install wget -y
```
![image](https://user-images.githubusercontent.com/110179869/193397994-72b3794c-7b13-4ec9-80db-c15359b013fc.png)

- Tải và giải nén Zimbra
```
mkdir zimbra && cd zimbra
```
![image](https://user-images.githubusercontent.com/110179869/193398008-3b0137c6-5f34-49a1-939d-3be6734f5852.png)
```
wget https://files.zimbra.com/downloads/8.8.10_GA/zcs-8.8.10_GA_3039.RHEL7_64.20180928094617.tgz --no-check-certificate
```
![image](https://user-images.githubusercontent.com/110179869/193398037-5f3e0fc5-e72f-4353-8a7e-aa1b002248d3.png)

- Cài đặt Zimbra
```
tar zxpvf zcs-8.8.10_GA_3039.RHEL7_64.20180928094617.tgz
```
![image](https://user-images.githubusercontent.com/110179869/193398052-cfa5218c-8436-418f-b192-0b95ddc92ad3.png)
```
cd zcs-8.8.10_GA_3039.RHEL7_64.20180928094617 
```
![image](https://user-images.githubusercontent.com/110179869/193398067-1f020488-7d91-43cf-bdd5-a4529eeae617.png)
```
./install.sh
```
- Nhấn `Y` để tải xuống các gói liên quan đến Zimbra.

- Nhấn `Y`, create lại tên domain.

- Chọn `7` sau đó chọn `4` để thiết lập tài khoản admin. 

![image](https://user-images.githubusercontent.com/110179869/193398346-6d3e0698-e5aa-43de-9eae-45a61ea2755a.png)

![image](https://user-images.githubusercontent.com/110179869/193398363-444e778b-6ee8-4f6d-997e-dfb433272474.png)

- Chọn `r` để xem lại cài đặt, chọn `a` để áp dụng thay đổi.

![image](https://user-images.githubusercontent.com/110179869/193398388-c221babc-0854-4d27-a83f-156195888741.png)

![image](https://user-images.githubusercontent.com/110179869/193398414-5a64800e-49e5-4969-80ab-748421c7f0fc.png)

![image](https://user-images.githubusercontent.com/110179869/193399017-979825c6-c331-4fa6-9254-8cbe649b9d04.png)

- Sau khi cài đặt xong khởi động lại dịch vụ zimbar bằng lệnh:
`su zimbra`

`zmcontrol restart`

![image](https://user-images.githubusercontent.com/110179869/193399103-4e4f893a-41f4-447a-bd69-4f54b7120aa7.png)

- Mở firewalld
```
firewall-cmd --permanent --add-port={25,80,110,143,443,465,587,993,995,5222,5223,9071,7071}/tcp

firewall-cmd --reload
```
![image](https://user-images.githubusercontent.com/110179869/193399212-a9acde2f-4306-4f50-af18-24ef08f92d2c.png)

# Bước 4: Thay đổi mật khẩu cho tài khoản admin
- Kiểm tra những quyền admin sử dụng
```
zmprov gaaa
```
![image](https://user-images.githubusercontent.com/110179869/193399284-1728d39b-87f1-492b-bb4f-a0063056dfa7.png)

- Thay đổi mật khẩu:
```
zmprov sp <admin email address> <new password>
```
![image](https://user-images.githubusercontent.com/110179869/193399356-85d404ee-4fc4-499f-b78a-b39977d06a64.png)

- Truy cập đường link sau để vào Zimbra:

https://mail.võhongson.vn:7071/zimbraAdmin/

![image](https://user-images.githubusercontent.com/110179869/193399492-f07e388d-73e3-46c7-a1c2-d7bb2b1e8465.png)

![image](https://user-images.githubusercontent.com/110179869/193399584-d1ba3b3b-fe23-48e8-99b1-c28e82b4e5c2.png)

![image](https://user-images.githubusercontent.com/110179869/193399881-0e16aad4-9776-470e-b417-c3b869aad892.png)

![image](https://user-images.githubusercontent.com/110179869/193402968-d4935441-0496-4812-979b-2bb4b0a6c9a4.png)
