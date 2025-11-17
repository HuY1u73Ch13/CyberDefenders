## Bối cảnh:
* Soc của TechNova System đã phát hiện ra lưu lượng truy cập đáng ngờ của máy chủ IIS công khai trong nền tảng của nó. Hoạt động này gợi ý về hiện tượng rớt web và nó đang kết nối với 1 máy chủ không xác định.
* Là 1 người điều tra pháp y, bạn có 3 bằng chứng trên tay như : Gói pcap lưu lại được từ luồng và lưu lượng truy cập từ ban đầu, tệp hình ảnh bộ nhớ đầy đủ của máy chủ và tệp mã độc được khôi phục lại từ ổ đĩa.
* Tái cấu trúc lại hành vi tấn công của kẻ tấn công để TechNova có thể ngăn chặn sự vi phạm và khả năng phòng thủ của nó.
* Máy chủ IIS là máy gì ?
* Máy chủ IIS là máy chủ chạy hệ điều hành window và bản thân IIS là viết tắt của Internet Information Services. Đây thường là 1 máy chủ web linh hoạt 
## Câu hỏi 1: Sau khi làm nhập IIS với các đầu dò bắn nhanh, kẻ tấn công đã tiết lộ nguồn địa chỉ của chúng. Địa chỉ IP nào đã tạo ra lưu lượng này ?
* <img width="1325" height="97" alt="image" src="https://github.com/user-attachments/assets/926637f6-f45e-43ba-81ca-3b2f3e0c8f84" />
## Câu hỏi 2: Tập trung vào một dịch vụ mở duy nhất để chiếm chỗ đứng, kẻ tấn công thực hiện liệt kê mục tiêu. Mã kỹ thuật MITRE ATT&CK nào bao gồm hoạt động này?
* **zeroing in on a single open service to gain a foothold** dựa theo câu nói tập trung duy nhất vào 1 chỗ tôi tìm kiếm trên internet và kết quả trả được là
* <img width="893" height="398" alt="image" src="https://github.com/user-attachments/assets/1b2f25b9-e5f8-46a1-9931-9f2d86630073" />
## Câu hỏi 3: Khi xem xét lưu lượng SMB, bạn quan sát thấy hai yêu cầu Tree Connect liên tiếp làm lộ các chia sẻ đầu tiên mà kẻ xâm nhập thăm dò trên máy chủ IIS. Hai đường dẫn UNC đầy đủ nào được truy cập?
* <img width="1180" height="173" alt="image" src="https://github.com/user-attachments/assets/44980ecf-4515-4507-9f97-671c891c7706" />
* Lọc gói smb2 ta được kết quả như ảnh trên
## Cảu hỏi 4: Bên trong thư mục chia sẻ, kẻ tấn công cài một payload có thể truy cập web để cấp quyền thực thi mã từ xa. Tên tệp độc hại mà chúng đã tải lên là gì và độ dài byte được chỉ định trong Yêu cầu Ghi SMB2 tương ứng là bao nhiêu?
* Lọc theo gói tin SMB2 tôi có được
* <img width="1647" height="160" alt="image" src="https://github.com/user-attachments/assets/576e727a-5003-4b6c-84a2-2edf2ad08749" />
* Gói tin yêu cầu ghi 1 file lạ là file shell.aspx và từ gói tin đấy tôi vào trường data và kiếm được thônng tin độ dài của file là 1015024
* <img width="681" height="120" alt="image" src="https://github.com/user-attachments/assets/07617503-4aee-457d-892f-825057da22c3" />
## Câu hỏi 5: Shell mới được cài đặt sẽ gọi lại cho kẻ tấn công qua một cổng không phổ biến nhưng thân thiện với tường lửa. Kẻ tấn công đã sử dụng cổng lắng nghe nào cho shell đảo ngược?
* Ở đây chúng ta cần tìm 1 gói tin được gửi từ máy nạn nhân về máy người tấn công nên tôi lọc theo địa chỉ **ip.addr == 10.0.2.4** để mong muốn tìm ra các gói tin có địa chỉ gửi đến là 10.0.2.4
* Và tôi tìm được gói tin ngưới đây
* <img width="1838" height="554" alt="image" src="https://github.com/user-attachments/assets/bd8baa81-777c-4ec4-831b-1f5ad9582d8a" />
## Câu hỏi 6: Ảnh chụp nhanh bộ nhớ của bạn sẽ ghi lại nhân hệ thống tại chỗ, cung cấp bối cảnh quan trọng cho vụ xâm nhập. Địa chỉ cơ sở nhân trong bản sao lưu là gì?
* <img width="980" height="170" alt="image" src="https://github.com/user-attachments/assets/2605880b-494c-4435-a6b7-c4ebefd322ab" />
* Câu hỏi hỏi địa chi cơ sở của máy nạn nhân nên chúng ta sẽ dùng plugin info để biết được địa chỉ cơ sở của máy nạn nhân.
## Câu hỏi 7: Một dịch vụ đáng tin cậy khởi chạy một tệp thực thi lạ nằm ngoài ngăn xếp IIS thông thường, báo hiệu một lệnh cấy ghép mã độc. Đường dẫn đầy đủ cuối cùng trên đĩa của tệp thực thi đó là gì và ID kỹ thuật mã hóa mã độc MITRE ATT&CK nào tương ứng với hành vi này?
* <img width="1371" height="343" alt="image" src="https://github.com/user-attachments/assets/d5d45e66-f6b0-4770-942c-dd729a55b463" />
* Thử tìm tiến trình lạ qua plugin cmd.line ta thấy được tệp lạ có tên là updatenow.exe dựa vào đường dẫn ta thấy được nó được đặt vào đường dẫn C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup\updatenow.exe
* Tức là thư mục này được đặt vào thư mục startup của window có nghĩa là nó sẽ khởi động cùng lúc với window 
* <img width="1063" height="537" alt="image" src="https://github.com/user-attachments/assets/f26463cc-3cbc-4b04-975a-37142b5f7b99" />
* Tôi tìm trên mạng với từ khóa này thì tìm ra được kĩ thuật tấn công đấy.
## Câu hỏi 8: Lưu lượng ra của shell ngược được xử lý bởi một tiến trình Windows tích hợp, tiến trình này cũng tạo ra tệp thực thi được cấy ghép. Tên của tiến trình này là gì và nó chạy dưới PID nào?
* <img width="915" height="77" alt="image" src="https://github.com/user-attachments/assets/66c47287-ddb1-46a7-9d71-a195932fcb2c" />
* Từ Scan của plugin cmdLine tôi thấy w3wp.exe có nghi ngờ nên tôi thử tìm PID của w3wp.exe bằng plugin pstree và tôi có thể tìm được PID của
## Câu hỏi 9: Kiểm tra tĩnh cho thấy tệp nhị phân đã được đóng gói để cản trở việc phân tích. Trình đóng gói nào đã được sử dụng để làm tối nghĩa nó?
* <img width="1227" height="812" alt="image" src="https://github.com/user-attachments/assets/8e3cf428-cf7c-4a1c-a5d5-9997a0609155" />
* Vào VirusTotal tôi sang phần detail dòng cuối cùng của ảnh có thể thấy malware này được đóng gói bằng UPX
## Câu hỏi 10: Phân tích tình báo mối đe dọa cho thấy phần mềm độc hại đang chuyển hướng đến máy chủ chỉ huy và kiểm soát của nó. Nó sẽ liên hệ với tên miền đủ điều kiện (FQDN) nào?
* 
## Câu hỏi 11: Intel nguồn mở liên kết hàm băm đó với một loại mã độc RAT phổ biến. Mẫu này thuộc họ phần mềm độc hại nào?
* 
