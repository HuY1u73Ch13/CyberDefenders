### ✅ Câu 1: Địa chỉ IP nào của máy mà kẻ tấn công ban đầu truy cập được?

![Câu 1](https://github.com/user-attachments/assets/84f1efe3-206d-44ee-bce5-a4355c65aa1a)

- Quan sát từ gói tin cho thấy IP `10.0.0.130` đã gửi **38,206 packet** đến `10.0.0.133`.
- ➤ **Kết luận**: `10.0.0.130` là IP của máy tấn công.

---

### ✅ Câu 2: Tên máy chủ mà kẻ tấn công đầu tiên sử dụng là gì?

![Câu 2](https://github.com/user-attachments/assets/20d2c3b8-f66a-4c00-b2dd-fb7cb4582cb6)

- Trong gói SMB2 số 132, thấy user `\ssales` đăng nhập từ một máy có hostname:
  - `S.A.L.E.S.-.P.C`
- ➤ **Kết luận**: Máy ban đầu được sử dụng là **`Sales-PC`**

---

### ✅ Câu 3: Tên người dùng mà kẻ tấn công sử dụng để xác thực là gì?

![Câu 3](https://github.com/user-attachments/assets/b89a6847-3d93-46ad-bf4a-5f2ee0c6f0a2)

- IP `10.0.0.130` đang cố gắng đăng nhập vào `10.0.0.133` thông qua **SMB2**.
- Gói tin chứa thông tin đăng nhập người dùng.
- ➤ **Kết luận**: User **`ssales`** là tài khoản được sử dụng để xác thực.

---

### ✅ Câu 4: Dịch vụ thực thi nào được kẻ tấn công cài trên máy mục tiêu?

![Câu 4](https://github.com/user-attachments/assets/45751aca-e1f4-4423-aad9-e27a738e86d7)

- IP `10.0.0.130` gửi file **`PSEXESVC.exe`** đến IP `10.0.0.133`.
- Đây là dịch vụ thực thi từ công cụ **PsExec** của Sysinternals.
- ➤ **Kết luận**: Dịch vụ được cài là **`PSEXESVC.exe`**

---

### ✅ Câu 5: PsExec đã sử dụng chia sẻ mạng nào để cài đặt dịch vụ?

![Câu 5](https://github.com/user-attachments/assets/8f21b7b3-2e5e-4bab-953c-d4f80acee837)

- Trình tự kết nối:
  1. Kiểm tra xác thực SMB qua `IPC$`
  2. Sau khi xác thực thành công → kết nối đến `ADMIN$`
  3. Upload file `PSEXESVC.exe` lên hệ thống đích.
- ➤ **Kết luận**:
  - Mạng chia sẻ dùng để xác thực: **`IPC$`**
  - Mạng chia sẻ để upload file: **`ADMIN$`**

---

### ✅ Câu 6: PsExec đã sử dụng mạng chia sẻ nào để giao tiếp?

- Dựa trên hình ảnh từ câu 5, ta thấy giao tiếp xảy ra qua hai mạng chia sẻ:
  - `IPC$` (Inter-Process Communication)
  - `ADMIN$` (Windows Administrative Share)
- ➤ **Kết luận**: PsExec dùng **`IPC$` và `ADMIN$`** để giao tiếp và điều khiển máy đích.

---

### ✅ Câu 7: Tên máy chủ thứ hai mà kẻ tấn công nhắm mục tiêu là gì?

![Câu 7a](https://github.com/user-attachments/assets/9258c83f-1279-4076-9157-c67aa3cd2142)  
![Câu 7b](https://github.com/user-attachments/assets/1c80259f-4a60-4097-9167-9abdd5531915)

- Từ IP `10.0.0.130`, tiếp tục truy cập đến IP `10.0.0.131` qua cổng **SMB2**.
- Hostname trong gói SMB cho thấy là: `Marketing-PC`
- ➤ **Kết luận**: Máy thứ hai bị nhắm mục tiêu là **`Marketing-PC`**

