## Câu hỏi 1: Nhiều luồng chứa macro trong tài liệu này. Cung cấp số của luồng cao nhất.
* Tải oledump trên này `https://didierstevens.com/files/software/` và giải nén thư mục ra để tìm
* `python3 oledump.py /mnt/d/Downloands/51-maldoc101/temp_extract_dir/MalDoc101/sample.bin` dùng command này để tìm được câu trả lời.
* ![{759CC602-1FE7-4CEE-A122-679D530B7D6D}](https://github.com/user-attachments/assets/12be719a-33f5-47c3-8f4b-46de36d41a10)
* Ta thấy M lớn là chứa macro và m có thể chứa macro nhưng không chắc chắn.
* Suy ra đáp án là 16 vì m vẫn tính là 1 steam có Macro
## Câu hỏi 2: Sự kiện nào được sử dụng để bắt đầu thực thi các macro?
* ![{35D09C80-D58A-406F-B8F8-789D942E4F39}](https://github.com/user-attachments/assets/c04c96c1-8a46-4485-85b0-b1159169d085)
* Dùng câu lệnh này để phân tích các và giải mã nội dung VBA, thì khi trích xuất file `steam 13` ta thấy có hàm Document_Open() tức là khi người dùng mở document nó sẽ tự động gọi đến hàm `boaxvoebxiotqueb` ở câu 15. 
## Câu hỏi 3: Maldoc này đang cố gắng phát tán loại phần mềm độc hại nào?
* Up file `sample.bin` lên trang `virustotal` ta thấy được family name là
* ![{5692508D-8B74-47D7-96BE-C04DD78EA8CD}](https://github.com/user-attachments/assets/12ced8a3-72d2-42b0-8d94-ee2621e3ed6a)
## Câu hỏi 4: Luồng nào chịu trách nhiệm lưu trữ chuỗi được mã hóa base64?
* `python3 oledump.py /mnt/d/Downloands/51-maldoc101/temp_extract_dir/MalDoc101/sample.bin  -v` dùng câu lệnh này để phân tích xem các steam và thấy steam 34 có dung lượng rất lớn
* ![{AE71F667-3255-48C8-9A46-12D3CD471D9A}](https://github.com/user-attachments/assets/ea36dd43-df27-429b-9773-9d2e4499289f)
* Rất có thể đây là nơi lưu trữ payload được mã hóa base64 và tôi thử xem nội dung VBA steam 34.
* ![{3E2467D6-DFA6-4384-B599-44BEAD97DE37}](https://github.com/user-attachments/assets/46cdead5-7eb7-4868-a80c-614f0539c180)
* Và đúng câu trả lời là 34.
## Câu hỏi 5: Tài liệu này có chứa biểu mẫu người dùng. Cung cấp tên.
* ![{86AFCD3E-5FE7-47D3-80D4-94B50429AB27}](https://github.com/user-attachments/assets/9af6a827-54b6-4925-aa82-276eab4408a6)
* Ta có thể thấy được là `roubhaol` là thư mục cha của các thư mục bên dưới bao gồm `i05,i07,i09,...`
## Câu hỏi 6: Tài liệu này chứa một chuỗi được mã hóa Base64 bị che giấu; giá trị nào được sử dụng để thêm vào (hoặc che giấu) chuỗi này?
* `2342772g3&*gs7712ffvs626fq`
* ![{98908545-C8AB-4B81-8EA2-A9BFED530B7A}](https://github.com/user-attachments/assets/1c2611a5-0041-4c6e-8410-673916760aec)
* Ta có thể thấy đây là chuỗi base64 dùng để chống phân tích thẳng base64
## Câu hỏi 7: Chương trình nào được thực thi bởi chuỗi được mã hóa Base64?
* `powershell`
## Câu hỏi 8: Lớp WMI nào được sử dụng để tạo quy trình khởi chạy Trojan?
* `Win32_Process`
## Câu hỏi 9: Nhiều tên miền đã được liên hệ để tải xuống Trojan. Cung cấp FQDN đầu tiên theo gợi ý được cung cấp.
* ![{8EADE4B6-3531-4739-AA61-19D2ED97447B}](https://github.com/user-attachments/assets/8bcda937-2380-4838-bc6f-6a027db822e9)


