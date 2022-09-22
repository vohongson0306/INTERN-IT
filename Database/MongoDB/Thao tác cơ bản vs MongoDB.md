# 1.Thao tác với db.
- tạo db

`use DATABASE_NAME`

![image](https://user-images.githubusercontent.com/110179869/191644596-4fc85402-605b-4269-be80-5ae6eaaba494.png)

- xóa db

`db.dropDatabase()`
    
- db đang sử dụng

` db`

![image](https://user-images.githubusercontent.com/110179869/191644670-f7065601-0e29-44c5-a063-f67d663423de.png)

- danh sách db

`show dbs`
    
![image](https://user-images.githubusercontent.com/110179869/191644761-daa83048-7cb5-4c6f-b437-174c7c8df620.png)

# 2.Kiểu dữ liệu:
```
        String: Đây là kiểu dữ liệu được sử dụng phổ biến nhất để lưu giữ dữ liệu. Chuỗi trong MongoDB phải là UTF-8 hợp lệ.

        Integer: Số nguyên có thể là 32 bit hoặc 64 bit tùy thuộc vào máy chủ của bạn.

        Boolean: Kiểu dữ liệu này được sử dụng để lưu giữ một giá trị Boolean (true/false).

        Double: Kiểu dữ liệu này được sử dụng để lưu các giá trị số thực dấu chấm động.

        Min/ Max keys: Loại này được sử dụng để so sánh giá trị đối với các yếu tố thấp nhất và cao nhất BSON.

        Array : Kiểu dữ liệu này được sử dụng để lưu giữ các mảng hoặc danh sách hoặc nhiều giá trị vào trong một key.

        Timestamp : Giúp thuận tiện cho việc ghi chép hoặc đánh dấu thời điểm một Document được sửa đổi hoặc được thêm vào.

        Object :  Kiểu dữ liệu này được sử dụng cho các Document được nhúng vào.

        Null :  Kiểu dữ liệu này được sử dụng để lưu một giá trị Null.

        Symbol :  Kiểu dữ liệu này được sử dụng giống như một chuỗi, tuy nhiên, nói chung nó được dành riêng cho các ngôn ngữ mà sử dụng kiểu symbol cụ thể.

        Date : Kiểu dữ liệu này được sử dụng để lưu giữ date và time hiện tại trong định dạng UNIX time. Bạn có thể xác định date time riêng cho bạn bằng việc tạo đối tượng Date và truyền ngày, tháng, năm vào trong đó.

        Object ID : Kiểu dữ liệu này được sử dụng để lưu giữ ID của Document.

        Binary data : Kiểu dữ liệu này được sử dụng để lưu giữ dữ liệu nhị phân.

        Code : Kiểu dữ liệu này được sử dụng để lưu giữ JavaScrip code vào trong Document.

        Regular expression : Kiểu dữ liệu này được sử dụng để lưu giữ Regular Expresion.
``` 









