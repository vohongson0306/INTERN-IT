<img src="https://bkhost.vn/wp-content/uploads/2022/08/tuong-lua-fire-wall-la-gi-e1660551886843.jpg">

# 1.Khái niệm
Firewall hay còn được gọi là Tường lừa - là một kỹ thuật được tích hợp vào hệ thống mạng để chống sự truy cập trái phép, nhằm bảo vệ các nguồn thông tin nội bộ và hạn chế sự xâm nhâp không mong muốn vào hệ thống. Firewal sử dụng các quy tắc để kiểm soát traffic vào, ra khỏi hệ thống hoạt động như một rào chắn giữa mạng an toàn và mạng không an toàn. Nó kiểm soát các truy cập đến nguồn lực của mạng thông qua một mô hình kiểm soát chủ động. Nghĩa là, chỉ những traffic phù hợp với chính sách được định nghĩa trong tường lửa mới được truy cập vào mạng, mọi traffic khác đều bị từ chối.

# 2.Chức năng của Firewall
Chức năng chính của Firewall là kiểm soát luồng thông tin từ giữa Intranet và Internet. Thiết lập cơ chế điều khiển dòng thông tin giữa mạng bên trong (Intranet) và mạng Internet.

- Cho phép hoặc cấm những dịch vụ truy cập ra ngoài.
- Cho phép hoặc cấm những dịch vụ từ ngoài truy cập vào trong.
- Theo dõi luồng dữ liệu mạng giữa Internet và Intranet.
- Kiểm soát địa chỉ truy nhập, cấm địa chỉ truy nhập
- Kiểm soát người sử dụng và việc truy cập của người sử dụng.
- Kiểm soát nội dung thông tin lưu chuyển trên mạng.

# 3.Ưu điểm và hạn chế của Firewall
## 3.1.Ưu điểm:
- Bảo vệ hệ thống bởi các tấn công (bên trong, bên ngoài).
- Lọc kết nối dựa trên nội dung dữ liệu.
- Thực thi NAT.
- Kết hợp được với hệ thống IDS/IPS.
- Thành phần trong giải pháp phòng thủ theo chiều sâu.
## 3.2.Hạn chế:
- Các tấn công ở lớp ứng dụng có thể bị bỏ qua.
- Các kết nối: Dial-up, VPN có thể vượt firewall.
- Quản lý vận hành tương đối phức tạp.
- Tồn tại các điểm yếu nội tại.
- Ảnh hưởng đến tốc độ kết nối.
# 4. phân loại:
## Packet-Filtering Firewall
- Là kiểu kiến trúc firewall cơ bản nhất và lâu đời nhất, về cơ bản tạo một trạm kiểm soát tại một router hoặc switch. Firewall thực hiện kiểm tra đơn giản các gói dữ liệu đi qua router, kiểm tra thông tin như địa chỉ IP đích và nguồn, loại gói tin (packet), số port và các thông tin khác mà không cần mở packet để kiểm tra nội dung của nó.
- Nếu gói thông tin không vượt qua kiểm tra, nó sẽ bị loại bỏ.
- Lợi ích của loại Firewall này là không sử dụng nhiều tài nguyên. Điều này có nghĩa là Firewall không có tác động lớn đến hiệu suất hệ thống và tương đối đơn giản.
## Circuit-Level Gateways
- Firewall này là một loại firewall đơn giản, nhanh chóng và dễ dàng chấp nhận hoặc từ chối lưu lượng truy cập mà không tiêu tốn nhiều tài nguyên máy tính, circuit-level gateways hoạt động bằng cách xác minh giao thức TCP handshake. Kiểm tra TCP handshake này được thiết kế để đảm bảo session mà gói dữ liệu (packet) đến là hợp lệ.
- Mặc dù cực kỳ tiết kiệm tài nguyên, nhưng các firewall này không tự kiểm tra gói tin. Vì vậy, nếu một gói chứa phần mềm độc hại, nhưng có giao thức TCP handshake phù hợp, nó sẽ đi qua ngay. Đây là lý do tại sao circuit-level gateways không đủ để tự bảo vệ doanh nghiệp của bạn.
## Stateful Inspection Firewall
- Loại firewall này kết hợp cả công nghệ kiểm tra gói tin và xác minh TCP handshake để tạo ra một mức độ bảo vệ tốt hơn một trong hai loại firewall trên.
- Tuy nhiên, những firewall này sử dụng khá nhiều tài nguyên của máy tính. Điều này có thể làm chậm quá trình truyền các gói tin phù hợp so với các giải pháp khác.
## Proxy Firewalls (Application-Level Gateways/Cloud Firewalls)
- Proxy firewall hoạt động ở lớp ứng dụng để lọc lưu lượng đến giữa mạng của bạn và nguồn lưu lượng. Do đó, loại firewall này cũng được gọi là application-level gateway. Các firewall này được phân phối thông qua một giải pháp dựa trên cloud hoặc một thiết bị proxy khác. Thay vì để lưu lượng kết nối trực tiếp, Proxy firewall thiết lập kết nối trước với nguồn lưu lượng và kiểm tra gói dữ liệu đến.
- Việc kiểm tra này tương tự như Stateful Inspection Firewall ở chỗ nó xem xét cả gói tin và giao thức TCP handshake. Tuy nhiên, Proxy firewall cũng có thể thực hiện kiểm tra gói tin ở tầng sâu hơn, kiểm tra nội dung thực tế của gói thông tin để xác minh rằng nó không chứa phần mềm độc hại.
## Next-Generation Firewall
- Nhiều loại firewall được tạo ra gần đây nhất đang được gọi là kiến trúc “Next-Generation”.
- Một số tính năng phổ biến của loại firewall này bao gồm kiểm tra nội dung thực của gói dữ liệu, kiểm tra TCP handshake và kiểm tra gói ở mức ngoài. Loại firewall này cũng có thể bao gồm các công nghệ khác, chẳng hạn như hệ thống ngăn chặn xâm nhập (IPS) hoạt động để tự động ngăn chặn các cuộc tấn công vào mạng của bạn.
## Software Firewall
- Software firewall bao gồm bất kỳ loại firewall nào được cài đặt trên thiết bị cục bộ chứ không phải là một phần cứng riêng biệt (hoặc cloud server). Lợi ích lớn của Software firewall là nó rất hữu ích trong việc tạo khả năng phòng thủ theo chiều sâu bằng cách cô lập các điểm cuối (endpoint) mạng riêng lẻ với nhau.
- Tuy nhiên, việc duy trì software firewall riêng lẻ trên các thiết bị khác nhau có thể khó khăn và tốn thời gian. Hơn nữa, không phải mọi thiết bị mạng đều có thể tương thích với một software firewall duy nhất, điều này có nghĩa là phải sử dụng nhiều software firewall khác nhau để bao phủ mọi nội dung.

## Hardware Firewalls
- Hardware firewall sử dụng một thiết bị vật lý hoạt động theo cách tương tự như router để chặn các gói dữ liệu và yêu cầu lưu lượng trước khi chúng được kết nối với các server của mạng. Firewall dựa trên thiết bị vật lý như thế này vượt trội về bảo mật ngoại vi bằng cách đảm bảo chặn lưu lượng độc hại từ bên ngoài mạng trước khi các điểm cuối mạng của công ty gặp rủi ro.
- Tuy nhiên, điểm yếu chính của hardware firewall là các cuộc tấn công nội gián thường dễ dàng vượt qua chúng. Ngoài ra, các khả năng thực tế của hardware firewall có thể khác nhau tùy thuộc vào nhà sản xuất — một số có thể có khả năng xử lý các kết nối đồng thời hạn chế hơn những kết nối khác.
## Cloud Firewalls
- cloud-firewall
- Bất cứ khi nào giải pháp cloud được sử dụng để cung cấp firewall, nó có thể được gọi cloud firewall hoặc tường lửa dưới dạng dịch vụ (FaaS). Cloud firewall được coi là giống với Proxy firewall, vì cloud server thường được sử dụng trong thiết lập Proxy firewall (mặc dù proxy không nhất thiết phải ở trên cloud, nó thường xuyên như vậy).
- Lợi ích lớn của việc có cloud firewall là chúng rất dễ mở rộng quy mô với tổ chức. Khi nhu cầu của bạn phát triển, bạn có thể thêm dung lượng bổ sung vào cloud server để lọc lưu lượng lớn hơn. Cloud firewall, giống như tường lửa phần cứng, vượt trội về bảo mật ngoại vi.
# 5. Cách thức hoạt động:
- Nhiệm vụ của Firewall là phân tích các traffic đến dựa trên các rule được thiết lập trước và lọc traffic đến từ các nguồn không an toàn hoặc đáng ngờ để ngăn chặn các cuộc tấn công. Firewall bảo vệ traffic tại điểm vào của máy tính, được gọi là cổng (port), nơi thông tin được trao đổi với các thiết bị bên ngoài. Ví dụ: “Địa chỉ nguồn 172.18.1.1 được phép đến đích 172.18.2.1 thông qua cổng 22.”
- Hãy coi địa chỉ IP là nhà và port là phòng trong nhà. Chỉ những người đáng tin cậy (source address) mới được phép vào nhà (destination address). Sau đó nó lọc thêm để những người trong nhà chỉ truy cập vào vài phòng nhất định (destination ports). Tùy thuộc vào việc họ có phải là chủ sở hữu hay không , một đứa trẻ, hoặc một vị khách. Chủ sở hữu được phép vào bất kỳ phòng nào (any port). Trong khi trẻ em và khách được phép vào một nhóm phòng nhất định (specific port).
- Firewall thiết lập biên giới giữa mạng bên ngoài và mạng mà nó bảo vệ. Nó được chèn vào nội tuyến qua kết nối mạng và kiểm tra tất cả các gói tin vào và ra khỏi mạng. Khi kiểm tra, nó sử dụng một tập hợp các quy tắc được cấu hình sẵn để phân biệt giữa các gói tin tốt và độc hại.
- Thuật ngữ “gói tin” đề cập đến các phần dữ liệu được định dạng để truyền qua internet. Các gói tin chứa dữ liệu, chẳng hạn như nó đến từ đâu. Firewall có thể sử dụng thông tin gói này để xác định xem một gói nhất định có tuân theo bộ quy tắc hay không. Nếu không, gói tin sẽ bị cấm xâm nhập vào mạng được bảo vệ.
- Bộ quy tắc có thể dựa trên một số điều được chỉ ra bởi dữ liệu gói, bao gồm:
```
    Nguồn của gói tin
    Điểm đến của gói tin
    Nội dung của gói tin
 ```
- Các đặc điểm này có thể được biểu diễn khác nhau ở các cấp khác nhau của mạng. Khi một gói tin truyền qua mạng, nó được định dạng lại nhiều lần để cho giao thức biết nơi gửi nó. Các loại firewall khác nhau tồn tại để đọc các gói tin ở các cấp mạng khác nhau.






























