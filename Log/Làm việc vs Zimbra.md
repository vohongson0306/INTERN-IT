# 1. log file zimbra
- Tất cả các log nội bộ của server zimbra được lưu trong thư mục /opt/zimbra/log.
image

# 2. mailbox.log
- Trong đó mailbox.log là nơi lưu trữ thời gian làm việc mức độ của sự việc, tác vụ, tên tài khoản, và địa chỉ IP cũng như mô tả liên quan đến sự việc.
- Log level thể hiện mức độ ảnh hưởng của sự kiện đến server. mặc định có 4 mức độ sử dụng: INFO, WARN, ERROR và FATAL.
  - INFO - Các event tại mức độ này có mục đích thông báo về các tiến trình của Zimbra như việc tạo, xóa message, v.v...
  - WARN - Các event tại mức này có nguy cơ tiềm tàng nhưng không ảnh hưởng đến hoạt động của server, ví dụ như sự kiện về đăng nhập sai của một người dùng.
  - ERROR - Thể hiện lỗi xảy ra và không ảnh hưởng đến hoạt động của server, ví dụ như cảnh báo về việc index dữ liệu của một người dùng đang bị lỗi.
  - FATAL - Thể hiện rằng server không thể hoạt động bình thường, ví dụ như thông báo không thể kết nối đến cơ sở dữ liệu.
- Các file log được cập nhật hằng ngày. Phiên bản sau cùng luôn có tên là mailbox.log, các file trước đó được nén và đặt tên theo ngày, ví dụ mailbox.log.2022-08-16.tar.gz.
image

# 3. Các file log khác.
- Thư mục /opt/zimbra/log còn chứa các file log khác, lưu lại các thông tin đặc thù như audit.log thể hiện đăng nhập thành công hoặc không.
- Bạn có thể dùng lệnh grep -ir "invalid password" /opt/zimbra/log/audit.log để xem những lần đăng nhập không thành công của user.
```
  grep -ir "invalid password" /opt/zimbra/log/audit.log
```

Bạn có thể tìm theo từ khóa FATAL khi server bị các sự cố nghiêm trọng. Hoặc tìm theo từ khóa ImapServer, Pop3Server khi muốn tìm thông tin liên quan đến giao thức pop3 hay imap.
# 4. một số cách tìm kiếm lỗi.
- tìm các log level error và fatal trong mailbox.
```
grep -iE 'fatal|error' mailbox.log
```
  - trong ảnh đang thể hiện lỗi xác thực đăng nhập không thành công do mật khẩu không hợp lệ
- tìm kiếm các log level info|warn và xung quanh đó.
```
grep -iEv -C3 'info|warn' mailbox.log
```
- tìm kiếm Hiển thị thêm một số dòng sau đó
```
grep -iEv -A3 'info|warn' mailbox.log
```
- Lọc theo từ khóa từ trái sang phải, đầu tiên là user1 sau đó là user2
```
grep -iE user1 /var/log/zimbra.log | grep user2
```
- giám sát user1 từ nhiều log file khác nhau theo thời gian thực
```
tail -f mailbox.log -f trace_log.2015_03_11 -f access_log.2015-03-11 -f sync.log -f ews.log | grep -i user1
```
# 5. Zimbra cung cấp công cụ giúp theo dấu các email đã gửi nhận: `zmmsgtrace`, chạy với quyền `Root.`
image
## truy vết theo địa chỉ gửi.
``` 
 /opt/zimbra/libexec/zmmsgtrace -s son@xn--vhongson-e4a.vn
```

## truy vết theo địa chỉ người nhận:
```  
/opt/zimbra/libexec/zmmsgtrace -r '@xn--vhongson-e4a.vn' 
```

## Trace từ các file log khác nhau
```
/opt/zimbra/libexec/zmmsgtrace -r '@gmail.com' /var/log/zimbra
```
# 6. Logger
- Để thiết lập ghi log tập trung trong một hệ thống Zimbra có nhiều server bạn cần cấu hình một host để thu nhận log. Thường bạn sẽ dùng mailbox server, cài đặt logger để thu thập log.
- Logger server sẽ thu thập thông tin thống kê, trạng thái của các service trên các server khác, zimbra.log được lưu tập trung nhưng các log khác như mailbox.log và audit.log được lưu theo kiểu round robin trên các mailstore server. Muốn tập trung các log này về một log server riêng, zimico khuyến cáo bạo dùng 1 giải pháp lưu và phân tích log tập trung của bên thứ 3 như Graylog.
## các bước thực hiện.
- Cài đặt logger của zimbra lên mailbox server này.
- Edit file /etc/sysconfig/rsyslog và cấu hình SYSLOGD_OPTIONS="-r -c 2"
- Edit /etc/rsyslog.conf và kích hoạt 2 dòng sau:
```
$ModLoad imupd $UDPServerRun 514 systemctl restart rsyslog su - zimbra /opt/zimbra/bin/zmsshkeygen /opt/zimbra/bin/zmupdateauthkeys /opt/zimbra/libexec/zmloggerinit Bạn kiểm tra thông số: zmprov gacf | grep zimbraLogHostname Trên các server khác, đảm bảo rằng thông số hiện tại là tên mailbox server đã được cài dịch vụ logger. Ngoài ra trên các server còn lại, chạy các lệnh sau: su - zimbra /opt/zimbra/bin/zmsshkeygen /opt/zimbra/bin/zmupdateauthkeys exit /opt/zimbra/libexec/zmsyslogsetup systemctl restart rsyslog su - zimbra zmcontrol restart
```
