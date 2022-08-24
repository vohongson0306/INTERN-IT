# 1.Khái niệm
- Ảo hóa là công nghệ cho phép khai thác triệt để khả năng hoạt động của các phần cứng trong hệ thống máy chủ bằng cách chạy đồng thời nhiều OS trên cùng lớp vật lý.
- Cùng chia sẻ tài nguyên phần cứng và được quản lý bởi lớp ảo hóa (Hypervisor).
- Lớp ảo hóa nằm giữa như một tầng trung gian giữa phần cứng (hardware) và phần mềm hệ điều hành (OS) giúp quản lý, phân phát tài nguyên phần cứng cho lớp OS ảo hoạt động ở trên.
# 2.Các thành phần của một hệ thống ảo hóa
<img src="https://thegioimaychu.vn/blog/wp-content/uploads/2019/12/tgmc-blog-5e033a0c0b66d.png">

- Tài nguyên vật lý chính (Host machine / Host hardwave): Máy chủ vật lý, CPU, RAM, ổ đĩa cứng, card mạng… Nhiệm vụ là chia tài nguyên cấp cho các máy ảo.
- Phần mềm ảo hóa (Hypervisor): cung cấp truy cập cho mỗi máy chủ ảo đến tài nguyên của máy chủ vật lý, lập kế hoạch và phân chia tài nguyên vật lý cho các máy chủ ảo, cung cấp giao diện quản lý cho các máy chủ ảo
- Hệ điều hành khách (Guest Operating System): được cài đặt trên một máy chủ ảo, thao tác như ở trên hệ điều hành thông thường.
- Mảy ảo (Virtual Machine): nó hoạt động như một máy chủ vật lý thông thường với tài nguyên riêng, giao diện riêng, hệ điều hành riêng.
# 3.Mục tiêu của ảo hóa
Ảo hóa xoay quanh 4 mục tiêu chính: Availability, Scalability, Optimization, Management.
- Availability: giúp các ứng dụng hoạt động liên tục bằng cách giảm thiểu (bỏ qua) thời gian chết (downtime) khi phần cứng gặp sự cố, khi nâng cấp hoặc di chuyển.
- Scalability:  khả năng tùy biến, thu hẹp hay mở rộng mô hình server dễ dàng mà không làm gián đoạn ứng dụng.
- Optimization: sử dụng triệt để nguồn tài nguyên phần cứng và tránh lãng phí bằng cách giảm số lượng thiết bị vật lý cần thiết (giảm số lượng server, switch, cáp, v.v. )
- Management: khả năng quản lý tập trung, giúp việc quản lý trở nên dễ dàng hơn bao giờ hết.
# 4.Ưu điểm và nhược điểm của ảo hóa
## Ưu điểm
- Tiết kiệm năng lượng tiêu thụ, giảm chi phí duy trì server (tiền điện để chạy và làm mát server)
- Giảm số lượng thiết bị vật lý cần thiết (giảm số lượng server, switch, cáp, phí gia công)
- Tận dụng tối đa nguồn tài nguyên, tránh lãng phí.
- Quản lý tập trung, liên tục, nâng cao hiệu quả làm việc của quản trị viên.
- Khả năng mở rộng dể dàng

## Nhược điểm.
- Thông thường, mỗi máy ảo chỉ sử dụng một file VMDK (file này có thể được chia nhỏ tùy theo cách cài đặt) để lưu lại toàn bộ dữ liệu trong máy ảo và một số file nhỏ khác để lưu cấu hình máy ảo. Do đó, nếu một trong số những tệp tin bị lỗi hoặc bị mất mà chưa được backup thì có thể xem như máy ảo đã bị hư hoàn toàn và không thể phục hồi.
- Ngoài ra nếu máy chủ có cấu hình phần cứng thấp nhưng lại có một máy ảo sử dụng quá nhiều tài nguyên hoặc chạy quá nhiều máy ảo sẽ làm chậm toàn bộ hệ thống bao gồm các máy ảo và các ứng dụng chạy trên máy ảo. Đồng thời do một hoặc vài máy chủ phải đảm nhận nhiều máy ảo chạy trên nó nên máy chủ gặp trục trặc, sự cố thì các máy ảo cũng sẽ bị ảnh hưởng theo.
- Còn ở góc độ bảo mật, nếu hacker nắm quyền điều khiển một máy chủ vật lý chứa các máy ảo thì hacker có thể kiểm soát được tất cả các máy ảo trong nó.
