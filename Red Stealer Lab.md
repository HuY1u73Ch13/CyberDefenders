## Kịch bản : Bạn là thành viên của nhóm Threat Intelligence tại SOC (Trung tâm điều hành bảo mật). Một tệp thực thi đã được phát hiện trên máy tính của một đồng nghiệp và bị nghi ngờ có liên kết đến máy chủ Command and Control (C2), cho thấy khả năng bị nhiễm phần mềm độc hại.
Nhiệm vụ của bạn là điều tra tệp thực thi này bằng cách phân tích hàm băm của nó. Mục tiêu là thu thập và phân tích dữ liệu có lợi cho các thành viên SOC khác, bao gồm nhóm Phản ứng sự cố, để ứng phó hiệu quả với hành vi đáng ngờ này.
## Câu hỏi 1: Phân loại phần mềm độc hại giúp hiểu rõ hơn và nhanh hơn về các hành vi và vectơ tấn công độc đáo của nó. Microsoft đã xác định loại nào cho phần mềm độc hại đó trong VirusTotal?
*  ![{FAD82DEA-11D2-4B4F-AEB8-0F670EEC609E}](https://github.com/user-attachments/assets/e7852f92-633c-4049-98d0-da2b12fff470)
*  Nhìn vào virustotal ta thấy nó được phân loại là trojan. Và Theo định nghĩa của TroJan là một loại của phần mềm (malware) giả dạng như phần mềm hợp pháp để lừa người dùng và thực thi. Khi nó chạy lên thì thực hiện hành vi độc hại như  
** Cài cửa hậu BackDoor để kẻ tấn công có thể truy cập từ xa    
** Ghi lại bàn phím (keylogger) để đánh cắp mật khẩu  
** Tải xuống phần mềm độc hại khác  
** Xóa thay đổi hoặc mã hóa dữ liệu  
** Dùng máy tính làm botnet  
## Câu hỏi 2: Việc xác định rõ ràng tên của tệp phần mềm độc hại sẽ cải thiện khả năng giao tiếp giữa nhóm SOC. Tên tệp liên quan đến phần mềm độc hại này là gì?
* ![{E64EA8C2-4C60-4101-ABFE-517C7928ED5A}](https://github.com/user-attachments/assets/73993601-d288-4052-b1ec-523c0d45f1d9)
## Câu hỏi 3: Biết được dấu thời gian chính xác khi phần mềm độc hại được phát hiện lần đầu có thể giúp ưu tiên các hành động ứng phó. Phần mềm độc hại mới được phát hiện có thể cần phải ngăn chặn và loại bỏ khẩn cấp so với các mối đe dọa cũ hơn, được ghi chép rõ ràng. Dấu thời gian UTC của lần đầu tiên phần mềm độc hại được gửi đến VirusTotal là gì?  
* ![{137BF65A-0416-4197-B0DC-F6245A9CD934}](https://github.com/user-attachments/assets/49bc4d68-337f-404b-9877-f3e07bb42205)
* Câu trả lời ta có được là `Frist Submission: 2023-10-06 04:41` 
## Câu hỏi 4: Understanding the techniques used by malware helps in strategic security planning. What is the MITRE ATT&CK technique ID for the malware's data collection from the system before exfiltration?
* Tôi được một số gợi ý là hãy chú ý các từ khóa là `collection` và `data from system` nên tôi đã tìm ra mã ID MITRE ATT&CK ở trên VirusTotal.
* ![image](https://github.com/user-attachments/assets/eb2ecf31-76c5-4603-8338-f7a0392c4ac0)
## Câu hỏi 5: Sau khi thực thi, phần mềm độc hại đã phân giải tên miền liên quan đến phương tiện truyền thông xã hội nào thông qua truy vấn DNS?
* ![{52B5860B-7CEF-4939-A2B5-C857F8F77A99}](https://github.com/user-attachments/assets/858fb17c-6ae4-4226-9ae6-c6fb752e243d)
## Câu hỏi 6: Sau khi xác định được địa chỉ IP độc hại, các thiết bị bảo mật mạng như tường lửa có thể được cấu hình để chặn lưu lượng truy cập đến và đi từ các địa chỉ này. Bạn có thể cung cấp địa chỉ IP và cổng đích mà phần mềm độc hại giao tiếp không?
* ![{F2AF3794-83A5-4F79-89D1-7F8411BAADBF}](https://github.com/user-attachments/assets/df33fa9c-52fb-4e1b-a16f-273b4c989001)
* ![image](https://github.com/user-attachments/assets/3b419598-af09-47a8-829b-66117e4016a6)
## Câu hỏi 7: Quy tắc YARA được thiết kế để xác định các mẫu và hành vi cụ thể của phần mềm độc hại. Sử dụng MalwareBazaar, tên của quy tắc YARA do " Varp0s" tạo ra để phát hiện phần mềm độc hại đã xác định là gì?
* ![{A8303442-E8BD-469E-B8A3-ABC5F0966EF9}](https://github.com/user-attachments/assets/f8c51150-2eb2-451c-bc53-dd82c0819405)
* Tôi thử search như này trên MALWARE BAZAAR thì được như trên ảnh sau thi bấm vào và lướt xuống thì ta thấy kết quả của câu trả lời này,
* `detect_Redline_Stealer` 
## Câu hỏi 8: Hiểu được nhóm phần mềm độc hại nào đang nhắm vào tổ chức sẽ giúp lập kế hoạch bảo mật chiến lược cho tương lai và ưu tiên các nguồn lực dựa trên mối đe dọa. Bạn có thể cung cấp các bí danh phần mềm độc hại khác nhau liên quan đến địa chỉ IP độc hại theo ThreatFox không?
* 
## Câu hỏi 9: Bằng cách xác định các DLL được nhập của phần mềm độc hại, chúng tôi có thể cấu hình các công cụ bảo mật để theo dõi việc tải hoặc sử dụng bất thường các DLL cụ thể này. Bạn có thể cung cấp DLL được phần mềm độc hại sử dụng để leo thang đặc quyền không?
* 
