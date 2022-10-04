- Việc kiểm tra log gửi/nhận của email server zimbra là rất cần thiết, giúp xác định được một email đã gửi/nhận thành công hay chưa và nếu chưa thành công thì bị dừng ở bước nào và báo lỗi ra sao.

- Đường dẫn file log
```
/var/log/maillog
```
- Chu trình gửi: Khi click gửi thư => `Connect` tới `email server` => MTA kiểm tra địa chỉ người nhận => Kiểm tra qua các `rule filter`, đánh giá `spam, virus` => Xếp vào `queue` => Gửi thư => Xóa khỏi `queue` => Thông báo `Message accepted for delivery`
