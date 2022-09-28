# Các thao tác cơ bản trên mail server Kerio-connect
## 1. Add domain mới
### Bước 1: Vào configuration -> domain -> add -> local domain
![image](https://user-images.githubusercontent.com/110179869/192675695-a7b57ea6-3a2c-4e61-be5b-f6845abbde81.png)

- Domain: Tên domain cần add
- Description: Mô tả thông tin liên quan đến domain
- User count: Giới hạn số user cho domain

![image](https://user-images.githubusercontent.com/110179869/192676616-c16a3300-b736-4022-bcaa-8bcf85a85a98.png)

### Bước 2: Tab Security
- Chọn theo hình dưới. 2 thông số dưới nhằm đảm bảo vấn đề liên quan đến password

![image](https://user-images.githubusercontent.com/110179869/192676033-4c0e3ac1-f430-4951-a935-53ae43a9bc36.png)

### Bước 3: Tab Message
- Giới hạn dung lượng gửi ra 50MB
- Ngoài ra có thể cấu hình thêm phần `Item clean-out` mục đích nhằm tối ưu hóa hệ thống dung lượng của user

![image](https://user-images.githubusercontent.com/110179869/192676226-3a42f98d-1774-41fa-9de5-cee4fd4dd750.png)

### Bước 4: Tab Custom Logo

- Chọn Logo và upload. Kích thước đề nghị 220x50

![image](https://user-images.githubusercontent.com/110179869/192676384-3c3d427b-133b-4aa2-b0fd-19c421993e0b.png)

- Cài đặt thành công cho 1 domain

![image](https://user-images.githubusercontent.com/110179869/192676772-57eef849-408c-4d52-8db3-8cff16449dd2.png)

### Bước 5: Set domain son.com thành domain chính để dễ quản lí

- Chuột phải vào domain son.com chọn Set as Primary

![image](https://user-images.githubusercontent.com/110179869/192676885-4d06e93b-ff5e-482f-b267-f1d19d9af922.png)

## 2. Add user cho domain son.com vừa tạo
### Bước 1: Vào `Account` -> `User` -> chọn `Domain`
![image](https://user-images.githubusercontent.com/110179869/192676999-e65bdd69-eff4-4ffb-88be-81d6c53f994c.png)

### Bước 2: `Add user` vào `domain` trên
- Chọn `add` -> điền thông tin user
### Bước 3: Tab `General`
- Điền thông tin user ( pas S0981241001.)

![image](https://user-images.githubusercontent.com/110179869/192677350-bf878c8a-8cae-404d-8e90-3e41bbfba921.png)

### Bước 4: Tab Contact
- Ở phần này có thể điền thông tin tùy ý hoặc bỏ qua
- 
![image](https://user-images.githubusercontent.com/110179869/192677959-23105a2d-1cd0-44b0-b561-48d95a9a63b1.png)

### Bước 5: Tab Groups

- Nếu có group riêng thì ta nên vào phần group để cấu hình. Ví dụ: Group Nhân sự, group IT, group Kế toán...
### Bước 6: Tab Quota

- Giới hạn dung lượng và cho mỗi user thì ta nên vào đây để cấu hình
- Ví dụ: Giới hạn user 500MB

![image](https://user-images.githubusercontent.com/110179869/192678045-518e1d22-64ac-49c5-9f8d-f0f250778bb4.png)

### Bước 7: Kiểm tra lại user vừa tạo có hoạt động hay không


























