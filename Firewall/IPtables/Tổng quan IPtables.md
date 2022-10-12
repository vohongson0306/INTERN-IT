<img src="https://fptcloud.com/wp-content/uploads/2022/03/iptables-1.jpg">

# 1.Khái niệm:
Iptables chính là một chương trình Firewall – Tường lửa miễn phí. Chương trình này được phát triển chủ yếu cho hệ điều hành Linux. Chương trình cho phép hệ điều hành thiết lập các quy tắc riêng để kiểm soát truy cập và tăng tính bảo mật cho hệ thống gồm: VPS/Hosting/Server.

# Các thành phần trong Iptables:
<img src="https://cdn-ak.f.st-hatena.com/images/fotolife/q/quoll00/20200209/20200209022945.png">

## Table
<img src="https://vietnix.vn/wp-content/uploads/2021/06/iptables-la-gi.webp">

Iptable sử dụng table để định nghĩa các rules cụ thể cho các gói tin. Các phiên bản Linux hiện nay có 4 loại table khác nhau:

+ Filter table
Table này quen thuộc và hay được sử dụng nhất. table này nhằm quyết định liệu gói tin có được chuyển đến địa chỉ đích hay không

+ Mangle table
Table này liên quan đến việc sửa header của gói tin, ví dụ chỉnh sửa giá trị các trường TTL, MTU, Type of Service

+ Table Nat
Table này cho phép route các gói tin đến các host khác nhau trong mạng NAT table cách thay đổi IP nguồn và IP đích của gói tin. Table này cho phép kết nối đến các dịch vụ không được truy cập trực tiếp được do đang trong mạng NAT

+ Table raw
1 gói tin có thể thuộc một kết nối mới hoặc cũng có thể là của 1 một kết nối đã tồn tại. Table raw cho phép bạn làm việc với gói tin trước khi kernel kiểm tra trạng thái gói tin

## Chains
Mỗi table được tạo với một số chains nhất định. Chains cho phép lọc gói tin tại các điểm khác nhau. Iptable có thể thiết lập với các chains sau:

+ Chain PREROUTING
Các rule thuộc chain này sẽ được áp dụng ngay khi gói tin vừa vào đến Network interface. Chain này chỉ có ở table NAT, raw và mangle

+ Chain INPUT
Các rule thuộc chain này áp dụng cho các gói tin ngay trước khi các gói tin được vào hệ thống. Chain này có trong 2 table mangle và filter

+ Chain OUTPUT
Các rule thuộc chain này áp dụng cho các gói tin ngay khi gói tin đi ra từ hệ thống. Chain này có trong 3 table là raw, mangle và filter

+ Chain FORWARD
Các rule thuộc chain này áp dụng cho các gói tin chuyển tiếp qua hệ thống. Chain này chỉ có trong 2 table mangle và table

+ Chain POSTROUTING
Áp dụng cho các gói tin đi network interface. Chain này có trong 2 table mangle và NAT

## Target
Target hiểu đơn giản là các hành động áp dụng cho các gói tin. Đối với những gói tin đúng theo rule mà chúng ta đặt ra thì các hành động (TARGET) có thể thực hiện được đó là:

+ ACCEPT
Chấp nhận gói tin, cho phép gói tin đi vào hệ thống

+ DROP
Loại bỏ gói tin, không có gói tin trả lời, giống như là hệ thống không tồn tại

+ REJECT
Loại bỏ gói tin nhưng có trả lời table gói tin khác, ví dụ trả lời table 1 gói tin “connection reset” đối với gói TCP hoặc bản tin “destination host unreachable” đối với gói UDP và ICMP

+ LOG
Chấp nhận gói tin nhưng có ghi lại log

Gói tin sẽ đi qua tất cả các rule chứ không dừng lại khi đã đúng với 1 rule đặt ra. Đối với những gói tin không khớp với rule nào cả mặc định sẽ được chấp nhận











