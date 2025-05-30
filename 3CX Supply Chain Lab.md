## Câu hỏi 1: Hiểu được phạm vi của cuộc tấn công và xác định phiên bản nào thể hiện hành vi độc hại là rất quan trọng để đưa ra quyết định sáng suốt nếu các phiên bản bị xâm phạm này có trong tổ chức. Có bao nhiêu phiên bản 3CX chạy trên Windows đã được gắn cờ là phần mềm độc hại?
* Tôi đã thử tìm kiếm với từ khóa 3CX trên google để xem coi có bao nhiêu phiên bản của 3CX chạy trên window có dính malware  
* ![{7190411B-0FEA-4035-B7CE-DBF74581AFCA}](https://github.com/user-attachments/assets/e1ee3d0c-fc4c-46ce-a6a8-01f4520ec30c)
* ![{0EBA6166-82B2-4024-9A91-98B3D80FBDE9}](https://github.com/user-attachments/assets/0f925e56-429a-4c0e-a7cb-25a159912913)
* Tôi được 1 số thông tin như sau đó là 2 phiên bản 3CX bị nhiễm độc
## Câu hỏi 2: Xác định tuổi của phần mềm độc hại có thể giúp đánh giá mức độ xâm phạm và theo dõi sự phát triển của các họ và biến thể phần mềm độc hại. Thời gian tạo UTC của phần .msimềm độc hại là bao lâu?
* ![{0474DD97-9EF5-4A85-A90D-D4EBD07D375E}](https://github.com/user-attachments/assets/52cfe504-88fa-4e9c-b182-b8252358ed06)
* Ta có thể đơn giản tìm được ngày khỏi tạo của nó trên virus total
## Câu hỏi 3: Các tệp thực thi ( .exe) thường được sử dụng làm tải trọng phần mềm độc hại chính hoặc phụ, trong khi các thư viện liên kết động ( .dll) thường tải mã độc hại hoặc tăng cường chức năng phần mềm độc hại. Phân tích các tệp được gửi bởi Microsoft Software Installer ( .msi) là rất quan trọng để xác định các tệp độc hại và điều tra toàn bộ tiềm năng của chúng. Các tệp DLL độc hại nào đã bị .msitệp này loại bỏ?
* ![{02842A78-2930-4C39-B513-7BA850592D4C}](https://github.com/user-attachments/assets/1239a279-b378-4010-9dd6-0d28aaa5e031)
* Tôi đọc được cái này dựa trên comment của 1 người dùng trên cộng đồng và 2 file đó là `ffmpeg.dll, d3dcompiler_47.dll`
## Câu hỏi 4: Việc nhận ra các kỹ thuật duy trì được sử dụng trong sự cố này là điều cần thiết cho các chiến lược giảm thiểu hiện tại và cải thiện khả năng phòng thủ trong tương lai. ID Kỹ thuật MITRE được các .msi tệp sử dụng để tải DLL độc hại là gì?
* ![{26B3A035-25A2-43D5-A0D2-6B4495DC2CB0}](https://github.com/user-attachments/assets/e35277a0-4bd2-4d19-a0f8-ac45a2aeb1f8)
* Tôi đã thử tìm trên GG với từ khóa như trên và tôi đã vào trang đầu tiên. Và tìm những kỹ thuật MITRE ATT&CK liên quan đến tiến trình dll. Tôi tìm được kỹ thuật T1547,T1546,T1574
* Và có vẻ kỹ thuật MITRE ATT&CK T1574: Hijack Execution Flow là liên quan nhất bởi vì kỹ thuật này rất quan trọng với các cuộc tấn công supply chain như vụ 3CX:
* `supply chain` dịch ra là chuỗi cung ứng là tập hợp các quy trình, tổ chức, con người, hoạt động, thông tin, và tài nguyên liên quan đến việc sản xuất và phân phối dịch vụ - từ nhà cung cấp ban đầu đến người tiêu dùng cuối cùng
## Câu hỏi 5: Việc nhận biết loại phần mềm độc hại ( threat category) là điều cần thiết cho cuộc điều tra của bạn, vì nó có thể cung cấp cái nhìn sâu sắc có giá trị về các hành động độc hại có thể xảy ra mà bạn sẽ kiểm tra. Loại mối đe dọa của hai DLL độc hại là gì?
* Để trả lời cho câu hỏi này ta sẽ lấy mã SHA-256 của 2 tệp dll trên rồi paste vào virus total để xem .
* ![{CFDB30FE-F283-499D-8B45-E41849FC7B46}](https://github.com/user-attachments/assets/a59ac720-85de-4639-b4e3-1fdc74ccf845)
* ![{6BB3FCFD-FCA1-411C-BDF8-A2CC6E8B6561}](https://github.com/user-attachments/assets/1b3c8486-66b0-4f55-bb56-dedf7a7a9003)
* Đáp án là trojan : còn trojan là một loại phầm mềm độc hại được giả dạng dưới kiểu file hoặc phần mềm có ích.


 


