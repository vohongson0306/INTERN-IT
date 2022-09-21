<img src="https://d1iv5z3ivlqga1.cloudfront.net/wp-content/uploads/2021/12/02152006/mongoDB-la-gi.png">

# 1.Khái niệm
- MongoDB là phần mềm cơ sở dữ liệu mã nguồn mở NoSQL hỗ trợ đa nền tảng được thiết kế theo hướng đối tượng. Bảng (collection) có cấu trúc linh hoạt cho phép dữ liệu không cần tuân theo dạng cấu trúc nào.

- Vì thế nó dùng để lưu trữ dữ liệu có cấu trúc phức tạp và đa dạng. Dữ liệu đó gọi là big data, đặc biệt chương trình này lưu trữ dữ liệu vào collection theo hướng tài liệu kiểu json thay vì bảng nên có hiệu suất cao và tính khả dụng cao.





# Ưu điểm của MongoDB
- Đầu tiên có thể nhắc đến là tính linh hoạt lưu trữ dữ liệu theo các kích cỡ khác nhau, dữ liệu dưới dạng hướng tài liệu JSON nên bạn có thể chèn vào thoải mái bất cứ thông tin gì bạn muốn.
- Khác với RDBMS, dữ liệu trong đây không có sự ràng buộc và không có yêu cầu tuân theo khuôn khổ nhất định, điều này giúp bạn tiết kiệm thời gian cho việc kiểm tra sự thỏa mãn về cấu trúc nếu muốn chèn, xóa, cập nhật hay thay đổi các dữ liệu trong bảng.
- MongoDB dễ dàng mở rộng hệ thống bằng cách thêm node vào cluster – cụm các node chứa dữ liệu giao tiếp với nhau.
- Ưu điểm thứ tư là tốc độ truy vấn nhanh hơn nhiều so với hệ quản trị cơ sở dữ liệu quan hệ RDBMS do dữ liệu truy vấn được cached lên bộ nhớ RAM để lượt truy vấn sau diễn ra nhanh hơn mà không cần đọc từ ổ cứng.
- Cũng là một ưu điểm về hiệu suất truy vấn của MongoDB, trường dữ liệu “_id” luôn được tự động đánh chỉ mục để đạt hiệu suất cao nhất.
# Nhược điểm của MongoDB là gì?
- Dữ liệu trong MongoDB không bị ràng buộc như RDBMS nhưng người sử dụng lưu ý cẩn thận mọi thao tác để không xảy ra các kết quả ngoài ý muốn gây ảnh hưởng đến dữ liệu.
- Một nhược điểm mà “dân công nghệ” hay lo ngại là bộ nhớ của thiết bị. Chương trình này thường tốn bộ nhớ do dữ liệu được lưu dưới dạng key-value, trong khi các collection chỉ khác về value nên sẽ lặp lại key dẫn đến thừa dữ liệu.
- Thông thường, dữ liệu thay đổi từ RAM xuống ổ cứng phải qua 60 giây thì chương trình mới thực hiện hoàn tất, đây là nguy cơ bị mất dữ liệu nếu bất ngờ xảy ra tình huống mất điện trong vòng 60 giây đó.



