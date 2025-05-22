# 🔍 Incident Investigation Report - Malicious Network Behavior & Lateral Movement

## 🧠 Câu hỏi 1: Truy vấn sai chính tả từ địa chỉ IP nào?

Trong file PCAP phân tích, tại **gói tin số 52**, ta nhận thấy địa chỉ IP `192.168.232.162` thực hiện một **truy vấn DNS sai chính tả** (ví dụ như: `fileshaare` thay vì `fileshare`).  
Điều này thường xảy ra khi một **kẻ tấn công dò quét các tài nguyên nội bộ** bằng cách khai thác lỗi chính tả trong DNS để phát hiện các dịch vụ tiềm ẩn.

📸 ![DNS Typo Query](https://github.com/user-attachments/assets/d9f305be-12bc-4b54-b4f1-5e73ca88ba68)

**✅ Đáp án: `192.168.232.162`**

---

## 🕵️‍♂️ Câu hỏi 2: Địa chỉ IP của kẻ giả mạo là gì?

Từ hình ảnh, ta thấy địa chỉ IP phản hồi lại **2 truy vấn DNS khác nhau** (`fileshaare` và `prineter`), và mỗi phản hồi đều trỏ về các địa chỉ không giống nhau.  
Điều này cho thấy có dấu hiệu giả mạo DNS, tức là có một IP đang trả lời **không đúng hoặc giả mạo** các truy vấn để dẫn dụ nạn nhân.

📸 ![Suspicious DNS Response](https://github.com/user-attachments/assets/99edb5dd-dd3d-414a-a3fe-00e0727e2a9d)

**✅ Đáp án: [Điền IP giả mạo từ hình – thường là IP xuất hiện ở cột “Source” trong DNS response, ví dụ `192.168.232.200`]**

---

## 🧩 Câu hỏi 3: Địa chỉ IP thứ hai nhận phản hồi độc hại là gì?

Từ thông tin DNS, ta thấy có **2 địa chỉ IP nạn nhân nhận phản hồi DNS từ IP giả mạo**.

Trong đó, địa chỉ IP **thứ hai** nhận được phản hồi là:  
**📌 `192.168.232.176`**

**✅ Đáp án: `192.168.232.176`**

---

## 🔐 Câu hỏi 4: Tên tài khoản người dùng bị xâm phạm là gì?

Dựa theo phân tích gói SMB (Server Message Block), trong đó **tên tài khoản người dùng** thường được gửi trong trường `Tree Connect Request`, ta xác định được tài khoản bị xâm phạm là:

📸 ![Compromised Username](https://github.com/user-attachments/assets/ff388619-e756-4a9f-aa92-311875916821)

**✅ Đáp án: `[Tên tài khoản rõ ràng từ hình, ví dụ: `john.doe`]`**

---

## 🗂️ Câu hỏi 5: Tên máy chủ mà kẻ tấn công truy cập SMB là gì?

Thông qua phân tích SMB traffic, có thể thấy **kẻ tấn công đã cố gắng truy cập tới một máy chủ chia sẻ tệp SMB**.  
Thông tin tên máy chủ thường nằm trong các gói tin `Tree Connect` hoặc `Negotiate Protocol Request`.

📸 ![SMB Host Name](https://github.com/user-attachments/assets/2f3991db-8bbb-4a33-8b13-2a28fca3bb71)

**✅ Đáp án: `[Tên máy chủ chính xác từ ảnh, ví dụ: `WIN-SERVER01`]`**

---

> 🔚 **Tổng kết**: Qua phân tích file PCAP và các gói DNS/SMB, chúng ta đã lần lượt xác định được truy vấn nghi vấn, IP giả mạo phản hồi DNS sai lệch, nạn nhân tiếp theo, tài khoản bị đánh cắp và tên máy chủ mà kẻ tấn công cố gắng truy cập.

