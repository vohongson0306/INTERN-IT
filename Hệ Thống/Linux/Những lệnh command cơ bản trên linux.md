# Lệnh liên quan đến hệ thống 
- exit: thoát khỏi cửa sổ dòng lệnh.
- logout: tương tự exit.
- reboot: khởi động lại hệ thống.
- halt: tắt máy.
- startx:khởi động chế độ xwindows từ cửa sổ terminal.
- mount: gắn hệ thống tập tin từ một thiết bị lưu trữ vào cây thư mục chính.
- unmount: ngược với lệnh mount.
# lệnh thao tác trên tập tin
- ls -lah: hiện các danh sách ẩn.

![image](https://user-images.githubusercontent.com/110179869/187813124-52f9b41d-8830-47fc-800c-0ccdbc3bf5df.png)

- ls: lấy danh sách tất cả các file và thư mục trong thư mục hiện hành.

![image](https://user-images.githubusercontent.com/110179869/187813202-7a2d0fc3-ad00-4349-bb23-54560410a3b9.png)

- pwd: xuất đường dẫn của thư mục làm việc.

![image](https://user-images.githubusercontent.com/110179869/187813258-d8deb9ae-69ec-4993-8da5-4b4125c5ceda.png)

- cd: thay đổi thư mục làm việc đến một thư mục mới.
- mkdir: tạo thư mục mới.

![image](https://user-images.githubusercontent.com/110179869/187813445-196527ed-2b35-4e14-a73a-21b0cc74290d.png)

- rmdir: xoá thư mục rỗng.

![image](https://user-images.githubusercontent.com/110179869/187813536-ccbd2cd0-84d7-46c1-a727-2cd94588adbb.png)

- cp:copy một hay nhiều tập tin đến thư mục mới.
- mv: đổi tên hay di chuyển tập tin, thư mục.
- rm: xoá tập tin.
- wc: đếm số dòng, số kí tự... trong tập tin.
- touch:tạo 1 tập tin.
- cat: xem nội dung tập tin.
- vi: khởi động trình soạn thảo văn bản vi.

![image](https://user-images.githubusercontent.com/110179869/187813804-36ec2988-2a81-466b-8f0c-471b7734d5a6.png)

- df: kiểm tra dung lượng đĩa.

![image](https://user-images.githubusercontent.com/110179869/187813733-9a11ea31-c863-480a-9360-411dd90390e0.png)

- du: xem dung lượng đĩa đã dùng cho một số tập tin nhất định.

![image](https://user-images.githubusercontent.com/110179869/187813707-6b0e3bae-ea66-437a-996f-11d9aaff625d.png)

- nano:khởi động trình soạn thảo văn bản nano.

![image](https://user-images.githubusercontent.com/110179869/187814186-54d24c4f-5f04-414f-8095-7ed5e48c0348.png)

- less:Xem tập tin theo dòng lệnh.

![image](https://user-images.githubusercontent.com/110179869/187814378-442c9582-eece-43bb-9380-28bd3b8be095.png)

- tail:xem nội dung tập tin( mặc định xem 10 dòng cuối, muốn xem 100 dòng cuối thì dùng lệnh sau : tail 100 tenfile)
- more: xem nội dung tập tin theo trang.
- head: xem nội dung tập tin (mặc định xem 10 dòng đầu, muốn xem 100 dòng đầu thì dùng lệnh sau : head 100 tenfile)
# lệnh khi làm việc trên terminal
- clear: xoá trắng cửa sổ dòng lệnh.
- date: xem ngày, giờ hệ thống.

![image](https://user-images.githubusercontent.com/110179869/188784370-386f86cf-3ca0-404e-9206-375785767ab1.png)


![image](https://user-images.githubusercontent.com/110179869/187814617-de7ff49f-6e0c-4cde-bc24-95b936301660.png)

- cal: xem lịch hệ thống.

![image](https://user-images.githubusercontent.com/110179869/188784127-b69bf49e-66a8-464b-944f-dc22bb050828.png)

# Lệnh quản lí hệ thống
- rpm: kiểm tra gói đã cài đặt hay chưa, hoặc cài đặt một gói, hoặc sử dụng để gỡ bỏ một gói
- ps: kiểm tra hệ thống tiến trình đang chạy.
![image](https://user-images.githubusercontent.com/110179869/188784242-4afd2492-6229-46eb-9787-2e0b57045136.png)

- kill: dừng tiến trình khi tiến trình bị treo. Chỉ có người dùng supper-user mới có thể dừng tất cả các tiến trình còn người dùng bình thường chỉ  có thể dừng tuieens trình mà mình tạo ra.
- top: hiển thị sự hoạt động của các tiến trình, đặc biệt là thông tin về tài nguyên hệ thống vè việc sử dụng các tài nguyên đó của từng tiến trình .

![image](https://user-images.githubusercontent.com/110179869/187814523-d46f93fb-816d-4a44-bf6c-4b20ab37fdc3.png)

- pstree: hiển thị tất cả các tiến trình dưới dạng cây.

![image](https://user-images.githubusercontent.com/110179869/187815654-622ef411-c95f-4356-99c3-e7b12a873d09.png)

- sleep: cho hệ thống dừng hoạt động trong 1 khoảng thời gian.
- useradd: tạo 1 người dùng mới. 
- groupadd: tạo 1 nhóm người dùng mới.
- passwd: thay đổi password cho người dùng .
- userdel:xoá người dùng đã tạo.
- groupdel: xoá nhóm người dùng đã tạo.
- gpasswd: thay đổi password của 1 nhóm người dùng.
- su: cho phép đăng nhập với tư cách của người dùng khác.
- groups: hiển thị nhóm của user hiện tại.
- who: cho biết ai đang đăng nhập hệ thống.

![image](https://user-images.githubusercontent.com/110179869/187814836-6d676078-34a4-42f9-a51f-a013c76fb03a.png)

- w:tương tự như lệnh who.

![image](https://user-images.githubusercontent.com/110179869/187814877-505966ca-6934-4e19-8537-5d4e170d29eb.png)

- man:xem hướng dẫn về dòng lệnh như cú pháp, các tham số.

![image](https://user-images.githubusercontent.com/110179869/187814915-bbc834a5-b283-41e1-9589-1c590cb63741.png)

# Các câu lệnh kiểm tra thông tin hệ thống ( system information)
| Lệnh Linux | Mô tả |
|----------------|------------|
| cat/proc/cpuinfo | Kiểm tra thông tin CPU(số core) |
| cat/proc/meminfo | Kiểm tra thông tin về RAM đang sử dụng |
| cat/porc/version | Kiểm tra phiên bản của Kernel Linux |
| cat/porc/ioports | Kiểm tra thông tin port I/O | 
| cat/ect/redhat-release | Kiểm tra phiên bản Centos |
| uname -a | Kiểm tra các thông tin về Kernel |
| free -m | Kiểm tra dung lượng RAM còn trống |
| init 0 | Tắt máy (tương đương lệnh shutdown -h now hoặc telinit 0) |
| df -h| Hiển thị thông tin những file hệ thống, nơi file được lưu hoặc tất cả những file mặc định. Lệnh này có thể xem được dung lượng ổ cứng đã sử dụng và còn trống. |
| du -sh| Kiểm tra dung lượng thư mục hiện tại |
| du  -ah| Hiển thị dung lượng của thư mục con và các file trong thư mục hiện tại |
| du -h -max-depth=1 | Hiển thị dung lượng các thư mục con ở cấp 1 (ngay trong thư mục hiện tại) |
| df | 	Kiểm tra dung lượng đĩa cứng, các phân vùng đĩa |
| lspci | Xem thông tin mainboard   /sbin/ifconfig Xem các địa chỉ IP của máy |
| hostname | Xem tên máy (hostname) |
| finger user@sever | Thu thập thông tin chi tiết về người dùng hiện đang dùng hệ thống |
|arch | 	Kiểm tra kiến trúc của máy (architech) |
|cat/proc/swaps | 	Kiểm tra thông tin SWAP của máy (tương tự như virtual RAM của Windows) |
| last reboot | 	Xem lịch sử reboot máy |

# Các lệnh shutdown, restart ... trong Linux
| lệnh Linux | Mô tả |
|--------------|------|
|Logout | Kết thúc session (phiên làm việc) hiện tại|
|reboot | 	Khởi động lại máy |
|shutdown -r now | Khởi động lại máy (tương đương với lệnh reboot) |
|shutdown -h now | 	Tắt máy (ngay lập tức) |
|shutdown -h 9:30| 	Hẹn giờ tắt máy (schedule) vào lúc 9h30 (tính theo khung 24h) |
|shutdown -c | 	Hủy bỏ tất cả các lệnh tắt máy trước đó (các lệnh tắt máy theo schedule) |
|telinit 0 | Tắt máy (tương đương lệnh shutdown -h now) |
|init 0 | Tắt máy (tương đương lệnh shutdown -h now hoặc telinit 0) |
|exit |  Thoát khỏi terminal |
|halt | Tắt máy (tương tự shutdown) |
|sleep | Cho hệ thống ngừng hoạt động trong một thời gian (ngủ – tương tự Windows) |
 
# Các lệnh quản lí user 
| lệnh Linux | Mô tả |
|--------------|------|
| passwd |	Đổi mật khẩu (standard user có thể đổi pass của họ còn user root thì thay đổi được password của mọi user)|
| useradd | Kiểm tra syntax và định dạng của dữ liệu user/password (/etc/passwd) |
| userdel | Tạo user mới, ví dụ: useradd -c “test user 1” -g group1|
| userdel | Xóa User |
| usermod | Thay đổi thông tin user (group, name…)|
| groupadd |	Tạo một nhóm user mới |
| groupdel |Xóa nhóm user |
| groupmod |	Thay đổi thông tin group, ví dụ, groupmod -n “old group name”  “new name”|
| who /w |	Hiển thị những user đang đăng nhập hệ thống |
| uname | Hiển thị tên của hệ thống (host) | 
| id | 	Hiển thị user ID (Chỉ danh của user) |
| logname | Hiển thị tên user đang login |
| su | Cho phép đăng nhập với tên user khác (tương tự secondary logon của Windows) |
| groups | Hiển thị nhóm của user hiện tại |
| #vi /ect/passwd |	Xem danh sách user |
| #vi /ect/group  |	Xem danh sách nhóm (group) |
| chmod [tên file=""][/tên] | Thay đổi quyền cho file/thư mục (chỉ user sở hữu file mới thực hiện được) |
| chown user [tên file=""][/tên] |Thay đổi chủ sở hữu file/thư mục |
| chgrp group [file][/file] |Thay đổi group sở hữu file/thư mục |

# Các lệnh Quản lý services và process:
| lệnh Linux | Mô tả |
|--------------|------|
| top |	Lệnh top khá giống như Task Manager trong Windows. Nó đưa ra thông tin về tất cả tài nguyên hệ thống, các process đang chạy, tốc độ load trung bình… Lệnh top -d thiết lập khoảng thời gian làm mới lại hệ thống  |
| ps -u username|	Kiểm tra những process được thực hiện bởi một user nhất định|
| ps -U root | 	Kiểm tra mọi process ngoại trừ những process hệ thống |
| ps -A |	Kiểm tra mọi process trong hệ thống|
| Ss | Kiểm tra socket đang kết nối |
| ss -I |	Hiển thị các cổng đang mở |
| w username | 	Kiểm tra user đăng nhập, lịch sử đăng nhập, các process user đó đang chạy |
|  vmstat3 | 	Kiểm soát hành vi hệ thống, phần cứng và thông tin hệ thống trong Linux |
| ps       |	Hiển thị các chương trình hiện đang chạy|
| uptime | Hiển thị thời gian đã vận hành của hệ thống trong bao lâu |
| rmp | 	Kiểm tra, gỡ bỏ hoặc cài đặt 1 gói .rpm |
| yum | 	Cài đặt các ứng dụng đóng gói (giống rpm)  |
| wget |	Tải các ứng dụng từ một website về |
| sh | 	Chạy một ứng dụng có đuôi .sh |
| Startx|	Khởi động chế độ xwindows từ cửa sổ terminal |
| yum update -y| 	Update Linux (CentOS)|
| stop/start/restart| 	Dừng/ khởi động/khởi động lại một service hoặc ứng dụng, ví dụ: service mysql stop hoặc /etc/init.d/mysqld start |
| kill |	Dừng proccess (thường dùng khi process bị treo). Chỉ có super-user mới có thể dừng tất cả các process còn user khác chỉ có thể dừng proccess mà user đó tạo ra |
| kill PID hoặc %job | Ngừng một process bằng số PID (Process Identification Number) hoặc số công việc |
| pstree | Hiển thị tất cả các process dưới dạng cây |
| service -status-all |	Kiểm tra tất cả các service và tình trạng của nó|
| whereis mysql |Hiển thị nơi các file dịch vụ được cài đặt|
| service -status-all │ grep abc |	Xem tình trạng của process abc | 
| kill -9 PID |	Bắt buộc đóng một process ID|
| kill -1 PID |Bắt buộc đóng một process ID và load lại cấu hình mặc định của process đó |

# Một số lệnh hữu ích khác
| lệnh Linux | Mô tả |
|--------------|------|
| clear | Xoá trắng cửa sổ dòng lệnh |
| hwclock | Fix lịch của BIOS |
| cal | Xem lịch hệ thống |
| date | Xem lịch ngày giờ hệ thống |
| date –s “1 JAN 2018 15:29:00” | Đặt ngày giờ hệ thống theo string |
| date +%Y%m%d -s “20180101″ | Đặt ngày hệ thống (không thay đổi giờ) |
| date +%T -s “00:29:00″ | Đặt giờ hệ thống, không thay đổi ngày |

# Các câu lệnh xem thông tin file và thư mục
| lệnh Linux | Mô tả |
|--------------|------|
| ls | Lấy danh sách tất cả các file và folder trong thư mục hiện hành |
| ls tenthumuc | Liệt kê nội dung bên trong một thư mục |
| ls -l | Như trên, nhưng liệt kê cả kích thước file, ngày cập nhật.|
| ls -a | Liệt kê tất cả các file ẩn |
| pwd | Xuất đường dẫn của folder đang làm việc |
| cd  | Thay đổi folder làm việc đến một folder mới (tương tự như trong DOS ) |
| df  | Kiểm tra disk space |

# Lệnh nén và giải nén
| lệnh Linux | Mô tả |
|--------------|------|
| tar -cvf	| Nén file/thư mục sang định dạng .tar|
| tar -xvf	| Giải nén file tar |
| gzip	| Chuyển file .tar sang .tar.gz |
| gunzip	| Chuyển file .tar.gz về .tar |
| tar -xzf	| Giải nén file .tar.gz, ví dụ:  tar -xvf archive.tar |
| tar -zxvf	| Giải nén file .tar.bz2 |
| tar -jxvf	| Giải nén file .tar.gz2 |
| unzip	| Giải nén file zip | 

# Lệnh sao lưu và phục hồi database
| lệnh Linux | Mô tả |
|--------------|------|
| mysqldump -u root -p[dbpass] [databasename] > [database.sql]	| Sao lưu database ra file .sql |
| mysqldump -u root -p[dbpass] [databasename] │ gzip -9 > [backupfile].sql.gz	| Sao lưu database và nén lại dưới dạng .gz |
| mysql -u username -p[dbpass] [databasename] < [database].sql | Khôi phục database |



