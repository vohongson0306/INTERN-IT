<img src="https://maychuviet.vn/wp-content/uploads/2019/05/cau-truc-ipv6-banner-700x450-1.png">

# 1.Khái niệm
IPv6 hay còn được gọi trong tiếng Anh là Internet Protocol version 6 là giao thức liên mạng phiên bản 6, là phiên bản thứ 4 trong quá trình phát triển các giao thức Internet (IP). Nó ra đời nhằm khắc phục tình trạng khan hiếm địa chỉ và nhược điểm trong thiết kế IPv4. IPv6 có chiều dài 128 bit và được chia thành 8 nhóm dưới dạng cụm số thập nhị phân.

Địa chỉ IPv6 sẽ có chức năng tương tự với IPv4 nhưng điểm khác IPv6 khác biệt và vượt trội hơn so với IPv4 là dãy số tập hợp các ký tự sẽ dài hơn để đáp ứng cho nhu cầu sử dụng của người dùng ngày càng tăng lên tính đến thời điểm hiện tại.

# 2.Lợi ích khi sử dụng IPv6
- Hỗ trợ các địa chỉ nguồn và đích có độ dài 128bit (16byte)
- Không gian địa chỉ lớn và dễ dàng quản lý hơn so với IPv4
- Sử dụng link-local (địa chỉ giao tiếp nội bộ) trên tất cả các node địa chỉ multicast
- Tự động cấu hình, không cần cấu hình thủ công hoặc sử dụng máy chủ DHCP giúp quản trị TCP/IP dễ dàng hơn
- Hỗ trợ gói tin kích thước tới 1280byte (không phân mảnh)
- Với định tuyến hoàn toàn phân cấp, IPv6 được thiết kế với cấu trúc định tuyến tốt hơn
- Khắc phục khả năng hỗ trợ và mức độ khả dụng multicast tốt hơn so với phiên bản v4
- IPv6 có mức độ bảo mật nâng cao hơn, hỗ trợ bảo mật mạng tốt hơn nữa
- Đáp ứng tốt các nhu cầu về thiết bị di động. Do sự phát triển không ngừng của các thiết bị di động trong thời gian gần đây, các cấu trúc giao thức Internet cũng cần được cải tiến để hỗ trợ tốt hơn. Trong khi đó, thời điểm IPv4 ra đời, khái niệm về thiết bị di động vẫn còn khá xa vời
# 3.Phân loại địa chỉ IPv6
<img src="https://st.quantrimang.com/photos/image/2017/08/17/cac-loai-dia-chi-IPv6.gif">

- Unicast
  - Để phân biệt các Host đơn lẻ trên một mạng người ta sử dụng địa chỉ Unicast. Địa chỉ này lại được chia thành 2 loại là liên kết cục bộ và toàn cục. Unicast liên kết cục bộ chỉ có thể truy cập đến các máy tính được chia sẻ liên kết. Unicast toàn cục lại có khả năng truy cập rộng rãi. Unicast cục bộ và Unicast toàn cục sử dụng định dạng địa chỉ khác nhau
- Anycast
  - Anycast là địa chỉ được sử dụng cho nhiều cổng trên nhiều node khác nhau. Khi thông tin được gửi đến thông qua địa chỉ anycast, thông tin này sẽ được di chuyển một trong số các cổng node đó, thông thường sẽ là cổng gần nhất
- Multicast
  - Địa chỉ Multicast có tác dụng trong việc nhận dạng một nhóm giao diện mạng. Nó được dùng để gửi thông tin đến giao diện mạng thuộc nhóm Multicast. Các địa chỉ Multicast có sự tách biệt với nhau. Giao diện mạng có địa chỉ Multicast không đồng nghĩa với việc nó nằm trong nhóm Multicast  khác hoặc có một địa chỉ Unicast
# 4.Các thành phần IPv6
Mỗi địa chỉ IPv6 gồm có 3 thành phần chính là Site Prefix, Interface ID và Subnet ID. Chúng được nhận dạng bởi vị trí các bit trong một địa chỉ.
- Site Prefix
  - Siet Prefix được biểu thị trong 3 trường đầu tiên. Nó giống như số mạng của IPv4 và được gán đến website bằng một ISP. Trong cùng một vị trí, tất cả các máy tính sẽ được chia sẻ cùng một Site Prefix. Siet Prefix cho phép dùng chung khi nó phát hiện ra mạng của bạn và cho phép truy cập từ internet
- Interface ID
  - Interface ID được biểu thị trong 4 trường cuối. Interface ID được cấu hình (tự động) dựa vào địa chỉ Media Access Control của giao diện mạng. Định dạng EUI-64 có thể được sử dụng để cấu hình cho ID giao diện
- Subnet ID
  - Subnet ID miêu tả cấu trúc trang mạng. Nó làm việc tương tự như cách làm việc của mạng con trong giao thức IPv4. Các mạng đó có thể dài đến 16 byte, được biểu thị trong định dạng Hexadecimal là chủ yếu. IPv6 Subnet giống như nhánh mạng đơn, một Subnet mask của IPv4
# 5.Cấu trúc IPv6
<img src="https://123host.vn/wp-content/uploads/2016/11/86.jpg">

Trong IPV6, thay vì sử dụng một địa chỉ nguồn và đích là 32bit để cung cấp khoảng 4.294.967.296 (232) địa chỉ  như IPv4, địa chỉ IPv6 có chiều dài 128bit, do đó độ dài của IP sẽ lớn hơn,tương đương với việc số địa chỉ được tạo ra từ bội số 128bit sẽ lớn hơn rất nhiều ,có thể lên đến 3.4x1038 địa chỉ.Ngoài ra,có một vài sự khác nhau trong cách biểu diễn địa chỉ của IPv6, một địa chỉ IPv6 thường được viết thành 8 nhóm, mỗi nhóm gồm có 4 số hex và mỗi nhóm được tách biệt với nhau bằng dấu “:”. Ví dụ sau thể hiện điều này 2001:0f68:0000:0000:0000:0000:1986:69af.

## Cấu trúc IPv6 gồm 2 phần:
- Payload: là sự kết hợp của Extension và PDU.Thông thường có thể lên tới 65535 byte.PDU thường bao gồm header của giao thức tầng cao và độ dài của nó, còn Extension là những thông tin liên quan đến dịch vụ kèm theo trong IPv6 được chuyển tới một trường khác và nó có thể có hoặc không.
- IPv6 Header: là thành phần luôn phải có trong một gói tin IPv6 và cố định 40 bytes
  - Version: 4 bits giúp xác định phiên bản của giao thức.
  - Traffic class: 8 bits giúp xác định loại lưu lượng.
  - Flow label: 20 bits giá mỗi luồng dữ liệu.
  - Payload length: 16 bits (số dương).Giúp xác định kích thước phần tải theo sau IPv6 Header.
  - Next-Header: 8 bits giúp xác định Header tiếp theo trong gói  tin.
  - Hop Limit: 8 bits (số dương). Qua mỗi node, giá trị này giảm 1 đơn vị ( giảm đến 0 thì gói bị loại bỏ).
  - Source address: 128 bits mang địa chỉ IPv6 nguồn của gói tin.
 
 Trong mạng máy tính, các chế độ địa chỉ đề cập đến việc lưu trữ một địa chỉ trên mạng. IPv6 cung cấp một số chế độ địa chỉ mà theo đó một máy chủ có thể được xử lý như: Unicast, Multicast và Anycast.
 ## Địa chỉ Unicast
 Trong chế độ địa chỉ unicast, máy chủ được xác định duy nhất trong một phân đoạn mạng. Gói IPv6 chứa cả địa chỉ IP nguồn và đích. Giao diện máy chủ được trang bị một địa chỉ IP duy nhất trong phân khúc mạng đó. Khi bộ chuyển mạch mạng hoặc bộ định tuyến nhận được gói IP unicast thì nó được gửi đến một máy chủ duy nhất.
 
 Địa chỉ unicast gồm có 4 loại khác nhau :
- Global Unicast Address: tương ứng với địa chỉ public của IPv4, là loại địa chỉ được cho phép truy cập rộng rãi trên mạng internet, hỗ trợ cho việc định tuyến và đánh địa chỉ phân cấp.
- Link-Local Address: địa chỉ này luôn được cấu hình một cách tự động trên interface của một thiết bị. Địa chỉ này luôn bắt đầu với FE80. 16 bit đầu tiên của địa chỉ liên kết cục bộ luôn được đặt thành 1111 1110 1000 0000 (FE80). 48 bit tiếp theo được đặt thành 0, do đó nó chỉ được sử dụng để liên lạc giữa các máy chủ IPv6 trên một liên kết (phân đoạn quảng bá). Các địa chỉ này không thể định tuyến, do đó, Bộ định tuyến không bao giờ chuyển tiếp các địa chỉ này bên ngoài liên kết.
- Site-Local Address: tương tự như địa chỉ Private trong IPv4(10.0.0.0/8,172.16.0.0/12 và 192.168.0.0/16), dùng trong nội bộ một Site.
- Unique-Local Address: được sử dụng trong phạm vi toàn cầu, dùng để thay thế cho địa chỉ site-local.
## Địa chỉ Multicast
Chế độ Multicast IPv6 giống như của IPv4. Gói tin được gửi đến nhiều node với một địa chỉ multicast đặc biệt. Tất cả các node quan tâm đến thông tin phát multicast đó, trước tiên cần tham gia nhóm multicast .Toàn bộ các node tham gia nhóm đều sẽ nhận được gói phát multicast này và xử lý nó, trong khi các node khác không quan tâm đến gói phát multicast đó thì bỏ qua.

Địa chỉ multicast cũng có các phạm vi: global, site-local, link-local ngoài ra multicast còn có thêm 2 phạm vi mới đó là organization-local và node-local. Một node IPv6 có thể được gắn rất nhiều địa chỉ.
- Organization-local: được sử dụng trong phạm vi một tổ chức với một số site.
- Node-local: chỉ có tính tương ứng trong phạm vi một node 
## Địa chỉ Anycast
IPv6 đã giới thiệu một loại địa chỉ mới, được gọi là địa chỉ Anycast.Trong chế độ địa chỉ này, nhiều Hosts được gán cùng một địa chỉ IP Anycast. Khi một node muốn liên lạc với một node được trang bị địa chỉ IP Anycast, nó sẽ gửi một tin nhắn Unicast.Tin nhắn này sẽ không được gửi đến tất cả các node trong nhóm giống như Multicast mà với sự trợ giúp của cơ chế định tuyến, thông điệp Unicast đó được gửi đến node gần nhất trong nhóm với người gửi(tính theo thủ tục định tuyến) . 
## Các địa chỉ IPv6 đặc biệt
|       | IPv6 Address | Meaning |
|----|-----|------|
|0:0:0:0:0:0:0:0/128|::/128|Địa chỉ không xác định|
|0:0:0:0:0:0:0:0|::/0|Tuyến đường mặc định|
|0:0:0:0:0:0:0:1/128|::1/128|Địa chỉ Loopback|

Địa chỉ Multicast dành riêng cho giao thức định tuyến
| IPv6 Address | Giao thức định tuyến |
|-----|------|
| FF02 : : 5 | OSPFv3 |
| FF02 : : 6 | OSPFv3 Designated Routers |
| FF02 : : 9 | RIPng |
| FF02 : : A | EIGRP |


