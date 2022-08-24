<img src="https://media.bkns.vn/uploads/2019/12/han-che-cua-ipv4-la-gi.jpg">

# 1.Khái niệm
IPv4 (Internet Protocol version 4) là phiên bản thứ tư trong quá trình phát triển của các giao thức Internet. IP – Internet Protocol, là một giao thức của chồng giao thức TCP/IP thuộc về lớp Internet, tương ứng với lớp thứ ba (lớp network) của mô hình OSI. Ngày nay, IP gần như là giao thức lớp 3 thống trị, được sử dụng rộng rãi trong mọi hệ thống mạng trên phạm vi toàn thế giới.
# 2.Cấu trúc địa chỉ IPv4
- Địa chỉ IP gồm 32 bit nhị phân, chia thành 4 cụm 8 bit (gọi là các octet). Các octet được biểu diễn dưới dạng thập phân và được ngăn cách nhau bằng các dấu chấm.
- Địa chỉ IP được chia thành hai phần: phần mạng (network) và phần host.
<img src="https://anninhmang.edu.vn/wp-content/uploads/2017/11/anh-1.png">

- Nguyên tắc đặt địa chỉ IP
  - Các bit phần mạng không được phép đồng thời bằng 0.
  - Nếu các bit phần host đồng thời bằng 0, ta có một địa chỉ mạng. 
  - Nếu các bit phần host đồng thời bằng 1, ta có một địa chỉ broadcast. 
# 3.Các lớp địa chỉ IPv4
# 3.1.Lớp A
<img src="https://anninhmang.edu.vn/wp-content/uploads/2017/11/dia-chi-ip-lop-A.jpg">

- Địa chỉ lớp A sử dụng một octet đầu làm phần mạng, ba octet sau làm phần host.
- Bit đầu của một địa chỉ lớp A luôn được giữ là 0.
- Các địa chỉ mạng lớp A gồm: 1.0.0.0 -> 126.0.0.0.
- Mạng 127.0.0.0 được sử dụng làm mạng loopback.
- Phần host có 24 bit => mỗi mạng lớp A có (224 – 2) host.
# 3.2.Lớp B
<img src="https://anninhmang.edu.vn/wp-content/uploads/2017/11/dia-chi-ip-lop-B.jpg">

- Địa chỉ lớp B sử dụng hai octet đầu làm phần mạng, hai octet sau làm phần host.
- Hai bit đầu của một địa chỉ lớp B luôn được giữ là 1 0.
- Các địa chỉ mạng lớp B gồm: 128.0.0.0 -> 191.255.0.0. Có tất cả 214 mạng trong lớp B.
- Phần host dài 16 bit do đó một mạng lớp B có (216 – 2) host.
# 3.3.Lớp C
<img src="https://anninhmang.edu.vn/wp-content/uploads/2017/11/dia-chi-ip-lop-C.jpg">

- Địa chỉ lớp C sử dụng ba octet đầu làm phần mạng, một octet sau làm phần host.
- Ba bit đầu của một địa chỉ lớp C luôn được giữ là 1 1 0.
- Các địa chỉ mạng lớp C gồm: 192.0.0.0 -> 223.255.255.0. Có tất cả 221 mạng trong lớp C.
- Phần host dài 8 bit do đó một mạng lớp C có (28 – 2) host.
# 3.4.Lớp D
- Gồm các địa chỉ thuộc dải: 224.0.0.0 -> 239.255.255.255
- Được sử dụng làm địa chỉ multicast.
- Ví dụ: 224.0.0.5 dùng cho OSPF; 224.0.0.9 dùng cho RIPv2
# 3.5.Lớp E
- Từ 240.0.0.0 trở đi.
- Được dùng cho mục đích dự phòng.
## Lưu ý
- Các lớp địa chỉ IP có thể sử dụng đặt cho các host là các lớp A, B, C.
- Để thuận tiện cho việc xác định địa chỉ IP thuộc lớp nào, có thể quan sát octet đầu của địa chỉ, nếu octet này có giá trị nằm trong khoảng:
  - 1 -> 126: địa chỉ lớp A.
  - 128 -> 191: địa chỉ lớp B.
  - 192 -> 223: địa chỉ lớp C.
  - 224 -> 239: địa chỉ lớp D.
  - 240 -> 255: địa chỉ lớp E.
# 4.Địa chỉ Private và địa chỉ Public
Địa chỉ IP được phân thành 2 loại: private và public.
- Private: chỉ được sử dụng trong mạng nội bộ (mạng LAN), không được định tuyến trên môi trường Internet. Có thể được sử dụng lặp lại trong các mạng LAN khác nhau.
- Public: là địa chỉ được sử dụng cho các gói tin đi trên môi trường Internet, được định tuyến trên môi trường Internet. Địa chỉ public phải là duy nhất cho mỗi host tham gia vào Internet.
