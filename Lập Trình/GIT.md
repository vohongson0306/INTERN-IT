<img src="https://blog.haposoft.com/content/images/2017/10/AAEAAQAAAAAAAAdxAAAAJDdlNTkxZDk0LTJlNmItNDc1NS1hODdiLTQwZTZiZDdmN2Y0Ng.png"> 

# 1.Khái niệm
GIT là hệ thống quản lý các phiên bản dưới dạng phân tán. Đây là hệ thống quản lý phổ biến nhất hiện nay. GIT là một phiên bản của Distributed Version Control System–DVCS hay còn gọi là VCS. Sử dụng GIT sẽ đem tới cho các lập trình viên một kho lưu trữ, trong đó chứa đầy đủ các lịch sử thay đổi của hệ thống. 

# 2.Lợi ích sử dụng phần mềm Git
- Thao tác thực hiện nhanh, gọn, lẹ hơn, việc sử dụng an toàn hơn.
- Người dùng có thể dễ dàng kết hợp các nhánh với nhau. Qua đó giúp đơn giản hóa quy trình code theo nhóm. 
- Khi sử dụng GIT, người dùng chỉ cần sử dụng clone mã nguồn từ khoa chứa/phiên bản nào đó có sẵn trong kho lưu trữ/ một nhánh trong kho lưu trữ. Hệ thống lưu trữ chính xác sẽ cho phép bạn có thể làm việc bất cứ lúc nào, ở bất cứ đâu. 
- Giờ đây, việc lập trình các dự án song song sẽ cực kỳ dễ dàng, hiệu quả và chính xác. 

# 3.Một số các thuật ngữ quan trọng liên quan đến Git
## Branch
Trong GIT, Branch được hiểu là các nhánh. Các Branch sẽ tương ứng với các phiên bản cụ thể trong kho lưu trữ. Branch cho phép người dùng có thể dễ dàng truy cập, theo dõi các thay đổi của các phiên bản, từ đó thử nghiệm hoặc lựa chọn sử dụng phiên bản cũ hơn. 
## Commit
Commit là một thuật ngữ cực kỳ quen thuộc trong Git. Vậy commit trong git là gì? Hiểu một cách đơn giản, commit là thuật ngữ thể hiện một thời điểm cụ thể trong lịch sử thực hiện code của bạn. Các dự án sẽ có nhiều thời điểm cụ thể trong lịch sử nên sẽ có nhiều code. Khi sử dụng git, bạn có thể dùng lệnh commit kết hợp với lệnh git add để kiểm tra các thay đổi và lưu trữ trong local repository. 
<img src="https://fptcloud.com/wp-content/uploads/2022/01/Commit-la-mot-thuat-ngu-cuc-ky-quen-thuoc-trong-Git-768x431.jpg">

## Check out
Khi sử dụng git, các lập trình viên sẽ dùng lệnh checkout để chuyển giữa các nhánh hay còn gọi là các branch. Chỉ cần nhập lệnh git checkout + tên Branch, bạn đã có thể chuyển đến nhánh mong muốn. Đồng thời, lệnh check out cũng cho phép người dùng chuyển về branch (master Branch). 
## Fetch
Sử dụng lệnh Fetch sẽ cho phép bạn nạp và tải các bản sao trên hệ thống lưu trữ và tải các tệp nhánh về máy tính cá nhân. Bạn có thể sử dụng lệnh Fetch để lưu các thay đổi mới nhất vào kho lưu trữ. Fetch cho phép bạn có thể lưu trữ nhiều nhánh trong cùng một thời điểm. 
## Fork
Fork là thuật ngữ thể hiện các bản sao của một kho lưu trữ. Tiện ích fork cho phép người dùng – các lập trình viên có thể thử nghiệm các thay đổi. Nhờ việc sử dụng trên bản sao nên người dùng có thể thoải mái thay đổi mà không lo ảnh hưởng tới các dự án chính. 
## Head
Các nhánh trong Git sẽ bao gồm các commit. Và các commit ở đầu 1 nhánh sẽ được gọi là Head. Một head sẽ tương ứng với một commit mới nhất trong hệ thống lưu trữ. 
## Index
Index là thuật ngữ được sử dụng khi bạn thêm/xóa/thay đổi một file dữ liệu nào đó. Tuy nhiên, file dữ liệu này vẫn sẽ cần nằm trong thư mục cho đến khi bạn sẵn sàng commit các thay đổi. Bạn có thể phân biệt các thay đổi dựa vào màu sắc của commit. Các thay đổi có màu xanh tức là đã sẵn sàng để được thay đổi, còn màu đỏ là chưa sẵn sàng. 
## Master
Master trong Git là gì? Đây là các nhánh chính trong kho lưu trữ của phần mềm Git mà bạn đang sử dụng. Nhánh master sẽ bao gồm các thay đổi và commit trong thời gian gần đây nhất. 
## Merge
Trong Git, người dùng có thể dùng lệnh Git Merge để bổ sung các thay đổi từ branch này sang branch khác. Người dùng chỉ cần dùng lệnh Merge và pull requests là đã có thể dễ dàng kéo các yêu cầu từ các nhánh khác nhau. 
## Origin
Đây là phiên bản mặc định của hệ thống lưu trữ. Origin sẽ đóng vai trò liên lạc với nhánh chính. Vì thế, người dùng có thể dùng lệnh Git push Origin master để thay đổi tới nhánh chính. Việc thay đổi có thể diễn ra cục bộ.
## Pull
Thuật ngữ Pull trong Git là gì? Hiểu một cách đơn giản, Pull là việc người dùng đề xuất các thay đổi mới cho Master Branch. Đây là tính năng phù hợp với các dự án cần làm việc nhóm. Người thực hiện có thể dùng tính năng Pull Request để yêu cầu người có nhiệm vụ thực hiện bảo trì kho lưu trữ để xem xét các thay đổi của hệ thống. 

Người dùng có thể dùng lệnh Git Pull để thay đổi lịch sử lưu trữ vào các nhánh chính. 

Push
Lệnh Push được sử dụng khi người lập trình cần cập nhật các branch từ xa. Đồng thời, Git Push cũng được dùng cho những thay đổi mới nhất mà người sử dụng đã commit.
## Rebase
Nếu muốn phân tích, di chuyển các commit, rebase sẽ là lệnh phù hợp. Bạn cũng có thể sử dụng lệnh Git rebase để thoát khỏi commit hoặc hợp nhất 2 nhánh khác nhau.
## Remote
Remote cũng là một kho lưu trữ. Tuy nhiên, đây là kho lưu trữ từ xa. Remote là một bản sao của một nhánh, có cấu trúc giao tiếp ngược dòng với nhánh gốc cũng như các nhánh khác có trong kho lưu trữ. 
## Repository
Đây là thuật ngữ thể hiện kho lưu trữ GIT với các tập của dự án. Trong kho lưu trữ Repository có thể chứa các branch, tags và các commit. 
## Stash
Lệnh Stash cho phép người dùng có thể loại bỏ các thay đổi hiện có tại mục đang lựa chọn. Sau đó, bạn có thể xóa các stashes. Trong trường hợp bạn muốn tạm dừng hoạt động của mình trong thời gian ngắn, lệnh Stash sẽ là lựa chọn hữu ích dành cho bạn.  
## Tags
Các tags được sử dụng để theo dõi commit quan trọng trong hệ thống. Người dùng có thể sử dụng các tags để chú thích commit, giúp việc tra cứu đối tượng nhanh chóng và đầy đủ hơn. 
## Upstream
Upstream là thuật ngữ để chơi nơi bạn có thể push các thay đổi trong nhóm chính. 

