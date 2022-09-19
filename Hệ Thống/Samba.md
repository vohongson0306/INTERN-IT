# 1.Cài đặt Samba Server
`yum update -y`

![image](https://user-images.githubusercontent.com/110179869/190939602-02ba395a-9e21-41ea-8b5c-7cb67e473d63.png)

![image](https://user-images.githubusercontent.com/110179869/190939609-0e588c9e-eb15-4395-92cc-122dc8954a92.png)

`yum install samba -y`

![image](https://user-images.githubusercontent.com/110179869/190939654-b35a3b1d-5847-4061-9ab3-5d1261c04746.png)

![image](https://user-images.githubusercontent.com/110179869/190939668-1e55b7fc-86c7-409c-8400-4b1c6bb7fd3f.png)

`systemctl enable smb.service`

![image](https://user-images.githubusercontent.com/110179869/190939759-96f0e88c-4847-4db8-98da-bcbba5d5aa6c.png)

`systemctl enable nmb.service`

![image](https://user-images.githubusercontent.com/110179869/190939795-68825a4a-7a27-4e10-b525-4018944f4f42.png)

`systemctl restart smb.service`

![image](https://user-images.githubusercontent.com/110179869/190939840-c9f6b419-ab70-431a-bef1-7d3455813211.png)

`systemctl restart nmb.service`

![image](https://user-images.githubusercontent.com/110179869/190939860-9e73331c-80aa-4ea0-a769-faf0f9c763cf.png)

## CentOS 7 có thể cần mở firewall cho Samba
```sh
firewall-cmd --permanent --zone=public --add-service=samba
firewall-cmd --reload
```

![image](https://user-images.githubusercontent.com/110179869/190941661-fbe0d6e5-06bb-4966-9ec7-790cd872c2fd.png)

# 2.Chia sẻ một thư mục public
`mv /etc/samba/smb.conf /etc/samba/smb.conf.bak`     # Sao lưu

![image](https://user-images.githubusercontent.com/110179869/190940342-ba800ff8-ba66-400d-ab22-61c80f3078d5.png)

`vi /etc/samba/smb.conf`  

![image](https://user-images.githubusercontent.com/110179869/190940371-a61cf5b4-6585-4701-8733-5c3881ea658e.png)

![image](https://user-images.githubusercontent.com/110179869/190941881-b27030e8-abba-44a9-8e42-5f76fa0f088d.png)

## Nhập vào nội dung sau:

```sh
[global]
workgroup = WORKGROUP
server string = My Samba Server
netbios name = centos
security = user
map to guest = bad user
dns proxy = no

#=== BAT DAU THIET LAP CHIA SE FILE
[PublicShare]
path = /samba/publicshare
browsable = yes
writable = yes
guest ok = yes
read only = no 
```

![image](https://user-images.githubusercontent.com/110179869/190941193-860aff36-dac6-4c49-8fd9-c5a1b04caca3.png)

`mkdir -p /samba/PublicShare/`

![image](https://user-images.githubusercontent.com/110179869/190940527-4296358f-05e3-4638-aaaa-f4a18a5127af.png)

## Phân quyền thư mục:
`chmod -R 0755 /samba/PublicShare/`

![image](https://user-images.githubusercontent.com/110179869/190940571-d4fded62-2a3b-49d2-8779-6897d8dab119.png)

`chown -R nobody:nobody /samba/publicshare/`

![image](https://user-images.githubusercontent.com/110179869/190940637-a5a55233-9be9-43f9-89b6-edf879aac835.png)

## khởi động lại Samba
`systemctl restart smb.service`

`systemctl restart nmb.service`

![image](https://user-images.githubusercontent.com/110179869/190940749-2612a0de-f6b4-4e93-ba9e-71c390e1a2e7.png)

# Kết nối từ Windows đến Samba Server
![image](https://user-images.githubusercontent.com/110179869/190940785-699fb34c-7971-45f1-9cd8-268bb2d7c917.png)

![image](https://user-images.githubusercontent.com/110179869/190940865-e236485b-39bf-4e03-ae45-d6a4583c6258.png)

![image](https://user-images.githubusercontent.com/110179869/190942144-b0fc37fc-fb83-4525-a420-b8bbc4687a3b.png)

![image](https://user-images.githubusercontent.com/110179869/190942167-9a6d1ab5-b5f5-4168-809f-8b18a74ef8de.png)
