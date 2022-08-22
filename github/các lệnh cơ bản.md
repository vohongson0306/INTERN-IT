# Các thuật ngữ Git quan trọng
  # 1. Branch
Các **Branch** (nhánh) đại diện cho các phiên bản cụ thể của một kho lưu trữ tách ra từ project chính của bạn.

Branch cho phép bạn theo dõi các thay đổi thử nghiệm bạn thực hiện đối với kho lưu trữ và có thể hoàn nguyên về các phiên bản cũ hơn.

  # 2. Commit
Một commit đại diện cho một thời điểm cụ thể trong lịch sử dự án của bạn. Sử dụng lệnh commit kết hợp với lệnh git add để cho git biết những thay đổi bạn muốn lưu vào local repository.

  # 3. Checkout
Sử dụng lệnh `git checkout` để chuyển giữa các branch. Chỉ cần nhập git checkout theo sau là tên của branch bạn muốn chuyển đến hoặc nhập git checkout master để trở về branch chính (master branch).

  # 4. Fetch
Lệnh `git fetch` tìm nạp các bản sao và tải xuống tất cả các tệp branch vào máy tính của bạn. Sử dụng nó để lưu các thay đổi mới nhất vào kho lưu trữ của bạn. Nó có thể tìm nạp nhiều branch cùng một lúc.

  # 5. Fork
Một fork là một bản sao của một kho lưu trữ (repository). Các lập trình viên thường tận dụng lợi ích của fork để thử nghiệm các thay đổi mà không ảnh hưởng đến dự án chính.

  # 6. Head
Các commit ở đầu của một branch được gọi là head. Nó đại diện cho commit mới nhất của repository mà bạn hiện đang làm việc.

  # 7. Index
Bất cứ khi nào bạn thêm, xóa hoặc thay đổi một file, nó vẫn nằm trong chỉ mục cho đến khi bạn sẵn sàng commit các thay đổi. Nó như là khu vực tổ chức (stagging area) cho Git. Sử dụng lệnh `git status` để xem nội dung của index của bạn.

Những thay đổi được tô sáng bằng màu xanh lá cây đã sẵn sàng để được commit trong khi những thay đổi màu đỏ thì chưa.

  # 8. Master
Master là nhánh chính của tất cả các repository của bạn. Nó nên bao gồm những thay đổi và commit gần đây nhất.
  # 9. Merge
Lệnh `git merge` kết hợp với các yêu cầu kéo (pull requests) để thêm các thay đổi từ nhánh này sang nhánh khác.

  # 10. Origin
Origin là phiên bản mặc định của repository. Origin cũng đóng vai trò là bí danh hệ thống để liên lạc với nhánh chính.

Lệnh `git push origin master` để đẩy các thay đổi cục bộ đến nhánh chính.

  # 11. Pull
Pull requests thể hiện các đề xuất thay đổi cho nhánh chính. Nếu bạn làm việc với một nhóm, bạn có thể tạo các pull request để yêu cầu người bảo trì kho lưu trữ xem xét các thay đổi và hợp nhất chúng.

Lệnh `git pull` được sử dụng để thêm các thay đổi vào nhánh chính.

  # 12. Push
Lệnh `git push` được sử dụng để cập nhật các nhánh từ xa với những thay đổi mới nhất mà bạn đã `commit`.

  # 13. Rebase
Lệnh `git rebase` cho phép bạn phân tách, di chuyển hoặc thoát khỏi các commit. Nó cũng có thể được sử dụng để kết hợp hai nhánh khác nhau.

  # 14. Remote
Một Remote (kho lưu trữ từ xa) là một bản sao của một chi nhánh. Remote giao tiếp ngược dòng với nhánh gốc (origin branch) của chúng và các Remote khác trong kho lưu trữ.

  # 15. Repository
Kho lưu trữ Git chứa tất cả các tệp dự án của bạn bao gồm các branch, tags và commit.

  # 16. Stash
Lệnh git stash sẽ loại bỏ các thay đổi khỏi chỉ mục của bạn và xóa stashes chúng đi sau.

Nó có ích nếu bạn muốn tạm dừng những gì bạn đang làm và làm việc khác trong một khoảng thời gian. Bạn không thể đặt stash nhiều hơn một bộ thay đổi ở cùng một thời điểm.

  # 17. Tags
Tags cung cấp cho bạn một cách để theo dõi các commit quan trọng. Các tags nhẹ chỉ đơn giản đóng vai trò là con trỏ trong khi các tags chú thích được lưu trữ dưới dạng các đối tượng đầy đủ.

  # 18. Upstream
Trong ngữ cảnh của Git, upstream đề cập đến nơi bạn push các thay đổi của mình, thường là nhánh chính (master branch).

Xem Git docs reference để biết thêm chi tiết về thuật ngữ liên quan đến Git.
# Các lệnh git cơ bản
  # 1) git config
Tác dụng : Để set user name và email của bạn trong main configuration file.
Cách xài : Để kiểm tra tên và kiểu email trong cấu hình dùng ` git config -- global user.name ` và `git config -- global user.email.` Để set email hoặc tên mới `git config  global user.name = “Hồng Sơn”` và `git config -- global user.email = “hongson@gmail.com”` 

  # 2) git init
Tác dụng : Khởi tạo 1 git repository 1 project mới hoặc đã có.

Cách xài: `git init` trong thư mục gốc của dự án.

  # 3) git clone
Tác dụng: Copy 1 git repository từ remote source.

Cách xài: `git clone <:clone git url:>`

  # 4) git status
Tác dụng: Để check trạng thái của những file bạn đã thay đổi trong thư mục làm việc. VD: Tất cả các thay đổi cuối cùng từ lần commit cuối cùng.

Cách xài: `git status` trong thư mục làm việc.

  # 5) git add
Tác dụng: Thêm thay đổi đến stage/index trong thư mục làm việc.

Cách xài: `git add`

  # 6) git commit
Tác dụng: commit nghĩa là một action để Git lưu lại một snapshot của các sự thay đổi trong thư mục làm việc. Và các tập tin, thư mục được thay đổi đã phải nằm trong Staging Area. Mỗi lần commit nó sẽ được lưu lại lịch sử chỉnh sửa của code kèm theo tên và địa chỉ email của người commit. Ngoài ra trong Git bạn cũng có thể khôi phục lại tập tin trong lịch sử commit của nó để chia cho một branch khác, vì vậy bạn sẽ dễ dàng khôi phục lại các thay đổi trước đó.

Cách dùng: `git commit -m ”Đây là message, bạn dùng để note những thay đổi để sau này dễ dò lại”`
  # 7) git push/git pull
Tác dụng: Push hoặc Pull các thay đổi đến remote. Nếu bạn đã added và committed các thay đổi và bạn muốn đẩy nó lên hoặc remote của bạn đã update và bạn apply tất cả thay đổi đó trên code của mình.

Cách dùng: `git pull <:remote:> <:branch:>` and `git push <:remote:> <:branch:>`

  # 8) git branch
Tác dụng: liệt kê tất cả các branch (nhánh).

Cách dùng: `git branch` hoặc `git branch -a`

  # 9) git checkout
Tác dụng: Chuyển sang branch khác

Cách dùng: `git checkout <: branch:>` hoặc `** _ git checkout -b <: branch:>` nếu bạn muốn tạo và chuyển sang một chi nhánh mới.

  # 10) git stash
Tác dụng: Lưu thay đổi mà bạn không muốn commit ngay lập tức.

Cách dùng: `git stash+` trong thư mục làm việc của bạn.

  # 11) git merge
Tác dụng: Merge 2 branch lại với nahu.

Cách dùng: Chuyển tới branch bạn muốn merge rồi  dùng `git merge <:branch_ban_muon_merge:>`

  #12) git reset
Tác dụng: Bạn đã đưa một tập tin nào đó vào Staging Area nhưng bây giờ bạn muốn loại bỏ nó ra khỏi đây để không phải bị commit theo.

Cách dùng: `git reset HEAD tên_file`

  # 13) git remote
Tác dụng: Để check remote/source bạn có hoặc add thêm remote

Cách dùng: `git remote` để kiểm tra và liệt kê. Và `git remote add <: remote_url:>` để thêm.

  # 14) git add
Tác dụng: Để đưa một tập tin vào Staging Area

Cách dùng: `git add tên_file` hoặc muốn thêm hết file của thư mục thì `git add all`
