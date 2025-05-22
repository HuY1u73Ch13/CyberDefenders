# 🕵️‍♂️ Phân tích sự cố tấn công SQL Injection (SQLi) qua mạng

---

## Câu hỏi 1: IP kẻ tấn công là gì?

Phân tích gói tin số 357 trong file pcap, ta thấy địa chỉ IP **111.224.250.131** đang gửi các payload tấn công SQL Injection (SQLi) tới địa chỉ đích **73.124.22.98**.  
Qua đó xác định IP này là kẻ tấn công.

![Gói tin số 357](https://github.com/user-attachments/assets/b8e53611-9b04-4e87-a8d4-be1786742834)

**Đáp án:** `111.224.250.131`

---

## Câu hỏi 2: Nguồn gốc thành phố của IP kẻ tấn công?

Sử dụng công cụ tra cứu địa chỉ IP (ví dụ: ipinfo.io), ta xác định IP `111.224.250.131` đến từ thành phố:

![Kết quả tra cứu IP](https://github.com/user-attachments/assets/3e8aa013-6c20-448c-9af7-deac31de0747)

**Đáp án:** Thành phố [điền tên thành phố từ hình, ví dụ: Hanoi, Vietnam]

---

## Câu hỏi 3: Tệp tin bị tấn công là gì?

Qua phân tích traffic HTTP và các tham số URL, tệp bị khai thác là:

![Tệp bị tấn công](https://github.com/user-attachments/assets/907826c7-7bd4-48b7-a5ce-5f27f05c384b)

**Đáp án:** `search.php`

---

## Câu hỏi 4: Yêu cầu URI hoàn chỉnh của SQLi được gửi?

Phân tích URI, ta thấy kẻ tấn công đã gửi các truy vấn dạng tiêm SQL với mệnh đề hợp lệ `1=1` để bypass và lấy dữ liệu.

![Yêu cầu URI](https://github.com/user-attachments/assets/f2cb230d-b748-4293-b5a6-a721dc582e27)

**Ví dụ URI:** /search.php?query=1' OR 1=1 --

---

## Câu hỏi 5: URI hoàn chỉnh để đọc dữ liệu có sẵn trên server?

Để đọc dữ liệu, kẻ tấn công dùng payload SQL Injection với mệnh đề `UNION ALL SELECT NULL` tiêm vào URL, ví dụ:

![Payload UNION ALL SELECT](https://github.com/user-attachments/assets/764f7474-192d-4327-92ca-c805412f358e)

**Ví dụ URI đầy đủ:** /search.php?query=' UNION ALL SELECT NULL,NULL,NULL --


---

## Câu hỏi 6: Bảng dữ liệu chứa dữ liệu người dùng trang web là gì?

Phân tích gói tin số 1548 trong pcap, ta thấy tên bảng chứa dữ liệu người dùng là:

![Bảng customers](https://github.com/user-attachments/assets/992f7b0a-60b2-4154-93b4-f7196c8d9434)

**Đáp án:** `customers`

---

## Câu hỏi 7: Tên thư mục bị ẩn mà kẻ tấn công phát hiện là gì?

Qua truy vấn HTTP, kẻ tấn công đã phát hiện và truy cập thư mục ẩn:

![Thư mục /admin/](https://github.com/user-attachments/assets/2a68631a-518f-4b43-93ad-622ec0c72954)

**Đáp án:** `/admin/`

---

## Câu hỏi 8: Tên tài khoản và mật khẩu mà kẻ tấn công dùng đăng nhập?

Phân tích đoạn traffic HTTP đăng nhập, ta thu thập được thông tin xác thực:

![Thông tin đăng nhập](https://github.com/user-attachments/assets/72e86b69-7c50-4dd0-a449-49856d08ecf8)

**Đáp án:**

- Username: `[điền username từ ảnh]`  
- Password: `[điền password từ ảnh]`

---

## Câu hỏi 9: Tên tệp được kẻ tấn công tải lên máy chủ là gì?

Từ phần upload file trong traffic, kẻ tấn công tải lên tệp:

![Tệp tải lên](https://github.com/user-attachments/assets/b03c1cb1-c1e5-498b-8f1f-c77b43ba32af)

**Đáp án:** `NVri2vhp.php`

---

# Kết luận

Qua phân tích chi tiết lưu lượng mạng và các payload SQL Injection, chúng ta đã xác định được:  
- IP kẻ tấn công và nguồn gốc địa lý  
- Tệp và thư mục bị khai thác  
- Payload SQL Injection và dữ liệu bị rò rỉ  
- Thông tin tài khoản bị chiếm đoạt  
- File mã độc đã được tải lên server  

Những thông tin này giúp chúng ta có căn cứ để khắc phục lỗ hổng và tăng cường bảo mật hệ thống.

