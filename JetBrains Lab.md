## Câu hỏi 1: Việc xác định địa chỉ IP của kẻ tấn công giúp truy tìm nguồn gốc và ngăn chặn các cuộc tấn công tiếp theo. Địa chỉ IP của kẻ tấn công là gì?
* `23.158.56.196`
* <img width="1193" height="183" alt="{9387CCC8-4278-446C-9C27-BA4B741992DB}" src="https://github.com/user-attachments/assets/ce5e5586-ebd6-41d7-9b52-d1472cfb3265" />
## Câu hỏi 2: Để xác định lỗ hổng tiềm ẩn, chúng tôi đang chạy phiên bản nào của dịch vụ máy chủ web?
* Tìm theo địa chỉ ip của kẻ tấn công trên và phương thức là http để xem version của nó tôi dùng query như sau.
* `ip.src == 23.158.56.196 && http`
* <img width="1413" height="70" alt="{886F3977-710E-4D2D-B144-2C1BDBF2428A}" src="https://github.com/user-attachments/assets/6f0b2c67-abca-4a3a-851d-ac0cf9140a38" />
* Tìm đọc gói tin như trên và ta được server có version là : 2023.11.3
* <img width="1132" height="122" alt="{2149D019-3F92-4F71-A75B-BBED884BA264}" src="https://github.com/user-attachments/assets/3ef2c3eb-10a3-483b-83ae-482cf8fd25cc" />
## Câu hỏi 3: Sau khi xác định phiên bản dịch vụ máy chủ web của chúng tôi, số CVE nào tương ứng với lỗ hổng mà kẻ tấn công đã khai thác?
* <img width="1278" height="625" alt="{1E6E50EF-C30C-405C-946E-8D8B9D032744}" src="https://github.com/user-attachments/assets/5b17de56-82c8-4172-a660-55a713bb44a1" />
# Câu hỏi 4: Kẻ tấn công đã lợi dụng lỗ hổng này để tạo một tài khoản người dùng. Hắn đã thiết lập thông tin đăng nhập nào?
* Tiếp tục câu hỏi 2 tìm gói `/hax?jsp=/app/rest/users;.jsp`
* <img width="1096" height="283" alt="{66D12889-CB12-4B17-9C57-F8C9ED0D2240}" src="https://github.com/user-attachments/assets/5676a8f4-16d7-4d7f-a398-61847b98362f" />
# Câu hỏi 5: Kẻ tấn công đã tải lên một webshell để đảm bảo quyền truy cập vào hệ thống. Tên tệp mà kẻ tấn công đã tải lên là gì?
* <img width="1093" height="168" alt="{79BAC098-F5F7-4DE6-9827-5D9BDB033BCA}" src="https://github.com/user-attachments/assets/42a54c84-2f2d-4ca6-97cb-624a82723fc1" />
* `/admin/pluginUpload.html:`
# Câu hỏi 6: Kẻ tấn công thực hiện lệnh đầu tiên của chúng thông qua web shell khi nào?
* <img width="747" height="947" alt="{898E9B2A-675C-41A2-AD2C-114606C41B9F}" src="https://github.com/user-attachments/assets/a725b6ed-cf46-44ef-af06-2f958127def6" />
# Câu hỏi 7: Kẻ tấn công đã can thiệp vào một tệp văn bản chứa thông tin đăng nhập của người dùng quản trị máy chủ web. Kẻ tấn công đã ghi tên người dùng và mật khẩu mới nào vào tệp?
* <img width="1041" height="933" alt="{B6D63306-E6BC-4572-8C92-79E39B991076}" src="https://github.com/user-attachments/assets/111ddda2-13cf-4051-b77e-e0e552cb9f2f" />
# Câu hỏi 8: Mã kỹ thuật MITRE cho hành động của kẻ tấn công trong câu hỏi trước (Câu 7) khi giả mạo tệp văn bản là gì?
* <img width="881" height="455" alt="{F388AA13-ED67-4E6A-99BF-0E81CE39725F}" src="https://github.com/user-attachments/assets/6a8999ad-6694-4aa4-abe9-c6b010eb4fbb" />
# Câu hỏi 9: Kẻ tấn công đã cố gắng trốn thoát khỏi container nhưng không thành công. Hắn ta đã sử dụng lệnh gì để làm điều đó?
* ![Uploading {83A73C6E-3A4B-4C1E-B666-92C215DC5F5A}.png…]()

