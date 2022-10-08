# 1. Cách xem file log
- Để xem file log chúng ta có thể sử dụng một số phương pháp phổ biến sau:
- vi: Chúng ta có thể sử dụng trình soạn thảo vi để kiểm tra file log.
- tail: Nếu chúng ta muốn xem nội dung của file log theo thời gian thực ứng dụng đang ghi vào đó, hãy sử dụng tail -f.
- grep: Nếu chúng ta biết chính xác những gì đang tìm kiếm trong file log hãy sử dụng lệnh grep để grep một mẫu.
- Ngoài ra còn nhiều phương pháp khác để kiểm tra file log.
# 2. grep:
## Tìm một chuỗi trong một file: 
- Đây là cách sử dụng cơ bản và hay gặp nhất, nếu đơn gỉan bạn muốn tìm một chuỗi nào đó trong chỉ một file duy nhất thì có thể dùng theo cú pháp sau :
```
        $ grep "chuoi" ten_file
```
- Kết qủa sẽ hiển thị ngay trên màn hình command line theo dòng nào có chứa chuỗi sẽ hiển thị cả dòng trong file đó ra và chuỗi đó sẽ được highlight.
## Tìm chuỗi trong nhiều file cùng lúc
Để làm được việc này thì bạn cần chỉ định pattern chung của các file muốn thực hiện tìm kiếm :
```
$ grep "chuoi" file_pattern
```
Ví dụ, tôi tìm chuỗi Error trong tất cả các file log mà chúng được ghi theo từng ngày với for mat report_ddmmyyyy.log :
```
$ grep "chuoi" report_*.log
```
Khi này kết qủa tìm kiếm sẽ hiển thị ra thêm cả tên file mà có chứa chuỗi Error dạng :
```
report_01082016.log: <nội dung match ở đây>

report_01082016.log: <nội dung match ở đây>

...
report_28082016.log: <nội dung match ở đây>

report_28082016.log: <nội dung match ở đây>

report_29082016.log: <nội dung match ở đây>
```
##  Tìm kiếm không phân biệt hoa thường

Bình thường nếu bạn đã chắc chắn chuỗi mình định tìm kiếm như nào và chỉ muốn có kết qủa match 100% chuỗi đó thì ko cần sử dụng thêm lựa chọn -i, khi khai báo thêm nó grep sẽ thực hiện tìm kiếm gần đúng theo kiểu không phân biệt ký tự hoa thường :
```
$ grep -i "chuoi" ten_file
```
Như ví dụ trên thì dù là Error, error hay ERROR ... đi chăng nữa thì bạn cũng sẽ nhận được kết qủa.

##  Tìm kiếm theo regular expression

Như bao ngôn ngữ lập trình, việc tìm kiếm theo regular expression luôn được hỗ trợ thì lệnh grep cũng vậy, bạn hoàn toàn có thể chỉ định biểu thức chính quy để tìm kiếm chuỗi match với nó.
```
$ grep "regex_here" ten_file
```
Trong grep thì nó cũng giống các ngôn ngữ khác, ví dụ [A-z] tức là match với chỉ kí tự alpha từ A lớn đến z nhỏ, hay dùng [^text] là ko chứa chuỗi text...

##  Tìm chính xác với grep -w

Nếu bạn tìm kiếm theo những lệnh trên thì kết qủa trả về sẽ chưa hẳn theo đúng mong muốn của bạn. Kết qủa thường sẽ thừa so với yêu cầu bởi vì grep sẽ tìm theo cả chuỗi con, ví dụ tìm no thì not, nothing cũng có chứa chuỗi no nên cũng sẽ trả về kết qủa. Do đó, nếu bạn muốn tìm chính xác từ mong muốn thì có thể dùng lựa chọn -w.
```
$ grep -i "is" demo_file
```
## Hiển thị thêm dòng trước, sau, xung quanh dòng chứa kết qủa

Có những trường hợp bạn phải thao tác với file rất lớn, nên có thể lựa chọn tìm kiếm mà có hiển thị ra các dòng trước, sau hoặc xung quanh dòng kết qủa sẽ có thể hữu ích.
```
$ grep -<A, B hoặc C> <n> "chuoi" demo_file
```
-- A : là after

-- B : là before

-- C : là xung quanh

-- n : là số tự nhiên chỉ định xem hiển thị trước, sau hay xung quang bao nhiêu dòng

Ví dụ
```
$ grep -B 3 -iw "chuoi" demo_file
```
-- Tức là hiển thị trước kết qủa thêm nội dung của 3 dòng nữa. Không phân biệt hoa thường và tìm chính xác

## Tìm tất cả các file ở tất cả các thư mục con

Đôi khi bạn không biết file ở đâu trong thư mục rất nhiều file, không nhớ tên file là gì hoặc đơn gỉan là muốn tìm kiếm với từ khóa xem nó có trong nhưng file nào trong thư mục hiện hành. Lúc đó, lựa chọn -r sẽ hữu ích. Nếu khai báo lựa chọn này thì nó sẽ tìm đến tận cùng các thư mục con, tất cả các file có trog chúng.
```
$ grep -r "chuoi" *
```
Đương nhiên bạn vẫn có thể tìm file pattern
```
$ grep -r "chuoi" file_name_*
```
## Tìm kiếm ngược

Với những lựa chọn trên bạn có thể tìm kiếm từ khóa theo những hoàn cảnh của riêng mình, nhưng nếu bạn muốn ngược lại tức là chỉ tìm những dòng không chứa từ khóa đó thì hãy dùng -v.
```
$ grep -v "chuoi" file_*
```
##  Đếm số kết qủa

grep hoàn toàn có thể hỗ trợ bạn đếm xem trong file chỉ định có bao nhiêu kết qủa trả về bằng cách dùng -c. Ví dụ như đếm xem có bao nhiêu bản ghi được insert trong file log.
```
 grep -c -w "INSERT" log_*
```
## Chỉ hiển thị tên file

Đơn gỉan là vậy, sẽ có case bạn chỉ quan tâm xem từ khóa bạn đang tìm xuất hiện trong những file nào thôi. Lúc đó hãy dùng lựa chọn -l
```
$ grep -l -r -w "Error" *
```
## Hiển thị số thứ tự của dòng kết qủa

Trong một file rất lớn thì nhu cầu biết được xem kết qủa ở dòng nào thì tôi nghĩ luôn là cần thiết. grep hoàn toàn làm được điều này với lựa chọn -n.
```
$ grep -n -w "Error" file_name
```
## Ứng dụng
Trong thực tế tôi hay gặp nhất có lẽ là lệnh kép kiểm tra xem một chương trình nào đó có đang chạy hay không, bằng cách kết hợp ps và grep. Ví dụ, với project Java thì đôi khi service tomcat đôi khi vì lý do nào đó mà nó bị chết nhưng tiến trình thì vẫn còn nên cần vào kill tiến trình đó đi rồi start lại. Tôi hay dùng lệnh sau để biết được id tiến trình của tomcat
# 3. tail
## Để hiển thị 10 dòng cuối của file, bạn nhập vào lệnh sau:
```
tail name_of_file
```
Hoặc là:
```
tail file_path
```
Kết quả sẽ hiển thị 10 dòng cuối

## Tale hiển thị số lượng dòng khi người dùng đặt đối số –n vào trong lệnh.

Lệnh tail giới hạn số dòng được viết như sau:
```
Tail –n* file_path
```
Bạn thay dấu `*` bằng số dòng muốn in.

Ví dụ, nếu bạn muốn hiển thị 2 dòng cuối của file, bạn nhập lệnh sau:
```
tail -n2 devisers.txt
```
`2` là số dòng, còn `devisers.txt` là tên file.

## Để xem những bytes cuối của một files lớn, bạn có thể dùng option -c khi nhập lệnh.
```
tail –c* file_path
```
Dấu `* `là số bytes. Thay nó bằng số bạn muốn xem.

## Để kiểm tra file có thay đổi không, theo thời gian thực bạn dùng thêm option -f. Nó cũng hiển thị 10 dòng cuối, nhưng thay đổi theo thời gian thực nếu file thay đổi. Vì vậy nó hay được dùng để xem file log. Nếu file có tên là devisers.txt thì lệnh nhập như sau:
```
tail -f devisers.txt
```
Phiên bản mới hơn của tail command cũng giúp người dung xem nhiều file hoặc folder cùng lúc. Khi file gốc thay đổi, header sẽ hiển thị dòng mà file thay đổi.

## Tail commands có thể kết hợp với các lệnh Linux command khác. Chúng ta có thể sử dụng nó với:

### Sử dụng Tail Command với `-r (Reverse Order)`

Tại đây, chúng ta sẽ hiển thị kết quả tail command theo thứ tự ngược lại.
```
tail –n* file_name | sort -r
```
Phần đầu của command là lệnh thông thường, sau đó chúng ta tách nó ra bằng dấu | để chỉ dẫn làm theo kiểu sắp xếp – sort -r, – tức là sắp xếp kiểu ngược lại.

### Sử dụng tail command với ls (File hoặc folder cũ nhất)

Theo ví dụ bên dưới chúng ta sẽ thấy 7 files hoặc folder được thay đổi lâu nhất trước đây.

Để xem, output của lệnh ls sẽ đưa vào trong tail command. Cú pháp như sau:
```
ls -l | tail -n8
```
`Tail -n8` là bạn có thể điền số tùy ý bạn muốn vào.



