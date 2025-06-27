## Câu hỏi 1: Mã băm MD5 của tệp EXE có khả năng gây hại mà người dùng đã tải xuống là gì?
* `336A7CF476EBC7548C93507339196ABB`
* ![{3CD5FCFF-34EE-44E9-9BC4-E3C50A5BB991}](https://github.com/user-attachments/assets/d983a0f0-1ed8-4a9b-befc-a9481c5debb0)
## Câu hỏi 2: URL tải tập tin xuống là gì?
* ![{5CB477EE-284F-47E1-9608-A87DF89ECE6B}](https://github.com/user-attachments/assets/1920d344-0023-443c-ad2e-64e018e79d55)
## Câu hỏi 3: Người dùng đã sử dụng ứng dụng nào để tải xuống tệp này?
* ![{27DDBD2D-BB4D-4277-BB4C-7E4F79839862}](https://github.com/user-attachments/assets/2f00649e-d883-4f75-880a-63f9979e2664)
## Câu hỏi 4: Bằng cách kiểm tra các hiện vật của Windows Mail, chúng tôi đã tìm thấy một địa chỉ email đề cập đến ba địa chỉ IP của máy chủ có nguy cơ hoặc bị xâm phạm. Các địa chỉ IP đó là gì?
* `https://boncaldoforensics.wordpress.com/2018/12/09/microsoft-hxstore-hxd-email-research/`
* ![{08C45943-D224-40F5-AD42-24161134DD8E}](https://github.com/user-attachments/assets/1d6f3afe-98d9-400e-bdc0-badf408e3698)
## Câu hỏi 5: Bằng cách kiểm tra tệp thực thi độc hại, chúng tôi phát hiện ra rằng nó sử dụng một tập lệnh PowerShell được che giấu để giải mã các tệp cụ thể. Tập lệnh sử dụng mật khẩu được xác định trước nào để mã hóa?
* Nó dùng tập lệnh powershell để che giấu nên là tôi đã dùng `strings` để đọc file exe đấy.
* ![{F9BA8C70-2DF9-48E7-960C-F6CBF4734093}](https://github.com/user-attachments/assets/c97ceea4-ad92-4def-8fc3-04a6fb95e5ee)
* Đọc code ta thấy nó đã được encode + reverse from base64. Nên tôi đã đưa nó vào cyberchef và được như hình bên dưới.
* ![{B20AB296-ACC3-4D5D-8706-6D1846B898AD}](https://github.com/user-attachments/assets/926781a3-9ce7-4376-b2e8-f18795b5e0d9)
## Câu hỏi 6: Sau khi xác định được cách thức hoạt động của tập lệnh, hãy giải mã các tập tin và gửi chuỗi bí mật.
* ![{5E85FC15-4E39-4D69-ACB6-F04CCB91E75B}](https://github.com/user-attachments/assets/261cd239-5cd8-4eab-8cb1-c27a43d11257)

