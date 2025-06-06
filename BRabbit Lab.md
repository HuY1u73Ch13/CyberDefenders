## Câu hỏi 1: Email lừa đảo được sử dụng để gửi tệp đính kèm độc hại cho thấy một số dấu hiệu của nỗ lực kỹ thuật xã hội tiềm ẩn. Nhận biết các dấu hiệu này có thể giúp xác định các mối đe dọa tương tự trong tương lai. Địa chỉ email đáng ngờ đã gửi tệp đính kèm là gì?
* ![{89F82836-92C4-4A2F-BF59-A0A168AB0494}](https://github.com/user-attachments/assets/40230079-7479-41f3-9fb7-fd0aab086bff)
* Đầu tiên tôi giải nén trên window thì thấy nó có 1 file warning.txt thì tôi mang file này vào máy ảo Kali của tôi để giải nén.
* ![{A5C52792-C561-4FD4-AAC9-5E6980AC9EE7}](https://github.com/user-attachments/assets/aa4a2323-6fe9-4b9c-8c88-043893edac0f)
* Tôi thử dùng lệnh less và cho nó ta file note.txt của tôi để tôi dễ xem file file tôi mới giải nén
* ![{B67FFB37-7DAD-409D-AED6-EAA1A1583EA4}](https://github.com/user-attachments/assets/7ec3a425-8aa1-42fd-b6fe-54beb69f1972)
* Quan sát file note.txt ta thấy 1 địa chỉ mail như trên.
* ![{648EC066-0D8F-4482-8EF7-6386398ABC50}](https://github.com/user-attachments/assets/d38bd7c1-6b48-45d3-9042-3a3e020c280f)
* `https://eml-analyzer.herokuapp.com/#/` Ta cũng có thể truy cập vào trang web này để biết view rõ hơn.
## Câu hỏi 2: Ransomware được xác định là một phần của họ phần mềm độc hại đã biết. Việc xác định tên họ của nó có thể cung cấp thông tin chi tiết quan trọng về hành vi và chiến lược khắc phục của nó. Tên họ của ransomware được xác định trong quá trình điều tra là gì?
* ![{BCADFB32-1878-419B-89A5-263AC15EDAC8}](https://github.com/user-attachments/assets/ac1edee9-a061-4a49-a452-a28952dd2ba6)
* Trong khi đọc phần nội dung của file `Urget Contract Action.eml` ta thấy được 1 file thực thi `.exe` giả dạng file PDF được mã hóa base64 đề chèn vào email này.
* Vì lần giải nén trước tôi không thể tìm thấy được file .exe này nên tôi đã dùng `munpack` từ để trích xuất file đính kèm từ .eml
* ![{EB3FCD70-ED7B-4370-93EA-85DB86CC2CF0}](https://github.com/user-attachments/assets/95ea463a-6584-43d0-8b85-af660c249ac6)
* Ném nó lên từ VirusTotal ta có tên đúng của file virus này là `FlashUtil.exe`
* ![image](https://github.com/user-attachments/assets/55c7d6e5-8edd-4bad-8326-12dfddcd571e)
* Tra family name của nó trên mạng ta được cái tên là `BadRabbit`
## Câu hỏi 3: Khi thực hiện, ransomware thả một tệp vào hệ thống bị xâm nhập để khởi tạo tải trọng của nó. Việc xác định tệp này là điều cần thiết để hiểu quy trình lây nhiễm của nó.Tên của tệp đầu tiên mà ransomware thả là gì?
* ![image](https://github.com/user-attachments/assets/3b8e6e0d-5842-484f-9afd-f907518d3b00)
* `https://tria.ge/250527-1lmmvszkz2/behavioral1` tôi đọc report từ trang này và biết được là
* `C:\Users\Admin\AppData\Local\Temp\630325cac09ac3fab908f903e3b00d0dad...exe` đây là file gốc của thư mục được thực thi. Tiếp theo sau khi thực thi tôi biết được là nó đã chạy `rundll32.exe` để thực thi payload trong file `infpub.dat`.
## Câu hỏi 4: Bên trong tệp bị thả, phần mềm độc hại chứa các hiện vật được mã hóa cứng, bao gồm tên người dùng và mật khẩu có thể cung cấp manh mối về nguồn gốc hoặc cấu hình của nó.Tên người dùng duy nhất được tìm thấy trong tệp bị thả là gì?
* 
## Câu hỏi 5: Sau khi thực hiện, ransomware đã giao tiếp với máy chủ C2. Nhận biết các kỹ thuật giao tiếp của nó có thể hỗ trợ giảm thiểu. Kỹ thuật phụ nào của MITRE ATT&CK mô tả việc ransomware sử dụng giao thức web để gửi và nhận dữ liệu?
* ![image](https://github.com/user-attachments/assets/a8f110d1-aa56-4d69-936a-da525b4e04f7)
* ![{47F96FD1-3E40-4715-B2AC-D7B8062B9FD8}](https://github.com/user-attachments/assets/cb290a2e-16aa-4d12-b1f5-8fc1370317d4)
* Dựa vào những gợi ý tôi tìm được kỹ thuật MITRE ATT&CK đấy là `T1071.001`
## Câu hỏi 6: Cơ chế bền bỉ là đặc điểm của ransomware tinh vi. Việc xác định cách đạt được sự bền bỉ có thể hỗ trợ phục hồi và ngăn ngừa tái nhiễm. ID kỹ thuật phụ MITRE ATT&CK liên quan đến kỹ thuật bền bỉ của ransomware là gì?
* ![{2D4F12FB-41CE-42C7-A79D-12A6CB661D2A}](https://github.com/user-attachments/assets/57cb4f0d-b984-46da-bb05-ecfbe99e6a42)
## Câu hỏi 7: Là một phần của chuỗi lây nhiễm, ransomware đã tạo ra các tác vụ cụ thể để đảm bảo hoạt động liên tục của nó. Việc nhận ra các tác vụ này rất quan trọng để khôi phục hệ thống. Tên của các tác vụ được ransomware tạo ra trong quá trình thực thi là gì?
* ![{1355B1D0-6EEB-4129-9ABE-34D705488499}](https://github.com/user-attachments/assets/bd23e1e9-6533-4fae-b6b2-54118e8cf455)
* ![{FA062FDD-43A3-42EA-BAE3-D4F61A41CF31}](https://github.com/user-attachments/assets/8b45b62e-4b50-47fe-8932-2471c9007ebf)
* Ta có thể thấy câu lệnh thứ nhất `/c schtasks /Delete /F /TN rhaegal` là xóa ngay lập tức task tên `rhaegal` khỏi hệ thống mà không cần hỏi người dùng.
* Ta có thể thấy câu lệnh thứ hai `/c schtasks /Create /SC once /TN drogon /RU SYSTEM /TR "C:\Windows\system32\shutdown.exe /r /t 0 /f" /ST 18:44:00` 
* Lệnh này tạo ra một task "drogon" để khởi động lại thể thống ngay lặp tức vào lúc 18:44 chạy dưới tài khoản SYSTEM.
## Câu hỏi 8: nhị phân độc hại dispci.exe hiển thị thông báo đáng ngờ khi thực thi, thúc giục người dùng vô hiệu hóa khả năng phòng thủ của họ. Chiến thuật này nhằm mục đích tránh bị phát hiện và cho phép thực thi toàn bộ ransomware. Thông báo đáng ngờ nào được hiển thị trong Console khi thực thi nhị phân này?
* ![{3F81C6CB-5796-4320-9A26-658C4B62DDA6}](https://github.com/user-attachments/assets/b00474ca-b58c-4615-a41b-10176fac4c1d)
* Xem trên AnyRun ta thấy `Disable your anti-virus and anti-malware programs` người ta có demo câu lệnh chạy.
## Câu hỏi 9: Để sửa đổi Master Boot Record (MBR) và mã hóa ổ cứng của nạn nhân, ransomware đã sử dụng một trình điều khiển cụ thể. Việc nhận ra trình điều khiển này là điều cần thiết để hiểu cơ chế mã hóa.Tên của trình điều khiển được sử dụng để mã hóa ổ cứng và sửa đổi MBR là gì?
* ![{59F48C3A-B75E-498C-A958-490C23193972}](https://github.com/user-attachments/assets/bf73eec9-65f8-4a49-86d4-c2a5198f1a5a)
## Câu hỏi 10: Việc quy kết là chìa khóa để hiểu bối cảnh mối đe dọa. Ransomware được liên kết với một nhóm tấn công đã biết thông qua các chiến thuật, kỹ thuật và quy trình (TTP) của nhóm này.Tên của tác nhân đe dọa chịu trách nhiệm cho chiến dịch ransomware này là gì?
* ![{8DD70A7C-B244-4FDC-B537-750CE86CDA62}](https://github.com/user-attachments/assets/0a5ab829-6a32-495a-a5f7-f5e3c835eb7d)
* https://attack.mitre.org/software/S0606/
* Tìm theo tên của phần mềm BadRabbit
## Câu hỏi 11: Phần mềm tống tiền khiến hệ thống không thể khởi động bằng cách làm hỏng các thành phần hệ thống quan trọng. Việc xác định kỹ thuật được sử dụng sẽ cung cấp thông tin chi tiết về khả năng phá hoại của nó.ID MITRE ATT&CK cho kỹ thuật được sử dụng để làm hỏng chương trình cơ sở hệ thống và ngăn chặn khởi động là gì?
* ![{0F44C548-70F8-4A59-8377-7ED90BE56C87}](https://github.com/user-attachments/assets/1dd11d5e-d6f3-491b-8e78-3ab3d323ff42)
* Bad Rabbit has used an executable that installs a modified bootloader to prevent normal boot-up.

