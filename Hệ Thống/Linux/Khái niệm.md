<img src="https://freetuts.net/upload/tut_post/images/2015/06/26/423/linux-la-gi.JPG">

# Khái niệm 
Linux là một hệ điều hành máy tính mã nguồn mở, cách hoạt động giống như các hệ điều hành khác như: Microsoft Windows, Apple Mac OS, iOS, Google android ... Đây là một HĐH sử dụng cả giao diện GUI và command line.

Nhiệm vụ của Linux là cho phép giao tiếp giữa phần cứng và phần mềm máy tính, xử lý tiếp nhận thông tin đầu vào và trả kết quả ra màn hình, đây chính là chứ năng cơ bản nhất của một hệ điều hành.

# Cấu trúc hệ điều hành linux
<img src="https://freetuts.net/upload/tut_post/images/2015/06/26/423/cau-truc-linux.png">

## Kernel 
Kernel chính là phần nhân của linux, là thành phần quan trọng nhất và có nhiệm vụ thiết lập giao tiếp giữa các phần mềm và thiết bị phần cứng. Hơn thế nữa, nó còn đảm nhận việc quản lý tài nguyên của hệ thống.

Nó có bốn nhiệm vụ chính như sau:
- Quản lý thiết bị: Một máy tính sẽ có nhiều thiết bị như CPU, RAM, card âm thanh, card đồ họa, v.v. kernel sẽ lưu trữ tất cả dữ liệu liên quan đến tất cả các thiết bị trong trình điều khiển thiết bị driver (nếu không có kernel thì sẽ không thể để điều khiển các thiết bị). Do đó kernel biết mỗi thiết bị có thể làm gì và thao tác với nó như thế nào để mang lại hiệu suất tốt nhất.
- Quản lý bộ nhớ: Một chức năng khác đó là quản lý bộ nhớ. Kernel theo dõi bộ nhớ đã sử dụng và chưa sử dụng và đảm bảo rằng các tiến trình không được sử dụng dữ liệu của nhau bằng địa chỉ bộ nhớ ảo.
- Quản lý quy trình: Kernel chỉ định đủ thời gian và ưu tiên cho các quy trình trước khi CPU xử lý cho các quy trình khác.
- Xử lý lệnh gọi hệ thống: Xử lý lệnh gọi hệ thống có nghĩa là một lập trình viên có thể viết một truy vấn hoặc yêu cầu Karnel thực hiện một tác vụ nào đó.

## System Libraries
System Libraries là những thư viện / phần mềm đặc biệt giúp truy cập vào các tính năng của Karnel. Mỗi Karnel sẽ phải được kích hoạt để thực hiện một tác vụ các ứng dụng sẽ hoàn thành những tác vụ đó.

## System Tools
Hệ điều hành Linux có một tập hợp các công cụ tiện ích, thường là các lệnh command line đơn giản. Nó là một phần mềm mà dự án GNU đã viết và xuất bản theo giấy phép mã nguồn mở của họ, nhằm giúp phần mềm cung cấp miễn phí cho tất cả mọi người.

Với sự trợ giúp của các lệnh, bạn có thể truy cập file của mình, chỉnh sửa và thao tác dữ liệu trong thư mục hoặc file của bạn, thay đổi vị trí của file hoặc bất cứ một thao tác nào khác.
## Development Tools
Với ba thành phần trên là hệ điều hành Linux có thể hoạt động được rồi đấy. Nhưng nhằm giúp các nhà phát triển có thể cập nhật hệ thống, cũng như tạo ra những công cụ khác thì Linux cho phép lập trình viên sử dụng những công cụ riêng của nó, ta gọi là toolchain.

## End User Tools
Đây chính là tập hợp những phần mềm mà người dùng cài vào máy tính để sử dụng như: Trình duyệt web, phần mềm nghe nhạc, office ...
