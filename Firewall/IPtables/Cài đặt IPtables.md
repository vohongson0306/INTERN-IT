- Trên CentOS, mặc định sử dụng tường lửa là firewalld. Để cài đặt IPTABLES thì trước tiên phải tắt service firewalld:
```
systemctl stop firewalld
```

- Không cho phép firewalld tự bật khi reboot server:
```
systemctl disable firewalld
```
![image](https://user-images.githubusercontent.com/110179869/195234349-c678fd2b-548e-4553-973d-10a2dc85667b.png)

- Đảm bảo không cho các dịch vụ khác start firewalld:
```
systemctl mask --now firewalld
```
![image](https://user-images.githubusercontent.com/110179869/195234377-45248f89-35bd-4985-a004-bfd4c86b4cb1.png)

- Cài đặt packages iptables-services từ CentOS repositories:
```
yum install iptables-services
```
![image](https://user-images.githubusercontent.com/110179869/195234439-4d7ca109-e7c9-45cd-a5f3-0dff14546b8e.png)

- Khởi động dịch vụ iptables
```
systemctl start iptables
```

- Bật tự động iptables khi boot server, để đảm bảo server luôn luôn có sự bảo vệ từ iptables.
```
systemctl enable iptables
```
![image](https://user-images.githubusercontent.com/110179869/195234480-59a51445-f2e9-4269-8e42-e4b1de28e0f2.png)

- Kiểm tra trạng thái iptables đảm bảo nó đang hoạt động:
```
systemctl status iptables
```
![image](https://user-images.githubusercontent.com/110179869/195234561-59217faf-6157-4256-a5e1-5c064db6df10.png)

