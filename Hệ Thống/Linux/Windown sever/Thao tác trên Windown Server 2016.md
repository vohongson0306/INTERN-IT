# 1.Đặt địa chỉ tĩnh:
## Địa chỉ IP được DHCP gán theo mặc định, vì vậy ta cần đặt địa chỉ IP tĩnh cho việc sử dụng Server 
### Cách 1: Chạy PowerShell với quyền admin và cấu hình như sau:

![image](https://user-images.githubusercontent.com/110179869/190082728-bf44dda9-3ef8-4dcb-aa43-3966b414a54c.png)

![image](https://user-images.githubusercontent.com/110179869/190082929-5cb4b3eb-5a9d-4fe7-be52-71af5dd0af1c.png)

`Get-NetIPInterface -AddressFamily IPv4 `

![image](https://user-images.githubusercontent.com/110179869/190083111-03fb3c64-33fd-4028-891b-b8c2b22ece47.png)

`Set-NetIPInterface -InterfaceIndex 6 -Dhcp Disabled`

![image](https://user-images.githubusercontent.com/110179869/190086363-90bb04d3-d719-43e3-8982-daf648175452.png)

`New-NetIPAddress -InterfaceIndex 6 -AddressFamily IPv4 -IPAddress "172.16.10.100" -PrefixLength 24 -DefaultGateway "172.16.10.1"`

![image](https://user-images.githubusercontent.com/110179869/190087217-e2175e84-b391-4859-aa62-81f30819964f.png)

`Set-DnsClientServerAddress -InterfaceIndex 6 -ServerAddresses "8.8.8.8" -PassThru`

![image](https://user-images.githubusercontent.com/110179869/190087260-136aa6e7-adc5-4848-a434-1e6788e23b66.png)

`ipconfig /all`

![image](https://user-images.githubusercontent.com/110179869/190087495-6f9cdec7-0c5e-4a7f-9d31-876f8c715f8d.png)


### Cách 2: Chạy Server Manager và chọn Local Server trên bảng điều khiển bên trái, rồi nhấp vào phần Ethernet trên bảng điều khiển bên phải

![image](https://user-images.githubusercontent.com/110179869/190084075-1fdf587e-41e5-4945-9370-aa6618280039.png)

- Nhấp chuột phải vào biểu tượng `Ethernet` và mở `Properties`

![image](https://user-images.githubusercontent.com/110179869/190084192-30292e86-ceae-4a0b-9f7f-f7ca10f1cde1.png)

![image](https://user-images.githubusercontent.com/110179869/190084402-b305ea80-ada0-49fe-a7f6-f4eaf1593b74.png)

- Đặt địa chỉ IP tĩnh, gateway và các địa chỉ khác cho mạng cục bộ

![image](https://user-images.githubusercontent.com/110179869/190084887-57c33eb5-540e-44c9-bc2f-4868165d6456.png)

- Sau khi đặt địa chỉ IP tĩnh, các thay đổi sẽ được kích hoạt trên Server Manager

![image](https://user-images.githubusercontent.com/110179869/190085153-5bcecda7-64f2-4754-b14d-366e0232cef8.png)

# 2.Thay đổi tên máy tính
- Tên máy tính được gán tự động theo mặc định, ta cần thay đổi nó

  - Chạy `Server Manager` và chọn `Local Server` ở bên trái, rồi kích vào phần `Computer Name` ở bên phải

  - Tại tab `Computer Name` click vào nút `Change` và nhập tên mà ta muốn thay đổi vào trường `Computer Name`.

![image](https://user-images.githubusercontent.com/110179869/190085655-0c6f882b-960a-4dd5-9c7a-082a73bdaf01.png)

![image](https://user-images.githubusercontent.com/110179869/190085747-618dee53-b28d-4d3d-9550-4b167ec0a14b.png)

![image](https://user-images.githubusercontent.com/110179869/190086104-1317ae89-6b13-4317-969c-4a09b0869927.png)
