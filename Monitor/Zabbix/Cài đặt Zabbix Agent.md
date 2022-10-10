>> Yêu cầu hệ thống: Máy client chạy hệ điều hành CentOS7 đã cài đặt Apache, tắt SELinux.
# Bước 1: Cài đặt Zabbix repository
```
rpm -Uvh https://repo.zabbix.com/zabbix/5.0/rhel/7/x86_64/zabbix-release-5.0-1.el7.noarch.rpm
yum clean all
```
![image](https://user-images.githubusercontent.com/110179869/194795422-5976a585-8f5c-4066-aa63-c64721bc02da.png)

Bước 2: Cài đặt Zabbix-agent
```
yum install zabbix-agent -y
```
![image](https://user-images.githubusercontent.com/110179869/194795474-42a8ae62-0778-47a3-9857-cb370ba38e89.png)

# Bước 3: Cấu hình Zabbix agent
- Sửa file cấu hình:
```
nano /etc/zabbix/zabbix_agentd.conf
```

- Sửa theo các tham số sau:
```
Server=<IP_ZABBIX_SERVER>
ServerActive=<IP_ZABBIX_SERVER>
Hostname=<ZABBIX_SERVER_HOSTNAME>
```

![image](https://user-images.githubusercontent.com/110179869/194795804-2ae8c9b4-def6-4727-a3a4-f20224aabf48.png)

![image](https://user-images.githubusercontent.com/110179869/194795885-202c2ea6-a176-440a-914b-fb6d0f76c128.png)

![image](https://user-images.githubusercontent.com/110179869/194795967-e59c85ac-f5bb-42e9-920f-fb849d8800c4.png)

# Bước 4: Bước 4: Cấu hình firewalld
```
firewall-cmd --zone=public --add-port=10050/tcp --permanent
firewall-cmd --reload
```
![image](https://user-images.githubusercontent.com/110179869/194796060-1f2341c0-bf89-4162-9422-95adb604ec83.png)

# Bước 5: Khởi động lại dịch vụ
```
systemctl enable zabbix-agent
systemctl restart zabbix-agent
systemctl status zabbix-agent
```
![image](https://user-images.githubusercontent.com/110179869/194796100-c340e043-e919-4c93-9af5-142bdb3d0c08.png)

# Bước 6: Kiểm tra việc cài đặt
- Thực hiện trên Zabbix Server
- Cài đặt zabbix-get
```
yum install zabbix-get
```
![image](https://user-images.githubusercontent.com/110179869/194796190-9d4d5b67-b191-4b92-91bb-098aa26c8f16.png)

- Kiểm tra kết nối
```
zabbix_get -s <ZABBIX_AGENT_IP> -k agent.version
``` 
![image](https://user-images.githubusercontent.com/110179869/194796279-a0f7b36f-fed9-4865-a185-f7eec8a3fd3c.png)




