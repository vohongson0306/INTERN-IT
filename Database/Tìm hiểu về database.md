# 1.Khái niệm
- Database hay còn được gọi là cơ sở dữ liệu và chúng thường được lưu trữ trực tuyến trong một hệ thống máy tính và có chức năng tập hợp các thông tin có cấu trúc hoặc dữ liệu. Hệ thống quản lý cơ sở dữ liệu (DBMS) sẽ có nhiệm vụ kiểm soát cơ sở dữ liệu database.
- Mô hình dữ liệu được sử dụng phổ biến trong các loại cơ sở dữ liệu để giúp xử lý và truy vấn dữ liệu hiệu quả là mô hình hóa theo hàng và cột trong một loạt các bảng. Ngôn ngữ được sử dụng để viết và truy vấn dữ liệu trong các cơ sở dữ liệu hầu hết có cấu trúc (SQL).
- Bạn có thể hiểu đơn giản, đặc điểm chính của Database chính là truy xuất ra những thông tin, dữ liệu bằng nhiều phương thức khác nhau và nội dung truy xuất được đảm bảo toàn vẹn dữ liệu ở mức độ cao.
# 2. Phân loại Database theo mục đích sử dụng
  ## Database dạng file
   Đây là dạng Database được sử dụng phổ biến nhất, đúng với cái tên của nó dữ liệu ở dạng này thường được lưu trữ dưới dạng các file. Các dạng phổ biến thường dùng là: *.mdb Foxpro, một số định dạng file khác là text, ascii, *.dbf.
  ## Database quan hệ
   Đây là dạng dữ liệu (thực thể) khác nhau được lưu trữ trong các bảng dữ liệu.  Giữa các thực thể này có mối liên hệ với nhau gọi là các quan hệ với nhau. Các hệ quản trị hỗ trợ database quan hệ nổi tiếng có thể kể đến: MS SQL server, Oracle, MySQL…
  ## Database hướng đối tượng
   Đây là dạng dữ liệu cũng được lưu trữ trong các bảng dữ liệu. Điều khác biệt là  các bảng có bổ sung thêm các tính năng hướng đối tượng như lưu trữ thêm các hành vi, nhằm thể hiện hành vi của đối tượng. Mỗi bảng xem như một lớp dữ liệu. Một dòng dữ liệu trong bảng là một đối tượng. Các hệ quản trị có hỗ trợ database hướng đối tượng như: MS SQL server, Oracle, Postgres SQL
  ## Database bán cấu trúc
  Đây là dạng dữ liệu được lưu dưới định dạng XML, các thông tin mô tả dữ liệu, đối tượng được trình bày trong các thẻ tag. Với ưu điểm lưu trữ được hầu hết các loại dữ liệu khác nhau, database bán cấu trúc là hướng mới trong nghiên cứu và ứng dụng về cơ sở dữ liệu.
# 3. Lợi ích khi sử dụng Database
Nhắc đến Database không thể không kể đến những lợi ích tuyệt vời mà chúng mang lại, cụ thể như:
## Đảm bảo an toàn dữ liệu
- Database xứng đáng nhận “điểm 10” về độ an toàn dữ liệu. Đảm bảo toàn vẹn và an toàn dữ liệu là điểm quan trọng hàng đầu trong công tác lưu trữ dữ liệu.
- bạn nên sử dụng cách lưu ra File .xml và file .csv, Nếu muốn lưu dữ liệu ra file text. Khi lưu ra hai loại file bạn hoàn toàn có thể chuyển đổi vào database dễ dàng và an toàn.
## Lưu trữ thông tin có hệ thống
- Database giúp người dùng thuận tiện trong việc tạo lập, lưu trữ, tìm kiếm và sử dụng dữ liệu một cách chính xác và nhanh chóng vì cấu trúc sắp xếp có tính hệ thống.
- Dữ liệu  sẽ được lưu trữ theo một cấu trúc nhất định , có tính nhất quán cao, đây là điều làm nên sự khác biệt lớn nhất giữa dữ liệu thông thường và cơ sở dữ liệu database.
## Công tác quản lí dễ dàng hơn
- Một database được thiết kế nhầm hỗ trợ trong việc tạo lập, cập nhập và khai thác thông tin được dễ dàng hơn. Dữ liệu sẽ được cập nhật thường xuyên và hoàn toàn không trùng lặp. Sử dụng database giúp tạo ra các sản phẩm chuyên nghiệp hơn, lưu trữ có hệ thống, dễ dàng trong công tác quản lí.
- Với ưu điểm đó, database ngày càng phổ biến trong lĩnh vực lập trình ứng dụng nói riêng và công nghệ thông tin nói chung.
## Đảm bảo khả năng truy xuất đồng thời
   Nhiều người có thể sử dụng database cùng lúc mà không phải qua các khâu rườm rà phức tạp nhờ vào việc truy xuất từ các cách khác nhau.  Do đó, bạn sẽ gặp nhiều thuận lợi trong việc  việc  sử dụng, quản lý, truy cập dữ liệu,…

## Linh hoạt thay đổi theo nhu cầu của người dùng
- Bạn có thể linh hoạt thay đổi kích cỡ và độ phức tạp của một database.  Có những database chỉ gồm vài trăm bản ghi (danh sách học sinh của một lớp) và có những database có dung lượng rất lớn (như database quản lí hàng hoá của một hệ thống siêu thị).
- Song song đó, hình thức lưu trữ database  cũng khá đa dạng. Database có thể được lưu trữ dưới nhiều dạng khác nhau như ổ cứng, USB hay đĩa CD.
# 4. ứng dụng của database:
- Hệ thống cơ sở dữ liệu đóng vai trò vô cùng quan trong trong thời đại thông tin – kỹ thuật như hiện nay. Chức năng chính của Database có thể kể đến là: lưu trữ, truy xuất và cập nhật dữ liệu cùng nhiều ứng dụng khác.
- Database giúp quản lý các dịch vụ bảo mật và phục hồi hệ thống quản trị dữ liệu, giúp thực thi các ràng buộc bên trong hệ cơ sở này. Đồng thời, quản lý và kiểm soát tất cả các máy khách kết nối, truy cập vào hệ thống dữ liệu ở hệ thống nguồn. Hỗ trợ xử lý tất cả các truy cập dữ liệu và các chức năng điều khiển khác.
- Ngoài ra, Database còn cung cấp tính năng kiểm soát đồng thời, giúp bảo mật chặt chẽ hơn. Tạo môi trường đa người dùng với điều kiện kết nối an toàn. Nhiều người có thể truy cập đồng thời và truy xuất được những dữ liệu cần thiết
















