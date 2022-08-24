<img src="https://vnpro.vn/upload/user/images/Th%C6%B0%20Vi%E1%BB%87n/tong-quan-ve-dinh-tuyen.jpg">

# 1.Khái niệm
Định tuyến (Routing) là quá trình tìm kiếm và xác định đường đi tốt nhất trên một mạng máy tính để gói tin tới được đích thông qua các thiết bị định tuyến.

Để làm được điều đó thì các thiết bị định tuyến cần phải dựa vào thông tin bẳng định tuyến (Routing Table) và giao thức định tuyến ( Routing Protocol).

# 2.Định tuyến tĩnh
## 2.1.Khái niệm
Định tuyến tĩnh là quá trình router thực hiện chuyển gói dữ liệu tới địa chỉ mạng đích dựa vào địa chỉ IP đích của gói dữ liệu. Để chuyển được gói dữ liệu đến đúng đích thì router phải học thông tin về đường đi tới các mạng khác. Thông tin về đường đi tới các mạng khác sẽ được người quản trị cấu hình cho router. 
## 2.2.Ưu Điểm 
- Sử dụng ít bandwidth hơn định tuyến động.
- Không tiêu tốn tài nguyên để tính toán và phân tích gói tin định tuyến.
## 2.3Nhược điểm:
- Không có khả năng tự động cập nhật đường đi.
- Phải cấu hình thủ công khi mạng có sự thay đổi.
- Phù hợp với mạng nhỏ, rất khó triển khai trên mạng lớn.
## 2.4.Một số tình huống bắt buộc dùng định tuyến tĩnh:
- Đường truyền có băng thông thấp
- Người quản trị mạng cần kiểm soát các kết nối.
- Kết nối dùng định tuyến tĩnh là đường dự phòng cho đường kết nối dùng giao thức định tuyến động.
- Chỉ có một đường duy nhất đi ra mạng bên ngoài (mạng stub).
- Router có ít tài nguyên và không thể chạy một giao thức định tuyến động.
- Người quản trị mạng cần kiểm soát bảng định tuyến và cho phép các giao thức classful và classless.

## 2.5.Cấu hình định tuyến tĩnh
Router (config) # ip route destination_subnet subnetmask{IP_next_hop|output_interface} [AD]

Trong đó:
- destination_subnet: mạng đích đến.
- subnetmask: subnet – mask của mạng đích.
- IP_next_hop: địa chỉ IP của trạm kế tiếp trên đường đi.
- output_interface: cổng ra trên router.
- AD: chỉ số AD của route khai báo, sử dụng trong trường hợp có cấu hình dự phòng.
