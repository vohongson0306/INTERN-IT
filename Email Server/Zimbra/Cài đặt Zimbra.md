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

- Kiểm tra xem có dịch vụ nào đang sử dụng port mà Zimbra sử dụng hay không.
```
yum -y install net-tools
```
- Cài đặt netstat.
```
netstat -tulpn | grep -E -w '25|80|110|143|443|465|587|993|995|5222|5223|9071|7071'
```

Nếu có service nào đang chạy trên các port trên thì tìm cách tắt đi hoặc thay thế, nếu chưa có thì thực hiện cài đặt.
```
yum install bind-utils
```
Kiểm tra lại bản ghi
```
dig -t A mail.xn--vhongson-e4a.vn

dig -t MX xn--vhongson-e4a.vn
```
# Bước 3: Cài đặt Zimbra
- Cài đặt các gói cần thiết
```
yum install unzip net-tools sysstat openssh-clients perl-core libaio nmap-ncat libstdc++.so.6 wget -y
```

- Cài đặt wget
```
yum install wget -y
```
- Tải và giải nén Zimbra
```
mkdir zimbra && cd zimbra
```

```
wget https://files.zimbra.com/downloads/8.8.10_GA/zcs-8.8.10_GA_3039.RHEL7_64.20180928094617.tgz --no-check-certificate
```

- Cài đặt Zimbra
```
tar zxpvf zcs-8.8.10_GA_3039.RHEL7_64.20180928094617.tgz

cd zcs-8.8.10_GA_3039.RHEL7_64.20180928094617 

./install.sh
```
- Nhấn `Y` để tải xuống các gói liên quan đến Zimbra.

- Nhấn `Y`, create lại tên domain.

- Chọn `7` sau đó chọn `4` để thiết lập tài khoản admin. (Nso01_8HMj)

- Chọn `r` để xem lại cài đặt, chọn `a` để áp dụng thay đổi.

- Sau khi cài đặt xong khởi động lại dịch vụ zimbar bằng lệnh:
`su zimbra`

`zmcontrol restart`
- Mở firewalld
```
firewall-cmd --permanent --add-port={25,80,110,143,443,465,587,993,995,5222,5223,9071,7071}/tcp

firewall-cmd --reload
```
