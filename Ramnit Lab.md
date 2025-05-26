## Câu hỏi 1: Tên của tiến trình chịu trách nhiệm cho hoạt động đáng ngờ này là gì?
* Đâu tiên tôi thử dùng tham số `windows.psscan` trong lệnh `vol.py` để quét các tiến trình của nó theo phương pháp tìm kiếm chữ ký . Nhưng tôi không thấy gì và không có gì có ích.
* Nên là tôi đã thử dùng tham số khác là `windows.cmdline` để hiển thị các câu lệnh mà có thể atacker có thể đã dùng và cũng như các câu lệnh mà atacker đã chạy và tôi phát hiện ra được 1 tiến trình lạ như sau
* `PS C:\Users\Admin\volatility3> python .\vol.py -f "C:\Users\Admin\Downloads\159-Ramnit\temp_extract_dir\memory.dmp" windows.cmdline`
* ![{6182ED6B-2C4F-4FA4-BE13-8C5FFD1BB43B}](https://github.com/user-attachments/assets/45fb25ea-47c6-4ac5-bf61-36fc40e0e8ba)
* Và đó là ChromeSetup.exe
## Câu hỏi 2: Đường dẫn chính xác của tệp thực thi cho tiến trình độc hại là gì?
* Đường dẫn được tôi chụp ở hình ảnh ở trên câu 1
* `C:\Users\alex\Downloads\ChromeSetup.exe`
## Câu hỏi 3: Việc xác định kết nối mạng rất quan trọng để hiểu được chiến lược truyền thông của phần mềm độc hại. Phần mềm độc hại đã cố gắng kết nối đến địa chỉ IP nào?
* Tôi dùng tham số `windows.netscan` để liệt kê tất cả các kết nối mạng (TCP/UDP/socket) đuọc tìm thấy trong bộ nhớ Ram dump và tôi đã thấy được ipsrc và ipaddr như hình ở bên dưới
* ![{96E6614E-A2D9-4686-8313-E187FEA821F7}](https://github.com/user-attachments/assets/650eaa17-4097-4557-8cfa-104774841488)
## Câu hỏi 4 : Để xác định nguồn gốc địa lý cụ thể của cuộc tấn công, thành phố nào được liên kết với địa chỉ IP mà phần mềm độc hại truyền tin?  
* Địa chỉ địa lý của ip `58.64.204.181` là ở HONG KONG
* ![{34CB1D20-9BF7-4E66-B3E6-5185958431C5}](https://github.com/user-attachments/assets/76cbbc08-1ebc-4baa-8f9e-b6f65ba7dcd2)
## Câu hỏi 5 : Hash đóng vai trò là mã định danh duy nhất cho các tệp, hỗ trợ phát hiện các mối đe dọa tương tự trên nhiều máy khác nhau. Hash SHA1 của phần mềm độc hại thực thi là gì?
* `python vol.py -f C:\Users\Admin\Downloads\159-Ramnit\temp_extract_dir\memory.dmp -o "dump" windows.dumpfile --pid 4628`
* Dùng câu lênh này để trích xuất các process có pid là 4628 rồi trích xuất vào thư mục dump
* `file.0xca82b85325a0.0xca82b7e06c80.ImageSectionObject.ChromeSetup.exe-1.img` ta đưa file này lên virus total để phân tích và để lấy mã SHA-1
* ![{7712CF35-AB17-4222-B691-A497E7AFAA55}](https://github.com/user-attachments/assets/0f646e86-8319-4581-8c67-16895019d688)
* ![{4C6C7640-382B-4707-99DC-8FF99EDC6C31}](https://github.com/user-attachments/assets/b901ac5f-557f-416a-ae97-f6002731aeab)
## Câu hỏi 6: Kiểm tra mốc thời gian phát triển của phần mềm độc hại có thể cung cấp thông tin chi tiết về quá trình triển khai của nó. Dấu thời gian biên dịch cho phần mềm độc hại là gì?
* ![{EFC6AC15-508E-460C-A2F6-71CE2A1A06FE}](https://github.com/user-attachments/assets/7871834b-7cef-4eb0-929a-47ee627c5c32)
* Ta có thể tìm thấy thời gian mà nó creation trên virustotal
## Câu hỏi 7 : Việc xác định các miền liên quan đến phần mềm độc hại này rất quan trọng để chặn các liên lạc độc hại trong tương lai và phát hiện mọi tương tác đang diễn ra với các miền đó trong mạng của chúng tôi. Bạn có thể cung cấp miền được kết nối với phần mềm độc hại không?
![{CF4C3B27-3756-4BBF-A457-09F071C3B888}](https://github.com/user-attachments/assets/0a965c7a-4950-4264-8de0-d69671a1e2b3)





