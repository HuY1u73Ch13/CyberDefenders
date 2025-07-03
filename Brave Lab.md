## Câu hỏi 1: Theo hệ thống nghi ngờ, hình ảnh RAM được thu thập vào thời điểm nào?
* Đầu tiên chúng ta sử dụng volatility3 để phân tích file mem này
* Chúng ra vào thư mục volatility3 và sử dụng command `python vol.py -f "D:\Downloands\67-AfricanFalls2\temp_extract_dir\c49-AfricanFalls2\20210430-Win10Home-20H2-64bit-memdump.mem" windows.info`
* Để phân tích file mem và lấy thông tin về thanh mem này và ta được
* ![{7F8F2850-C10D-4D24-95C7-1C021A2671CC}](https://github.com/user-attachments/assets/e03bb5a7-2d9a-45d4-9c7d-01e28520d888)
## Câu hỏi 2: Giá trị băm SHA256 của hình ảnh RAM là gì?
* Tiếp theo ta sử dụng
* ![{71C007F1-6496-4070-85CA-750591053644}](https://github.com/user-attachments/assets/f9d292b5-9db4-4499-9a05-40d146e8d619)
* Để lấy được mã sha256.
## Câu hỏi 3: ID tiến trình của brave.exe là gì ?
* `python ./vol.py -f "D:\Downloands\67-AfricanFalls2\temp_extract_dir\c49-AfricanFalls2\20210430-Win10Home-20H2-64bit-memdump.mem" windows.pslist`
* ![{02B2AE11-6C42-43E2-908A-F0E1FDC32F10}](https://github.com/user-attachments/assets/0e9aeb3e-4ca7-49cb-a3c4-14d5dae94363)
## Câu hỏi 4: Có bao nhiêu kết nối mạng đã được thiết lập tại thời điểm mua lại?
* 
## Câu hỏi 5: Chrome đã thiết lập kết nối mạng với tên miền nào?
*
## Câu hỏi 6: Giá trị băm MD5 của tiến trình thực thi cho PID 6988 là gì ?
*
## Câu hỏi 7: Bạn có thể xác định từ bắt đầu ở vị trí 0x45BE876 và dài 6 byte không?
*
## Câu hỏi 8: Ngày và giờ tạo của tiến trình cha của powershell.exe là gì ?
*
## Câu hỏi 9: Đường dẫn đầy đủ và tên của tập tin cuối cùng được mở trong Notepad là gì?
*
## Câu hỏi : Nghi phạm đã sử dụng trình duyệt Brave trong bao lâu ? (Tính bằng giờ)
*
