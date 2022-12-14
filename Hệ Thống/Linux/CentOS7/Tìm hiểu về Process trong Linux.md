# 1.Processes (Tiến trình)
Tiến trình (processes) được hiểu đơn giản là một chương trình đang chạy trong trong hệ điều hành. Một tiến trình có thể phân thành một hay nhiều tiến trình con khác
# 2. Phân loại tiến trình
## 2.1. Init process
- Init process là tiến trình đầu tiên được khởi động sau khi bạn lựa chọn hệ điều hành trong boot loader. Trong cây tiến trình, init process là tiến trình cha của các tiến trình khác. Init process có đặc điểm sau:
  - PID = 1
  - Không thể kill init process
## 2.2. Parents process – Child process
- Trong hệ điều hành linux các tiến trình được phân thành parents process và child process. Một tiến trình khi thực hiện lệnh fork() để tạo ra một tiến trình mới thì đưọc gọi là parents process. Tiến trình mới tạo được gọi là child process.
<img src="https://wiki.tino.org/wp-content/uploads/2019/10/process01.png">
- Một parents process có thể có nhiều child process nhưng một child process chỉ có một parents process. Khi quan sát thông tin của một tiến trình, ngoài PID (Processes ID) ta cần để ý tới PPID (Parent Processes ID). Nó sẽ cho ta thông tin về parents process của tiến trình đó:

`ps -ef`

![image](https://user-images.githubusercontent.com/110179869/189081047-34f3c5c5-bd25-41c3-a266-84c3a97f1bae.png)

## 2.3. Orphan process – Zombie Process
- Khi parents process – child process hoạt động sẽ xảy ra một số trường hợp đặc biệt. Lúc đó Orphan process – Zombie Process sẽ được hình thành.
- Khi một parents process bị tắt trước khi child process được tắt, tiến trình con đó sẽ trở thành một orphan process. Lúc này init process sẽ trở thành cha của orphan processes và thực hiện tắt chúng.
- Khi một child process được kết thúc, mọi trạng thái của child process sẽ được thông báo bởi lời gọi hàm wait() của parents process. Vì vậy, kernel sẽ đợi parents process trả về hàm wait() trước khi tắt child process. Tuy nhiên vì một vài lí do mà parents process không thể trả về hàm wait(), khi đó child process sẽ trở thành một zombie process. Khi ở trạng thái này, tiến trình sẽ gần như giải phóng bộ nhớ hoàn toàn, chỉ lưu giữ một số thông tin như PID, lượng tại nguyên sử dụng,… trên bảng danh sách tiến trình.
- Tuy giải phóng bộ nhớ hoàn toàn nhưng các zombie process không bị kết thúc. Vì vậy nếu lượng zombie process lớn sẽ nắm giữ lượng lớn các PID. Nếu lượng PID đầy, sẽ không có tiến trình mới được tạo thêm. Các zombie process sẽ chỉ bị kết thúc nếu như parents process của chúng bị kill.
- Để tìm các zombie process ta gõ kiểm tra trạng thái của tiến trình theo lệnh sau:
## 2.4 Daemon Process
Một Daemon Process là một tiến trình chạy nền. Nó sẽ luôn trong trạng thái hoạt động và sẽ được kích hoạt bởi một điều kiện hoặc câu lệnh nào đó. Trong Unix, các daemon thường được kết thúc bằng “d” ví dụ như httpd, sshd, crond, mysqld,…
# 3.Các lệnh về Process
`-f` : hiển thị đầy đủ thông tin về các process

![image](https://user-images.githubusercontent.com/110179869/189083524-9026e042-3fa3-4f29-95f0-dad918298600.png)

`-e` : hiển thị đầy đủ các process ( bao gồm cả system process )

![image](https://user-images.githubusercontent.com/110179869/189083724-2409a313-f128-4d33-b9a6-eb2bd721671b.png)


-aux = -ef : hiển thị đầy đủ thông tin về tất cả các process

![image](https://user-images.githubusercontent.com/110179869/189083854-3748fe24-c208-4916-8fe4-12c6a5ef3aa4.png)


`-u` : hiển thị các process liên quan đến user hiện hành

![image](https://user-images.githubusercontent.com/110179869/189083588-609005ac-2f57-4cf4-82f2-696667aae072.png)


`-p PID` : hiển thị thông tin process cụ thể

`pgrep ssh` :để tìm kiếm bất kỳ quy trình liên quan đến SSH nào trên hệ thống

![image](https://user-images.githubusercontent.com/110179869/189084694-581a327c-51d6-43ee-a244-6bb41fdc10cc.png)

`top` :Kiểm tra live các process đang chạy

![image](https://user-images.githubusercontent.com/110179869/190943020-46d367e9-7781-4285-b35b-a70761dffe46.png)

- Thông tin được hiển thị:
  - Dòng 1:
    - Thời gian
    - Máy tính đã chạy được bao lâu rồi
    - Số lượng người dùng
    - Trung bình tải
    - Trung bình tải hiển thị thời gian load hệ thống trong 1, 5 và 15 phút cuối.
  - Dòng 2:
    - Tổng số nhiệm vụ
    - Số lượng tác vụ đang chạy
    - Số lượng tác vụ trong trạng thái “ngủ”
    - Số lượng tác vụ đã dừng
    - Số lượng tác vụ zombie (tiến trình không tồn tại)
  - Dòng 3:
    - Mức sử dụng CPU bởi người dùng theo tỷ lệ phần trăm
    - Mức sử dụng CPU bởi hệ thống theo tỷ lệ phần trăm
    - Mức sử dụng CPU bởi các tiến trình có mức ưu tiên thấp theo tỷ lệ phần trăm
    - Mức sử dụng CPU bởi idle process (tiến trình cho biết bộ xử lý đang rảnh rỗi) theo tỷ lệ phần trăm
    - Mức sử dụng CPU bởi io wait (thời gian CPU không hoạt động để chờ I/O disk hoàn thành) theo tỷ lệ phần trăm
    - Mức sử dụng CPU bởi việc ngắt phần cứng theo tỷ lệ phần trăm
    - Mức sử dụng CPU bởi việc ngắt phần mềm theo tỷ lệ phần trăm
    - Mức sử dụng CPU bởi steal time (thời gian CPU ảo “chờ” CPU thực) theo tỷ lệ phần trăm
  - Dòng 4:
    - Tổng bộ nhớ hệ thống
    - Bộ nhớ trống
    - Bộ nhớ đã sử dụng
    - Bộ nhớ đệm buffer cache
  - Dòng 5:
    - Tổng swap có sẵn
    - Tổng swap còn trống
    - Tổng swap đã sử dụng
    - Bộ nhớ khả dụng
  - Bảng chính:
    - ID tiến trình
    - Người dùng
     - Mức độ ưu tiên
    - Mức độ nice (gọi một tập lệnh shell với mức độ ưu tiên cụ thể)
    - Bộ nhớ ảo được sử dụng bởi tiến trình
    - Bộ nhớ “thường trú” mà một tiến trình sử dụng (tức là tiến trình luôn ở trong bộ nhớ và không thể chuyển ra thiết bị lưu trữ khác)
    - Bộ nhớ có thể chia sẻ
    - CPU được sử dụng bởi tiến trình theo tỷ lệ phần trăm
    - Bộ nhớ được sử dụng bởi tiến trình theo tỷ lệ phần trăm
    - Thời gian tiến trình đã được chạy
    - Lệnh
