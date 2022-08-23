<img src="https://www.totolink.vn/public/uploads/img_post/arp-la-gi-muc-dich-va-cach-thuc-hoat-dong-cua-arp-1.jpg">

# 1.Khái niệm
ARP (viết tắt của cụm từ Address Resolution Protocol) là giao thức mạng được dùng để tìm ra địa chỉ phần cứng (địa chỉ MAC) của thiết bị từ một địa chỉ IP nguồn. Nó được sử dụng khi một thiết bị giao tiếp với các thiết bị khác dựa trên nền tảng local network. Ví dụ như trên mạng Ethernet mà hệ thống yêu cầu địa chỉ vật lý trước khi thực hiện gửi packets. 

ARP là phương thức phân giải địa chỉ động giữa địa chỉ lớp network và địa chỉ lớp datalink. Quá trình thực hiện bằng cách: một thiết bị IP trong mạng gửi một gói tin local broadcast đến toàn mạng yêu cầu thiết bị khác gửi trả lại địa chỉ phần cứng ( địa chỉ lớp datalink ) hay còn gọi là Mac Address của mình.
 
ARP là giao thức lớp 2 - Data link layer trong mô hình OSI và là giao thức lớp Link layer trong mô hình TCP/IP.

# 2.Những thành phần quan trọng trong ARP
- ARP Cache: sau khi phân giải địa chỉ MAC, ARP sẽ gửi đến bộ lưu trữ một bản để tham khảo trong tương lai. Các giao tiếp kế tiếp sẽ có thể dùng địa chỉ MAC từ bản.
- ARP Cache Timeout: đó là thời gian mà địa chỉ MAC trong bộ nhớ cache ARP có thể lưu trữ.
- ARP request: có nhiệm vụ truyền một gói tin qua mạng để xác nhận xem chúng có gặp đúng địa chỉ MAC đích hay không.
- ARP response/reply: phản hồi địa chỉ MAC từ đích hỗ trợ truyền dữ liệu xa hơn.
