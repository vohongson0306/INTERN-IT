>> Căn bản cấu hình CSF Firewall
# 1. Những file cấu hình trong CSF
- Toàn bộ thông tin cấu hình và quản lý CSF được lưu ở các file trong folder /etc/csf. Nếu bạn chỉnh sửa các file này thì cần khởi động lại CSF để thay đổi có hiệu lực.
```
csf.conf : File cấu hình chính để quản lý CSF.
csf.allow : Danh sách địa chỉ IP cho phép qua firewall.
csf.deny : Danh sách địa chỉ IP từ chối qua firewall.
csf.ignore : Danh sách địa chỉ IP cho phép qua firewall và không bị block nếu có vấn đề.
csf.*ignore : Danh sách user, IP được ignore
```
# 2. cấu hình.
Trước khi cấu hình CSF, chúng ta cần tìm hiểu các quy ước về thông số:
– Tất cả các file cấu hình csf nằm ở: /etc/csf/

– Các tham số khi cấu hình có dạng ARGS = “VALUE” , trong đó
```
            + VALUE = “0″ => Disable (Tắt)

            + VALUE = “1″ => Enable (Bật)

            + VALUE > 1 (VALUE = “10″ , VALUE = “60″ … ) : giới hạn tối đa.

            + VALUE >1 (VALUE = “3600″ , VALUE = “7200″ … ) : thời gian tối đa.
```
# cấu hình căn bản:
- cấu hình csf firewall nằm trong file csf.conf
```
          nano /tmp/csf/csf.conf
```
- Chúng ta bắt đầu thực hiện config CSF. Đầu tiên hãy mở file: csf.conf và chỉnh sửa theo hướng dẫn bên dưới:
```
TESTING = "0"
```
- Mặc định khi cài xong CSF thì TESTING = “1″, với TESTING = “1″ thì LFD daemon (Login Fail Detect daemon) sẽ không hoạt động, do đó nếu máy chủ bị tấn công thì CSF cũng sẽ không block IP tấn công.
```
TESTING_INTERVAL = "5"
```
- Thời gian chạy cronjob để clear iptables nếu như TESTING=1 , tính bằng phút.
```
AUTO_UPDATES = "0"
```
- Tắt chế độ auto update của CSF.
```
TCP_IN = "22,25,53,80,443"
```
- Cho phép kết nối TCP qua các cổng: Dùng cho các dịch vụ SSH, sendmail, DNS, Web trên server. (nếu bạn không sử dụng https và email có thể bỏ 25 và 443).
```
TCP_OUT = "25,80"
```
- Cho phép kết nối từ máy chủ ra bên ngoài: cho phép server kết nối đến web server, sendmail server khác.
```
UDP_IN = "53"
```
- Cho phép người dùng sử dụng dịch vụ DNS trên server.
```
UDP_OUT = "53"
```
- Cho phép server truy vấn DNS bên ngoài.
```
ICMP_IN = "1"
```
- Cho phép người dùng thực hiện lệnh ping đến server.
```
ICMP_IN_RATE = "20/s"
```
- Nếu để giá trị này thấp thì khi ping sẽ nhận được giá trị request time out.
```
ETH_DEVICE = "eth0"
```
- Mặc định csf sẽ cấu hình iptables để filter traffic trên toàn bộ các card mạng , ngoại trừ card loopback . Nếu như bạn muốn rules iptables chỉ applied vào card mạng “eth0″ thì khai báo ở đây.
```
ETH_DEVICE_SKIP = "eth1"
```
- Nếu bạn không muốn rules iptables không applied vào card mạng nào thì khai báo ở đây. Ví dụ card “eth1″ là card local , bạn không muốn filter trên card này thì cấu hình như trên.
```
DENY_IP_LIMIT = "200"
```
– Giới hạn số lượng IP bị block “vĩnh viễn” bởi CSF (các IP này được lưu trong file /etc/csf/csf.deny).
– Con số này để 200 nếu bạn sử dụng VPS và 500 nếu bạn sử dụng server. – Khi số lượng IP bị block vượt qua con số này , csf sẽ tự động unblock IP cũ nhất.
```
LF_DAEMON = "1"
```
- Enable tính năng Login fail detection.
```
LF_CSF = "1"
```
- Tự động restart CSF khi csf bị stop.
```
PACKET_FILTER = "1"
```
- Filter các gói tin TCP không hợp lệ… )
```
IPV6 = "0"

Disable IPV6 support.
SYNFLOOD = "1" SYNFLOOD_RATE = "30/s" SYNFLOOD_BURST = "40"
```
- Bật chức năng synflood protection : Nếu 1 IP gửi 30 cú pháp SYN trong vòng 1s và số lượng SYN connection tồn tại trên server đạt trên 40 thì block tạm thời IP đó.
```
CONNLIMIT = "80;20"
```
- Giới hạn số lượng new concurrent connection đến server trên mỗi IP.
– Ví dụ trên có nghĩa : mỗi IP được phép mở 20 concurrent new connection đến port 80 trên server.
```
PORTFLOOD = "80;tcp;20;5"
```
- Giới hạn số lượng connection đến một port cụ thể trong một khoảng thời gian nhất định.
– Ví dụ như trên có nghĩa : nếu nhiều hơn 20 kết nối tcp đến port 80 trong vòng 5s thì block IP đó tối thiểu 5s tính từ packet cuối cùng của IP đó. Sau 5s IP đó sẽ tự động được unlock và truy cập bình thường.
```
DROP_NOLOG = "10050,10051"
```
- Danh sách các port khi bị drop sẽ không cần phải ghi vào log.
```
CONNLIMIT_LOGGING = "1"
```
- Ghi log các IP vượt quá giới hạn CONNLIMIT cấu hình ở bước trên.
```
LF_ALERT_TO = "your_email@your_domain.com"
```
- Mặc định toàn bộ email thông báo sẽ được gửi về root của server . Nếu bạn muốn gửi đến địa chỉ email khác thì khai báo ở đây.
```
LF_PERMBLOCK = "1" LF_PERMBLOCK_INTERVAL = "86400" LF_PERMBLOCK_COUNT = "6" LF_PERMBLOCK_ALERT = "1"
```
- Enable tính năng block vĩnh viễn một IP . Nếu một IP bị temp ban (ban tạm) 6 lần khi vi phạm các rule sẽ block ip này 86400s ( 1 ngày) đồng thời gửi email về cho ngừoi quản trị biết.
```
LF_TRIGGER = "1"
```
- Enable tính năng Login Fail Detect cho từng dịch vụ cụ thể (được khai báo bên dưới).
```
LF_TRIGGER_PERM = "1"
```
- Khi LF_TRIGGER = “1″ thì có thể enable LF_TRIGGER_PERM để kích hoạt block IP permanent.
```
LF_TRIGGER_PERM = “1″ => IP sẽ bị block permanent.
LF_TRIGGER_PERM = “86400″ => IP sẽ bị block 1 ngày.
LF_SELECT = "1"
```
- Khi một IP vi phạm các rule của LFD thay vì block toàn bộ traffic từ IP này đến server thì chỉ block traffic đến dịch vụ mà IP này login fail (ví dụ login FTP sai nhiều lần thì block truy cập đến FTP nhưng vẫn cho phép truy cập vào website)
```
LF_EMAIL_ALERT = "1"
```
- Gửi email thông báo nếu một IP bị block bởi các trigger bên dưới
```
LF_SSHD = "5" LF_SSHD_PERM = "1"
```
– Nếu login SSH sai 5 lần thì sẽ bị block IP (temp block).
– Nếu bị temp block lớn hơn số lần quy định ở LF_PERMBLOCK_COUNT (cấu hình bước trên ) thì sẽ block permanent.
```
LF_FTPD = "0" LF_FTPD_PERM = "1"
```
- Không kích hoạt login fail detect cho dịch vụ FTP. Tương tự cho các dịch vụ còn lại bên dưới ( SMTP , POP3 , IMAP , .htpasswd , mod_security … )
```
LF_SSH_EMAIL_ALERT = “0″
```
- Không gửi email thông báo khi có một ai đó login thành công thông qua SSH
```
LF_SU_EMAIL_ALERT = “0″
```
- Không gửi email thông báo khi có một người dùng “su” (switch user) qua người dùng khác. Không gửi email khi họ dùng lệnh “su” , bất kể “su” thành công hoặc thất bại.
```
LF_DIRWATCH = "3600"
```
– LFD sẽ check thư mục /tmp và /dev/shm định kỳ sau mỗi 3600s , nếu phát hiện ra các file nghi vấn là file độc hại sẽ gửi email thông báo đến cho chúng ta.
– Thường thì trên server thư mục, /temp và /dev/shm phân quyền cho phép mọi người dùng có quyền ghi trên thư mục này , do đó các attacker lợi dụng điều này để ghi mã độc vào đây (các file để back connect , local root exploit … )
```
LF_DIRWATCH_DISABLE = "1"
```
- Khi phát hiện ra các file nghi vấn ở thư mục /tmp và /dev/shm sẽ mv chúng khỏi 2 thư mục trên và append vào file /etc/csf/suspicious.tar , thuận tiện cho chúng ta theo dõi , phân tích về sau và phần nào vô hiệu hóa cuộc tấn công của attacker.
```
LF_DIRWATCH_FILE = "60"
```
- Theo dõi sự thay đổi của các file và thư mục , nếu có thay đổi gửi email thông báo về cho chúng ta. Để theo dõi file/thư mục nào thì add chúng vào file csf.dirwatch. Cấu hình như trên thì 60s chạy 1 lần.
```
LF_INTEGRITY = "0"
```
- Kiểm tra tính toàn vẹn của hệ điều hành bằng cách so sánh MD5 của các file binary khi LFD start với MD5 của các file đó lúc kiểm tra. Nếu khác nhau thì sẽ gửi email thông báo. Tính năng này có thể sẽ hoạt động không chính xác khi hệ thống update và sẽ tăng I/O , load của server do phải tính toán MD5 rất nhiều lần.
```
LF_DISTATTACK = "0"
```
- Phát hiện tấn công brute force từ mạng botnet. Nếu như một account bị login sai quá giới hạn cho phép từ nhiều IP khác nhau thì sẽ block toàn bộ IP đã login sai.
```
LF_DISTATTACK_UNIQ = "2"
```
- Số lượng IP tối thiểu để nhận biết đây là tấn công phân tán (DDOS).
```
LT_POP3D = "30"
```
- Block login POP3 nếu một account được login nhiều hơn 30 lần trong 1 giờ từ 1 IP. Tương tự cho LT_IMAPD.
```
LT_EMAIL_ALERT = "0"
```
- Send email khi một account vượt quá giới hạn cho phép của LT_IMAPD và LT_POP3D
```
LT_SKIPPERMBLOCK = "0"
```
- Không áp dụng permanent block cho LT_POP3D/LT_IMAPD
```
CT_LIMIT = "300"
```
- Giới hạn số lượng connection từ một IP đến server . Nếu số lượng đó vượt quá 300 thì temp block IP đó.
```
CT_INTERVAL = "30"
```
- Các lần scan để kiểm tra cách nhau 30s.
```
CT_EMAIL_ALERT = "1"
```
- Gửi email thông báo nếu một IP bị block bởi connection tracking.
```
CT_PERMANENT = "0"
```
- Disable block permanent cho connectiong tracking.
```
CT_BLOCK_TIME = "1800"
```
- Thời gian block một IP nếu như vi phạm Connection tracking limit.
```
CT_SKIP_TIME_WAIT = "0"
```
- Khi đếm số lượng connection từ 1 IP đến server thì bỏ qua trạng thái TIME_WAIT của connection , không đếm trạng thái này.
```
CT_STATES = "SYN_RECV"
```
- Chỉ đếm các kết nối ở trạng thái SYN_RECV
```
CT_PORTS = "80,443"
```
- Chỉ áp dụng connection tracking cho các kết nối đến port 80 và 443.
```
PS_INTERVAL = "300" PS_LIMIT = "15"
```
- Trong 500s nếu kết nối đến nhiều hơn 15 port không có trên server sẽ block IP đó.
```
PS_PORTS = "0:65535,ICMP"
```
- Giới hạn range port sẽ được theo dõi.
```
PS_PERMANENT = "0"
```
- IP bị block bởi Port Scan Tracking sẽ là temp block hoặc là permanent :
```
PS_PERMANENT = “0″ : IP bị temp block – PS_PERMANENT = “1″ : IP bị block permanent.
```
```
PS_BLOCK_TIME = "3600"
```
- Nếu PS_PERMANENT = “0″ thì đây là thời gian temp block của một IP.
```
PS_EMAIL_ALERT = "1"
```
- Gửi email thông báo khi có một IP bị block.
- Sau khi thực hiện config xong cấu hình CSF. Bạn phải restart lại CSF để thay đổi có hiệu lực: csf -r



















