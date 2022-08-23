<img src="https://fptcloud.com/wp-content/uploads/2022/02/ssh-la-gi.png">

# 1.Khái niệm
SSH viết đầy đủ là Secure Shell, đây là một giao thức hỗ trợ các nhà quản trị mạng truy cập vào máy chủ từ xa thông qua mạng internet không bảo mật. Ngoài ra, SSH còn cung cấp các bộ tiện ích phục vụ phát triển chính giao thức SSH.

SSH tạo ra cơ chế xác thực qua mật khẩu mạnh, hình thành mối liên kết giao tiếp dữ liệu mã hóa ra giữa hai máy qua môi trường internet. Ngày nay giao thức SSH được giấy quản trị mạng sử dụng phổ biến trong quá trình quản lý, điều chỉnh ứng dụng từ xa. Nó cho phép vị tự đăng nhập vào mạng máy tính và thực hiện một số tác vụ cơ bản như dịch chuyển file.
# 2.Chức năng chính
iao thức đảm nhiệm khá nhiều chức năng trong hệ thống điều khiển, liên kết máy chủ. Các chức năng cơ bản phải kể đến như:

- Hỗ trợ truy cập từ xa vào những hệ thống, thiết bị ứng dụng giao thức SSH.
- Cho phép dịch chuyển file an toàn.
- Thực thi lệnh bảo mật, an toàn trên hệ thống điều khiển từ xa.
- Quản lý an toàn và hiệu quả thành phần hạ tầng mạng.

SSH có thể kết hợp với Terminal Session thay thế cho những chương trình Telnet có tính bảo mật thấp.
# 3.Kỹ thuật mã hóa trong SSH
Ưu điểm lớn nhất của SSH nằm ở khả năng mã hóa, truyền tải dữ liệu an toàn giữa thành phần Host và Client. Trong đó, Host chính là máy chủ từ xa cần liên kết với máy tính Client. Kỹ thuật mã hóa thông qua SSH có thể triển khai theo 3 phương thức khác nhau.
## Mã hóa Symmetric Encryption
Symmetric Encryption chính là một phương thức mã hóa ứng dụng Secret Key theo hai chiều, giải mã tin cho Host và Client. Như vậy, bất kỳ ai sở hữu mã khóa đều có khả năng giải mã tin nhắn trong quá trình truyền tin.

<img src="https://fptcloud.com/wp-content/uploads/2022/02/Mo-ta-qua-trinh-ma-hoa-theo-phuong-thuc-Symmetric-Encryption.jpg">

Symmetric Key được ứng dụng để mã hóa hoàn toàn phiên giao dịch diễn ra trong giao thức SSH. Trong đó, Host và Client có nhiệm vụ tạo Key bí mật, tuyệt đối không để lộ cho bên thứ ba.

Chính bởi Key không truyền tải giữa Client và Host nên thuật toán rất bảo mật. Cả hai máy tính có thể chia sẻ thông tin chung, ứng dụng chúng xác định mã Key bí mật. Bất kỳ máy tính khác có thể nắm bắt thông tin hay không, chúng cũng không dò được mã khóa bí mật.

Tuy nhiên cũng cần lưu ý rằng, Secret Token chỉ có thời hạn sử dụng trong một phiên SSH, nó hình thành từ chứng thực Client. Khi tạo mới Key, toàn bộ Packets giữa hai máy cần trải qua mã hóa bởi Private Key. Quá trình này gồm cả bước cung cấp mật khẩu bởi người dùng.
Symmetric Encryption chính là một phương thức mã hóa ứng dụng Secret Key theo hai chiều, giải mã tin cho Host và Client. Như vậy, bất kỳ ai sở hữu mã khóa đều có khả năng giải mã tin nhắn trong quá trình truyền tin.

## Mã hóa Asymmetric Encryption
<img src="https://fptcloud.com/wp-content/uploads/2022/02/Mo-ta-cach-thuc-ma-hoa-theo-phuong-thuc-Asymmetric-Encryption.jpg">
Khác với Symmetric Encryption, phương thức Asymmetric Encryption lại dùng 2 khóa riêng biệt để phục vụ mã hóa và giải mã. Bao gồm khóa công khai Public Key và khóa riêng tư Private Key, hình thành cặp khóa Public-private key pair.

## Mã hóa Hashing
<img src="https://fptcloud.com/wp-content/uploads/2022/02/Hashing-phuong-thuc-ma-hoa-ung-dung-pho-bien-trong-Secure-Shell-Connection.jpg">

Hashing một chiều là phương thức mã hóa ứng dụng phổ biến trong Secure Shell Connection. Khác với Symmetric Encryption và Asymmetric Encryption, Hashing không sử dụng vào mục đích giải mã. Chúng hình thành sau mỗi lần nhập liệu, không thể khai thác. Như vậy, Hashing sẽ không thể quay lại để giải mã.

Thông thường, để tạo ra một mật mã Hash rất đơn giản qua một lần Input. Thế nhưng chúng ta lại không thể tạo ra Input thông qua chính lần Hash đó. Nói cách khác, Client đang giữ Input đó. Điều này có nghĩa chỉ Client có thể tạo một crypto-graphic hash để tiến hành xác định hai bên nhập Input.

Giao thức SSH cần đến Hash để kiểm tra tính xác thực của tin nhắn. Quy trình xác thực này đảm bảo rằng lệnh không thể giả danh bởi bất cứ phương thức nào.



