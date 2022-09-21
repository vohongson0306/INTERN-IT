# I. Các bước tải, cài đặt SQL Server 2019 :
## Bước 1: Truy cập trang chủ để tải SQL Server 2019
https://www.microsoft.com/en-us/sql-server/sql-server-downloads

Sau đó ấn nút download ở phần developer để tải phần mềm về

![image](https://user-images.githubusercontent.com/110179869/191442245-55c906c4-b0f7-43f7-b96d-5d38417ef8fe.png)

![image](https://user-images.githubusercontent.com/110179869/191442462-6f3a1cdb-4c3f-4e52-a12b-12a4bee8cbc9.png)

## Bước 2: Mở ứng dụng đã tải xong ra
![image](https://user-images.githubusercontent.com/110179869/191442671-c5830c68-1fab-4895-bb47-dde52751067a.png)

## Bước 3: Sau khi mở ứng dụng ta có 3 lựa chọn tùy mục đích khác nhau cho người dùng:
![image](https://user-images.githubusercontent.com/110179869/191442988-ab05930f-db4d-460b-aae4-270d223d3547.png)

- Basic: đây là tùy chọn đơn giản nhất cho người dùng, tại đây ứng dụng sẽ tự động cài đặt các chức năng cơ bản cho bạn.
- Custom: đây là phần cài đặt cho các bạn muốn sử dụng chuyên sâu hơn, khi chọn bạn sẽ được tự cài đặt các cấu hình của phần mềm.
- Download Media: khi chọn vào mục này, hệ thống sẽ tải về cho bạn một file cài đặt offline nhằm mục đích cài được trên nhiều thiết bị khác nhau mà không cần load lại từ đầu.

![image](https://user-images.githubusercontent.com/110179869/191443388-976edd5a-d1e6-4334-b9f4-7958e6769e32.png)

- Mình sẽ chọn chế độ Basic, các bạn hãy chọn basic và ấn Accept sau đó ấn nút Install để tiến hành cài đặt.

![image](https://user-images.githubusercontent.com/110179869/191443737-53ea65e4-6595-4484-91c0-f6166227d834.png)

## Bước 4: Tại đây ta ấn nút Customize để bắt đầu setting cấu hình để sử dụng.

![image](https://user-images.githubusercontent.com/110179869/191445541-b73a3291-90a0-48c2-b412-822856c185df.png)

## Bước 5: Cửa sổ đầu tiên ta ấn next.

![image](https://user-images.githubusercontent.com/110179869/191445935-3c6228f6-0505-409e-aea2-0d65451229d7.png)

## Bước 6: Hệ thống sẽ kiểm tra xem các mục đã đạt yêu cầu chưa, dấu tích xanh là đã ổn và thường thì mục Firewall sẽ màu vàng cảnh báo là nó có thể ảnh hưởng đến quá trình cài đặt, riêng mục này các bạn có thể bỏ qua và tiếp tục bấm next.

![image](https://user-images.githubusercontent.com/110179869/191446214-9d117dea-64eb-467e-a0c5-700f8c126036.png)

Tiếp theo, ở mục Product key bạn phải chọn mục developer để có thể sử dụng miễn phí phần mềm này và ấn next để tiếp tục.

![image](https://user-images.githubusercontent.com/110179869/191446735-f93c54d1-d44b-443b-bb87-132e9329d5ef.png)

Ở mục License Terms ta chọn I accept the license terms and Privacy Statement và nhấn next

![image](https://user-images.githubusercontent.com/110179869/191447474-8321582b-de8e-4410-b007-39ac355554da.png)

Ở mục Features Selection ta nên chọn Database Engine Services, Data Quality Client và Client Tools Connectivity để ứng dụng cung cấp đủ packages và chức năng cho bạn học đầy đủ về môn cơ sở dữ liệu và bấm next.

![image](https://user-images.githubusercontent.com/110179869/191447863-666542be-dc9b-4d5d-ad97-e415e082dcad.png)

![image](https://user-images.githubusercontent.com/110179869/191448277-18598f06-dbc4-47a6-a73d-d6531ba5d222.png)

## Bước 7: Đến với mục Feature Configuration Rules, tới đây bạn có thể đặt tên cho Instance (tên các bạn có thể đặt tùy ý, không dấu, không khoản trắng) sau đó nhấn next cho đến phần Database Engine Configuration.

![image](https://user-images.githubusercontent.com/110179869/191448514-975b8b82-78f3-408c-a409-74e4278d0a99.png)

## Bước 8: Ở mục này, ta bấm chọn chức năng Mix Mode. Đây là chức năng bảo mật cho cơ sở dữ liệu của bạn.
Tiếp theo các bạn nhập mật khẩu cho tài khoản supper admin(sa) của bạn. Và cuối cùng nhấn nút Add current User để thêm tài khoản.

Cuối cùng bạn nhấn next cho đến mục Ready to Install.

![image](https://user-images.githubusercontent.com/110179869/191448977-4f3e8486-6bc0-477c-a57e-79e0f23750fa.png)

## Bước 9: Đây là phần cuối cùng. Bạn chỉ cần nhấn Install và đợi đến khi file cài đặt xong và bấm close để hoàn tất.

![image](https://user-images.githubusercontent.com/110179869/191449111-4822ee5c-05a6-4201-8a2a-c94995d72880.png)

![image](https://user-images.githubusercontent.com/110179869/191449614-2abb8e88-257a-45e3-93b9-57a57eba3adc.png)

# II. Cài đặt SQL Server Management Studio (SSMS)
## Bước 1: Bạn chọn nút Install SSMS. Hệ thống sẽ tự động đưa bạn đến link tải.

![image](https://user-images.githubusercontent.com/110179869/191449664-3f737a74-c9cf-4864-9990-8699355f0609.png)

## Bước 2: Ấn vào “Download SQL Server Management Studio (SSMS)” để tải file SSMS về

![image](https://user-images.githubusercontent.com/110179869/191449903-9065c22f-bf63-4ac6-a41b-b2da259c9bf9.png)

## Bước 3: Mở file vừa tải về, bấm Install để cài giao diện cho phần mềm

![image](https://user-images.githubusercontent.com/110179869/191450377-6d0f3dcb-0c79-44b5-8095-e00ca70e6fd7.png)

Cuối cùng, sau khi cài xong ta chọn Close để hoàn tất.

![image](https://user-images.githubusercontent.com/110179869/191451613-38a012df-b5de-4a67-9d9c-4129da71ef24.png)

vào ssms để login in vào

![image](https://user-images.githubusercontent.com/110179869/191452559-af0f549d-cd67-4847-bcf6-b69823e69911.png)



