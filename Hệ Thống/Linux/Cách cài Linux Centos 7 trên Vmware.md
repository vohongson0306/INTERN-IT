# Các bước cài đặt centos 7 trên VMware.
## Chuẩn bị:
+ Cài đặt VMware workstation Pro 
+ Souce ios centos 7 ( www.centos.org/download/)
+ Cấu hình tối thiểu : Ổ cứng : 40 GB , RAM : 4G
+ Cấu hình khuyến cáo : Ổ cứng : 100GB , RAM : 8GB đối với 64bit.
## Cài đặt 
### Bước 1: Khởi động máy ảo VMware > File > New Virtual Machine.

### Bước 2: Chọn Custom > Next.

### Bước 3:  check vào ô I will install the operating system later. > Next

### Bước 4:  Chọn Linux > Version: Centos 7 64-bit (ở đây, máy của mình là 64bit nên mình sẽ chọn là centos 7 64-bit)

### Bước 5:  Đặt tên và chọn nơi lưu file (đây là file đĩa ảo, file này khá nặng nên lưu ở ổ đĩa nào còn trống nhiều dung lượng để tránh gặp lỗi khi cài đặt).

### Bước 6: Chọn tốc độ xử lý của máy ảo.

### Bước 7: Chọn RAM, nếu ram bạn nhiều thì có thể để lên cao hơn nữa.

### Bước 8: Thiết lập card mạng cho máy ảo ( bạn có thể chọn card nat hoặc bried)

### Bước 9:  Thiết lập chế độ nhập xuất

### Bước 10: tiếp click Next

### Bước 11:  Tạo một ổ đĩa ảo mới. Chọn Create a new virtual disk > Next

### Bước 12: Chọn dung lượng cho ổ đĩa đó, mình để mặc định là 40GB. NHỚ CHỌN Store virtual disk as a single file

### Bước 13: Chọn đường dẫn lưu file ổ đĩa ảo, sau này có thể copy và chuyển qua máy tính khác mã vẫn dùng được máy ảo.

### Bước 14: Chọn Customize Hardware để kiếm tra lại các thiếp lập.

### Bước 15:  New CD/DVD  (IDE) > Use ISO image file và chọn đến đường dẫn file ISO centos 7 đã tải về ở trên. Sau đó ấn Close.

### Bước 16: Chọn Finish

### Bước 17: Khởi động centos bằng Power on this virtual machine

### Bước 18: Chọn Install centos 7

### Bước 19: Thiết lập ngôn ngữ > Continue (english khuyến cáo).

### Bước 20: Thiết lập ngày, giờ. DATE & TIME > Done (set giờ việt nam nhé, cứ trỏ chuột vào bản đồ việt nam)

### Bước 21: Ở mục SOFTWATE SELECTION, chọn giao diện đồ hoạ (GUI) để dễ dàng thao tác:
-Server with GUI > KDE > Done

### Bước 22: Mục INSTALLATION DESTINATION, chọn ổ đĩa ảo 40GB mình đã tạo lúc nãy > Done

### Bước 23: Mục NETWORK & HOST NAME, chọn ON > Done

### Bước 24: Chọn Begin Installation

### Bước 25: Thiết lập tài khoản ROOT, tài khoản này rất quan trọng nên cần phải ghi nhớ mật khẩu

### Bước 26:  Chờ máy tự động cài đặt, bạn chờ khoảng 3 đến 5 phút tuỳ vào cấu hình của máy tính. Click Reboot

### Bước 27: Tick chọn I accept the license agreement

### Bước 28: Tạo tài khoản mới để đăng nhập vào hệ thống.

### Bước 29: Set mật khẩu cho tài khoản của bạn vừa tạo lúc nãy. LƯU Ý 2 MẬT KHẨU ROOT VÀ USER KHÁC NHAU

### Bước 30: Giờ ta đã có thể chạy được Centos trên máy ảo VMware.

