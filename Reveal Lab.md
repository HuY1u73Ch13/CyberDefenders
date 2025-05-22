## Câu hỏi 1: Việc xác định tên của tiến trình độc hại giúp hiểu được bản chất của cuộc tấn công. Tên của tiến trình độc hại là gì?
Đầu tiên tôi tải về file .dmp tôi cũng không biết đấy là file gì. Sau đó tôi đã tìm hiểu được file dump là file dump bộ nhớ, chứa bộ nhớ của toàn ram
Tôi tìm được vài gợi ý là dùng WinDbg để phân tích file .dmp và tôi cũng thử dùng nhưng không tìm được gì. Sau đó tôi chuyển sang tool volatility3 để phân tích 
![{C4FB18C9-E830-42B2-9EC8-3455A0010872}](https://github.com/user-attachments/assets/2c4c2dc5-d22d-4c0e-860c-3cf2bebc2ff9)
Như hình ảnh tôi thấy powershell.exe thì tôi nghĩ đây cũng là tiến trình nguy hiểm vì PowerShell cho phép thực thi các câu lệnh, script phức tạp, quản lý hệ thống, tự động hóa rất nhiều tác vụ. Điều này khiến nó là công cụ yêu thích của nhiều attacker để khai thác, tấn công hoặc thực thi mã độc.
## Câu hỏi 2: Biết ID tiến trình cha (PPID) của tiến trình độc hại giúp theo dõi phân cấp tiến trình và hiểu được luồng tấn công. PID cha của tiến trình độc hại là gì?
![{6EF24DE6-EC94-4BB2-AAA5-773C4C563AA7}](https://github.com/user-attachments/assets/b53486e9-06fb-434e-b8a4-929636b7b6b6)
![{D2AC4E6A-E0D8-456B-B081-D52A1A110A05}](https://github.com/user-attachments/assets/aa300963-f0d7-4b5b-a2da-3803840bfb29)
PID là 	Mã định danh tiến trình còn PPID là Mã định danh tiến trình cha của tiến trình đấy suy ra tiến trình cha của powershell.exe là 4120
## Câu hỏi 3: Việc xác định tên tệp mà phần mềm độc hại sử dụng để thực hiện tải trọng giai đoạn thứ hai là rất quan trọng để xác định các hoạt động độc hại tiếp theo. Tên tệp mà phần mềm độc hại sử dụng để thực hiện tải trọng giai đoạn thứ hai là gì?
