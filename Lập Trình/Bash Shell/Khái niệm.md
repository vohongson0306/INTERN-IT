# Tìm hiểu về Bash Shell

## 1. Shell script
<img src="https://bigvn.net/wp-content/uploads/2017/01/linux-620x420.png">

- Shell là chương trình giao tiếp với người dùng , chấp nhận các lệnh nhập từ keyboard và thực thi nó .
- Nếu muốn sử dụng nhiều lệnh chỉ bằng 1 lệnh , có thể lưu chuỗi lệnh vào file text và bảo shell thực thi chuỗi lệnh thay vì tự nhập vào các lệnh .
- Shell-script là 1 chuỗi các lệnh được viết trong plain-text file ( giống batch trong MS-DOS nhưng mạnh mẽ hơn ) .
- **Ưu điểm** :
    - Shell-script có thể nhận input từ user , file hoặc output từ màn hình .
    - Tiện lợi để tạo nhóm lệnh riêng
    - Tiết kiệm thời gian
    - Tự động làm các công việc đã được lên lịch


## 2. Cách tạo và thực thi shell-script
**Bước 1:** Tạo file shell. File shell có đuôi là `.sh`
- Sử dụng `vi`, `vim`, ... để tạo file
- Dòng đầu tiên luôn là `#!/bin/bash` -> Bắt buộc
- Sau dấu `#` được coi là comment, chú thích của đoạn shell và không có giá trị trong việc thực thi

Ví dụ: file `helloWord.sh`

![image](https://user-images.githubusercontent.com/110179869/189562487-d0dd69a5-b81d-46a7-90a4-de9636894893.png)

```bash
#!/bin/bash
echo "Hello World!"
```
![image](https://user-images.githubusercontent.com/110179869/189562407-7333c4c6-ae15-4628-a945-2dd0201f4cd8.png)

**Bước 2:** Cấp quyền thực thi cho file 
```
chmod 755 helloWord.sh
```
![image](https://user-images.githubusercontent.com/110179869/189562582-7622240a-c00c-4783-a3fb-cd9c3e48be81.png)

**Bước 3:** Thực thi file shell
Có một vài cách để thực thi file shell
- *Cách 1*: 
    ```
    ./<tên_file_sh>
    ```
![image](https://user-images.githubusercontent.com/110179869/189562599-27d8abe1-b553-41ab-94c3-cedc968ee5d2.png)

- *Cách 2*: 
    ```
    bash <tên_file_sh>
    ```
![image](https://user-images.githubusercontent.com/110179869/189562623-be5b0c11-ad54-4030-92a6-02327e936883.png)

- *Cách 3*:
    ```
    sh <tên_file_sh>
    ```
![image](https://user-images.githubusercontent.com/110179869/189562660-361ad650-b81c-41b0-9deb-573046881ec4.png)

