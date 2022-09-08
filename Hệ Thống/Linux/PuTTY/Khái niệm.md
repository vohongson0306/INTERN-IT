<img src="https://media.bkns.vn/uploads/2020/03/putty-la-gi.jpg">

# 1.Khái niệm:
PuTTY là phần mềm giúp người dùng kết nối, quản lý và điều khiển các server thông qua mạng internet. Cơ sở xây dựng và phát triển PuTTY là gì? Ban đầu, PuTTY là giao diện đầu cuối Client chỉ hỗ trợ một vài giao thức mạng bao gồm SCP, SSH, Telnet, Rlogin… dành riêng cho hệ điều hành Windows.
# 2.Tính năng của PuTTY
- Hỗ trợ cho hệ điều hành Windows 32 bit và 64 bit.
- Dễ dàng kết nối, điều khiển nhiều máy tính trong cùng phạm vi. Đồng thời cũng thuận lợi cho việc truyền nhận dữ liệu giữa chúng.
- Cung cấp cho người dùng trình điều khiển các SSH với khóa mã hóa, các giao thức như SSH2, SSH1, thuật toán mã hóa thay thế như 3DES, Arcfour, Blowfish, DES và khóa công khai xác thực.
- Hỗ trợ xác thực Public key và Active Directory/Kerberos.
- Sử dụng một chương trình câu lệnh riêng biệt để chuyển giao file mà không cần tích hợp các hỗ trợ chuyển file.
- Không hỗ trợ script nhưng có thể sử dụng kết hợp với WinSCP.
- Có thể được sử dụng với kết nối cổng nối tiếp trong hệ thống mạng LAN.
# 3.Các thành phần cấu trúc của PuTTY
- PuTTY: gồm các Telnet, Rlogin, SSH Client, tất cả có thể kết nối với một cổng nối tiếp.
- PSCP: là dòng lệnh sao chép tập tin an toàn, còn có tên gọi khác là SCP khách.
- PSFTP: phiên chuyển tập tin chung giống với FPT, chính là một SFTP khách hàng.
- PuTTYtel: là khách hàng Telnet.
- Plink: là giao diện dòng lệnh để PuTTY lại đầu.
- Pageant: là đại lý SSH cho PuTTY, PSCP và Plink.
- PuTTYgen: là RSA và DSA tiện ích quan trọng.
# 4.Phân tích một số đặc tính PuTTY cơ bản
## Cửa sổ giao diện
Giao diện luôn là yếu tố đầu tiên thu hút và để lại ấn tượng với người dùng. Vì thế, cửa sổ giao diện là tính năng cơ bản của PuTTY. Trong phần mềm PuTTY, mô phỏng giao diện được đánh giá cao là giao diện có cấu hình tốt, hỗ trợ cho các thuật toán mã hóa, các giao thức SSH, Telnet và giao thức TCP/IP đơn giản.

## Chuyển giao file
Các thành phần PSFTP hay PSCP được cung cấp và sử dụng phục vụ quá trình chuyển giao file. PSFTP là giao thức mà người sử dụng có thể tải dữ liệu trên máy chủ giúp bảo vệ thông tin và mã hóa các lệnh; còn PSCP là phương thức liên lạc và gửi tệp từ xa được bảo mật bằng giao thức SSH, cho phép chuyển tập tin mà không rò rỉ thông tin.

Bên cạnh đó, người dùng còn sử dụng WinSCP và FileZilla kết hợp với PuTTY để truyền file, nhưng hai phần mềm này yêu cầu bạn đăng nhập mới có thể thực hiện chuyển giao file.

## Xác minh public key
Ở đặc tính này, người dùng sử dụng công cụ PuTTYgen để tạo khóa mới, chuyển đổi giữa các tệp .ppk lưu trữ khóa SSH và các định dạng khóa khác. Việc quản lý các khóa SSH để tránh bị xâm nhập và thu thập bởi các phần mềm độc hại là rất quan trọng đối với người sử dụng. Vì thế, chúng tôi đưa ra giải pháp tối ưu nhất để quản lý khóa SSH và duy nhất hỗ trợ các tệp .ppk là cài đặt Universal SSH Key Manager trên máy tính của bạn.

## Hỗ trợ Telnet
PuTTY hỗ trợ giao thức Telnet vì nó được phát triển từ một Telnet client. Tuy nhiên, giao thức Telnet thường đánh mất tên và mật khẩu của người dùng. Chính vì lý do đó mà giao thức SSH ra đời để giải quyết. Tại một số quốc gia không cho phép sử dụng mã hóa, phần mềm hiện đã sử dụng công cụ PuTTYtel. Mặt khác, hiện nay hầu hết các quốc gia đều sử dụng SSH để đề phòng các nguy cơ về bảo mật từ Telnet.

## Lỗ hổng an ninh của PuTTY là gì?
### Đặc tính cơ bản cuối cùng chúng tôi đề cập trong bài viết này là các lỗ hổng an ninh, cụ thể như sau:
   - Tràn bộ nhớ đệm: là lỗ hổng mã từ xa có thể dẫn đến một truy nhập bộ nhớ máy tính và chương trình bị kết thúc, người sử dụng có thể lợi dụng lỗ hổng này để phá vỡ an ninh hệ thống.
   - Tràn số nguyên trong xử lý thoát chuỗi thiết bị đầu cuối: là lỗ hổng mã từ xa và lỗi bộ nhớ có liên quan đến việc gửi chuỗi thoát đến thiết bị đầu cuối, đây là một công cụ máy chủ lợi dụng thực thi mã và ảnh hưởng an ninh trên máy khách.
