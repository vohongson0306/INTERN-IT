# Giám sát (monitor) hệ thống mạng

Đối với các cơ sở hạ tầng mạng, hệ thống giám sát an toàn mạng là vô cùng quan trọng, nhất là đối với các tổ chức, tập đoàn, doanh nghiệp. Ngoài ra, hệ thống giám sát an toàn mạng phát hiện kịp thời các tấn công mạng, các điểm yếu, lỗ hổng bảo mật của các thiết bị, ứng dụng và dịch vụ trong hệ thống. Phát hiện kịp thời sự bùng nổ virus trong hệ thống mạng, các máy tính bị nhiễm mã độc, các máy tính bị nghi ngờ là thành viên của mạng máy tính ma (botnet).

## 1. Các yếu tố cốt lõi trong giám sát mạng

Nhằm mang lại hiệu quả cao cho việc giám sát mạng, chúng ta cần nắm vững các yếu tố cốt lõi đặc thù của công việc này. Cụ thể bao gồm:

- Nắm vững những công cụ, thiết bị, phần mềm phục vụ cho công việc giám sát, trong đó bao gồm phần mềm nội bộ và phần mềm mở
- Nắm vững những bộ phận, đơn vị, hệ thống, dịch vụ và thiết bị phục vụ cho việc giám sát
- Sử dụng một cách bài bản những công cụ, giải pháp hỗ trợ việc xử lý, phân tích kết quả giám sát. Một số công cụ như Snort, Wireshark, Nessus, Nmap…
- Đảm bảo nhân viên có kiến thức tốt về lĩnh vực này

## 2. Các thành phần trong hệ thống mạng

Vì là một hệ thống mạng toàn diện nên việc giám sát an toàn mạng rất quan trọng, yêu cầu bạn phải nắm được nhưng thành phần trong hệ thống như:
- Server – máy chủ
- Các thiết bị hạ tầng mạng như: Hub, Router, switch.
- Máy trạm, mô hình máy trạm
- Các thiết bị và hệ thống phục vụ cho việc theo dõi hệ thống mạng
- Phần mềm và ứng dụng trong máy trạm, máy chủ.

## 3. Lợi ích của một hệ thống giám sát an toàn mạng

- Bản chất của SIEM hay còn gọi Security information and event management được tạo ra với mục đích chính là thu thập các dữ liệu, thông tin về những sự kiện an ninh. Nó được tính từ những thiết bị đầu cuối cho tới lưu dữ liệu tập trung. nhờ vào kết quả phân tích của công cụ hệ thống an toàn mạng, chúng ta có thể phát hiện ra những nguy cơ trước sự tấn công của tin tặc.

- Lợi ích chính của hệ thống giám sát an ninh mạng là:
  - Giúp việc quản lý được tập trung hơn
  - SIEM có thể phát hiện ra các sự cố tấn công, thâm nhập mạng mà những thiết bị thông thường khó lòng phát hiện được.
  - Giúp việc xử lý sự cố đơn giản mà lại hiệu quả hơn

## 4. Thu thập dữ liệu cho hệ thống

- Thu thập dữ liệu, thông tin về tình trạng và lịch sử hoạt động của các thiết bị trong cùng một hệ thống mạng nội bộ. Chính vì mỗi hệ thống lại có những thành phần khác nhau, nền tảng khác nhau. Do đó “Log” được đưa về trung tâm xử lý và phân tích.
- Sau khi kết thúc quá trình phân tích, xử lý, các thông tin, tệp, dữ liệu thu thập được sẽ giúp nhà quản trị đưa ra những kế hoạch phòng tránh hoặc khắc phục khỏi nguy cơ tấn công.

## 5. Các giải pháp tăng cường cho hệ thống mạng

Có 3 giải pháp chính giúp hệ thống giám sát được an toàn bao gồm:

- Giải pháp quản lý và phân tích sự kiện an ninh: là sự kết hợp của cả hai giải pháp trên nhằm khắc phục những hạn chế vốn có. Vì vậy, tài liệu sẽ hướng tới xây dựng giải pháp này.
- Giải pháp quản lý thông tin an ninh: tập trung vào việc thu thập, lưu trữ nhật ký.
- Giải pháp quản lý sự kiện an ninh: tập trung vào việc phân tích và xử lý các nhật ký đã được thu thập để đưa ra cảnh báo cho người dùng.
