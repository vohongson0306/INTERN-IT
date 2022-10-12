# Một số nguyên tắc áp dụng trong Iptables
- Đầu tiên cần xác định các service muốn đóng/mở và các port tương ứng. Ví dụ:
  - Để truy cập VPS bằng SSH, cần mở port SSH - 22
  - Truy cập Website, cần mở port HTTP - 80 và HTTPS - 443
  - Để gửi mail, cần mở port SMTP - 22 và SMTPS - 465/587
  - Để người dùng nhạn được mail, cần mở port POP3 -110, POP3S - 995, IMAP - 143 và IMAPS - 993.
  - Sau khi đã xác định được các port cần mờ, cần thiết lập các qui tắt tường lửa tương ứng để cho phép.
- Xem các rules hiện tại:
```
  iptables -L
```
![image](https://user-images.githubusercontent.com/110179869/195234936-9b4bd2fb-7651-4458-a27e-d660547afccf.png)

- Clear đi rules cũ dùng :
```
  iptables -F
```
![image](https://user-images.githubusercontent.com/110179869/195235023-fbfcda82-825c-4c52-b9e0-4d7c12807f70.png)

- Thông tin về các cột :
  - Cột 1 target: Hành động sẽ được áp dụng cho mỗi qui tắc, gồm:
    - Accept : gói dữ liệu được chuyển tiếp để xử lí tại ứng dụng cuối hoặc hệ điều hành
    - Drop: gói dữ liệu bị chặn, loại bỏ
    - Reject: gói dữ liệu bị chặn, loại bỏ đồng thời gửi một thông báo lỗi tới người gửi
  - Cột 2: PROT (protocol – giao thức) quy định các giao thức sẽ được áp dụng để thực thi quy tắc, bao gồm all, TCP hay UDP. Các ứng dụng SSH, FTP, sFTP… đều sử dụng giao thức TCP.
  - Cột 4, 5: SOURCE và DESTINATION địa chỉ của lượt truy cập được phép áp dụng quy tắc
# Các sử dụng iptables để mở port cho VPS
- Để mở port trong iptables, cần chèn chuỗi ACCEPT PORT. Cấu trúc lệnh để mở port xxx như sau:
  - iptables -A INPUT -p tcp -m tcp --dport xxx -j ACCEPT
  - iptables -I INPUT -p tcp -m tcp --dport xxx -j ACCEPT
- A tức Append – chèn vào chuỗi INPUT (chèn xuống cuối)
- I tức Insert - chèn vào chuỗi INPUT (chèn vào dòng chỉ định rulenum)
- Để tránh xung đột với rule gốc, các bạn nên chèn rule vào đầu, sử dụng -I
# Mở port SSH
- Để truy cập VPS qua SSH, bạn cần mở port SSH 22:
```
iptables -I INPUT -p tcp -m tcp --dport 22 -j ACCEPT
```
![image](https://user-images.githubusercontent.com/110179869/195235481-843d6345-8a5a-4367-bdd8-825bad1de975.png)

- Có thể cho phép kết nối VPS qua SSH duy nhất từ 1 ip bằng lệnh:
```
iptables -I INPUT -p tcp -s 192.168.44.161 -m tcp --dport 22 -j ACCEPT
```
![image](https://user-images.githubusercontent.com/110179869/195235751-eb8ddeee-38ef-4a94-aaad-745e141720a9.png)

- Mở port Webserver
```
iptables -I INPUT -p tcp -m tcp --dport 80 -j ACCEPT
iptables -I INPUT -p tcp -m tcp --dport 443 -j ACCEPT
```
![image](https://user-images.githubusercontent.com/110179869/195235968-e0cea822-8b57-4686-a0c9-edfbe7969f1b.png)

- Mở port Mail
  - SMTP
```
iptables -I INPUT -p tcp -m tcp --dport 25 -j ACCEPT
iptables -I INPUT -p tcp -m tcp --dport 465 -j ACCEPT
```
  - POP3
```
iptables -A INPUT -p tcp -m tcp --dport 110 -j ACCEPT
iptables -A INPUT -p tcp -m tcp --dport 995 -j ACCEPT
```
   - IMAP
```
iptables -A INPUT -p tcp -m tcp --dport 143 -j ACCEPT
iptables -A INPUT -p tcp -m tcp --dport 993 -j ACCEPT
```
![image](https://user-images.githubusercontent.com/110179869/195236160-e2977e40-77d7-4b3e-bbe7-36089615461b.png)

![image](https://user-images.githubusercontent.com/110179869/195236235-fd0d9f3b-2d38-47f8-b022-7ab3cb7d6eb3.png)

# Chặn 1 IP truy cập
```
iptables -A INPUT -s IP_ADDRESS -j DROP
```
- Chặn 1 IP truy cập 1 port cụ thể:
```
iptables -A INPUT -p tcp -s IP_ADDRESS –dport PORT -j DROP
```
# Bước cuối :
- Sau khi đã thiết lập đầy đủ, bao gồm mở các port cần thiết hay hạn chế các kết nối, cần block toàn bộ các kết nối còn lại và cho phép toàn bộ các kết nối ra ngoài từ VPS.
```
iptables -P OUTPUT ACCEPT
iptables -P INPUT DROP
```
- Load lại:
```
Service reload iptables
```
# Các remove 1 rule
- Đầu tiên cần tìm dòng của rule đấy:
```
iptables -L INPUT --line-numbers
```
![image](https://user-images.githubusercontent.com/110179869/195236642-07a55504-c3f2-4ca8-8373-835397022382.png)

- Xóa theo dòng:
```
sudo iptables -D INPUT 5
```
![image](https://user-images.githubusercontent.com/110179869/195236768-82ad4ae3-d441-492c-af87-7736565901b9.png)




