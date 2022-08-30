# Các bước cài đặt centos 7 trên VMware.
## Chuẩn bị:
+ Cài đặt VMware workstation Pro 
+ Souce ios centos 7 ( www.centos.org/download/)
+ Cấu hình tối thiểu : Ổ cứng : 40 GB , RAM : 1G
+ Cấu hình khuyến cáo : Ổ cứng : 100GB , RAM : 8GB đối với 64bit.
## Cài đặt 
### Bước 1: Khởi động máy ảo VMware > File > New Virtual Machine.
![image](https://user-images.githubusercontent.com/110179869/187343761-741f37d3-f091-44a1-a5eb-e4aa3e4204fd.png)

### Bước 2: Chọn Custom > Next.
![image](https://user-images.githubusercontent.com/110179869/187343831-a7fb8afc-4b87-496a-9454-50442f100ad1.png)

### Bước 3:  check vào ô I will install the operating system later. > Next
![image](https://user-images.githubusercontent.com/110179869/187344034-d3ce777b-42e0-4b71-8443-4fdda02a9f3e.png)

### Bước 4:  Chọn Linux > Version: Centos 7 64-bit (ở đây, máy của mình là 64bit nên mình sẽ chọn là centos 7 64-bit)
![image](https://user-images.githubusercontent.com/110179869/187344020-c7e2c411-d02f-4ca1-aed3-53e1aff188ce.png)

### Bước 5:  Đặt tên và chọn nơi lưu file (đây là file đĩa ảo, file này khá nặng nên lưu ở ổ đĩa nào còn trống nhiều dung lượng để tránh gặp lỗi khi cài đặt).
![image](https://user-images.githubusercontent.com/110179869/187344158-4af1af2d-9de0-40dc-9243-af8472818c47.png)

### Bước 6: Chọn tốc độ xử lý của máy ảo.
![image](https://user-images.githubusercontent.com/110179869/187344201-5e16f279-6d9a-4647-8220-2b011a871729.png)

### Bước 7: Chọn RAM, nếu ram bạn nhiều thì có thể để lên cao hơn nữa.
![image](https://user-images.githubusercontent.com/110179869/187344237-a409834c-f3dd-4a3d-9008-b8d971801bb5.png)

### Bước 8: Thiết lập card mạng cho máy ảo ( bạn có thể chọn card nat hoặc bried)
![image](https://user-images.githubusercontent.com/110179869/187344318-2b88c742-7735-430f-9811-f3b115c54ac3.png)

### Bước 9:  Thiết lập chế độ nhập xuất
![image](https://user-images.githubusercontent.com/110179869/187344363-9c577be2-073e-4e63-94e3-8bc8ce14f91a.png)

### Bước 10: tiếp click Next
![image](https://user-images.githubusercontent.com/110179869/187344405-2b4e634b-9950-4bdd-aba0-058792f1f00d.png)

### Bước 11:  Tạo một ổ đĩa ảo mới. Chọn Create a new virtual disk > Next
![image](https://user-images.githubusercontent.com/110179869/187344468-1af3c8f6-c40d-49fd-9842-147f66b4905b.png)

### Bước 12: Chọn dung lượng cho ổ đĩa đó, mình để mặc định là 40GB. NHỚ CHỌN Store virtual disk as a single file
![image](https://user-images.githubusercontent.com/110179869/187344513-65f99315-b881-40b7-979e-54c0d28c0133.png)

### Bước 13: Chọn đường dẫn lưu file ổ đĩa ảo, sau này có thể copy và chuyển qua máy tính khác mã vẫn dùng được máy ảo.
![image](https://user-images.githubusercontent.com/110179869/187344850-b40eed6b-7774-4b5f-a41e-7d58c6320811.png)

### Bước 14: Chọn Customize Hardware để kiếm tra lại các thiếp lập.
![image](https://user-images.githubusercontent.com/110179869/187344894-61f384bd-405c-407f-815b-e8e4cf8218f7.png)

### Bước 15:  New CD/DVD  (IDE) > Use ISO image file và chọn đến đường dẫn file ISO centos 7 đã tải về ở trên. Sau đó ấn Close.
![image](https://user-images.githubusercontent.com/110179869/187344963-d6a927d3-d3b1-4ed6-8a16-74b574fe9c92.png)

### Bước 16: Chọn Finish
![image](https://user-images.githubusercontent.com/110179869/187344986-03c32108-2078-46a0-8a0b-72d6c5346441.png)

### Bước 17: Khởi động centos bằng Power on this virtual machine
![image](https://user-images.githubusercontent.com/110179869/187345011-be2d5f2b-8be1-4b1a-8652-b57322720af6.png)

### Bước 18: Chọn Install centos 7
![image](https://user-images.githubusercontent.com/110179869/187345085-35c1cf8f-2ce9-48c4-b898-cac296967bc0.png)

### Bước 19: Thiết lập ngôn ngữ > Continue (english khuyến cáo).
![image](https://user-images.githubusercontent.com/110179869/187345153-55c9af05-27a9-471a-9e5b-8d89d5e766d7.png)

### Bước 20: Thiết lập ngày, giờ. DATE & TIME > Done (set giờ việt nam nhé, cứ trỏ chuột vào bản đồ việt nam)
![image](https://user-images.githubusercontent.com/110179869/187345307-122e05f1-2eb3-422b-a1b3-15031f5980e4.png)

### Bước 21: Ở mục SOFTWATE SELECTION, chọn giao diện đồ hoạ (GUI) để dễ dàng thao tác:
-Server with GUI > KDE > Done
![image](https://user-images.githubusercontent.com/110179869/187345452-17a44dea-9eca-486d-9eef-6d4324babd9b.png)

### Bước 22: Mục INSTALLATION DESTINATION, chọn ổ đĩa ảo 40GB mình đã tạo lúc nãy > Done
![image](https://user-images.githubusercontent.com/110179869/187345516-a6407aa0-9e42-460f-b7da-d6d3a1ad01ba.png)

### Bước 23: Mục NETWORK & HOST NAME, chọn ON > Done
![image](https://user-images.githubusercontent.com/110179869/187345581-cd01d481-4481-4d9c-a5dd-c04feb816442.png)

### Bước 24: Chọn Begin Installation
![image](https://user-images.githubusercontent.com/110179869/187345654-7949f28c-6763-4151-b642-f98f4d806eb8.png)

### Bước 25: Thiết lập tài khoản ROOT, tài khoản này rất quan trọng nên cần phải ghi nhớ mật khẩu
![image](https://user-images.githubusercontent.com/110179869/187345883-f045dd04-69ed-4b80-a022-669346c2bbc6.png)

### Bước 26:  Chờ máy tự động cài đặt, bạn chờ khoảng 3 đến 5 phút tuỳ vào cấu hình của máy tính. Click Reboot
![image](https://user-images.githubusercontent.com/110179869/187346042-ec60cf76-4f72-411b-bf77-1e40687e0146.png)

![image](https://user-images.githubusercontent.com/110179869/187347416-f3cb0ba9-2f57-42c0-a4f4-375277061e69.png)

### Bước 27: Tick chọn I accept the license agreement
![image](https://user-images.githubusercontent.com/110179869/187347554-828b32d9-468f-4ab5-866b-cb7588bb0b25.png)

### Bước 28: Tạo tài khoản mới để đăng nhập vào hệ thống.
![image](https://user-images.githubusercontent.com/110179869/187347896-2075af5a-35b4-4ca5-bfb8-7dcc2498dd3f.png)


### Bước 29: Set mật khẩu cho tài khoản của bạn vừa tạo lúc nãy. LƯU Ý 2 MẬT KHẨU ROOT VÀ USER KHÁC NHAU
![image](https://user-images.githubusercontent.com/110179869/187348351-641ec829-d156-4604-b960-610f253eecad.png)

![image](https://user-images.githubusercontent.com/110179869/187348396-7bbd1a68-fe26-4a51-9c2e-883e932535dc.png)

![image](https://user-images.githubusercontent.com/110179869/187348569-1c09a5bd-bd57-4e34-9483-b7555cc62b71.png)

### Bước 30: Giờ ta đã có thể chạy được Centos trên máy ảo VMware.
![image](https://user-images.githubusercontent.com/110179869/187348585-2096e428-a17f-4685-b024-0812d3964b5d.png)

![image](https://user-images.githubusercontent.com/110179869/187348630-3023bbcf-4d04-49c9-96b2-1a6eac36343f.png)
