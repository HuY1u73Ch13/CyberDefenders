## Câu hỏi 1: Tên của tiến trình đáng ngờ này là gì?
* ![image](https://github.com/user-attachments/assets/f2277926-ce76-4a11-ae2a-9b1891f59853)
* Ta thấy tên tiến trình này lạ và không có đường dẫn cụ thể nên tôi nghi ngờ đây là tệp virus
## Câu hỏi 2: Tên tiến trình con của tiến trình đáng ngờ là gì?
* ![{94499128-0BA4-49F3-8441-33DF83ED12B5}](https://github.com/user-attachments/assets/229c481e-fd57-4307-9d15-fd248ee71f7d)
* Dựa vào số PPID ta có thể tìm ra được tiến trình con của tiến trình oneetx.exe là rundll32.exe
## Câu hỏi 3: Chế độ bảo vệ bộ nhớ được áp dụng cho vùng bộ nhớ của quy trình đáng ngờ là gì?
* `PAGE_EXECUTE_READWRITE`
## Câu hỏi 4: Tên của tiến trình chịu trách nhiệm cho kết nối VPN là gì?
* `python .\vol.py -f "C:\Users\Admin\Downloads\106-RedLine\temp_extract_dir\MemoryDump.mem" windows.netscan`
* Dùng câu lệnh này để tìm những tiến trình nào có kết nối ra bên ngoài ta thấy tiến trình `tun2socks.exe`
* `python vol.py -f "C:\Users\Admin\Downloads\106-RedLine\temp_extract_dir\MemoryDump.mem" windows.pslist`
* Dùng tiếp câu lệnh này để tìm tiến trình cha của tiến trình này `tun2socks.exe`
* ![image](https://github.com/user-attachments/assets/62bde64c-3927-4bf8-a419-614e46d4e2b5)
* Ta tìm thấy được `Outline.exe` là tiến trình chịu trách nhiệm cho kết nối VPN này
## Câu hỏi 5: Địa chỉ IP của kẻ tấn công là gì?
![image](https://github.com/user-attachments/assets/0898af93-066e-4e5b-b5f3-488fe6ceff0e)
## Câu hỏi 6: URL đầy đủ của tệp PHP mà kẻ tấn công đã truy cập là gì?
* Đầu tiên ta biết mục tiêu là đường dẫn chứa file chuỗi URL sẽ vẫn tồn tại trong ram ngay cả khi tiến trình không chạy nữa hoặc là bị xóa
* Vậy nên đầu tiên ta sẽ dùng String để lọc ra tất cả các chuỗi trong file `MemoryDump.mem`
* Dùng `strings "C:\Users\Admin\Downloads\106-RedLine\temp_extract_dir\MemoryDump.mem" > C:\Users\Admin\Downloads\strings_output.txt ` để in ra các chuỗi vào file `strings_output.txt`
* Tiếp theo ta dùng `Select-String ".php" -Path "C:\Users\Admin\Downloads\strings_output.txt"` để chọn ra những chuỗi có tên php trong đấy. Sau khi lọc xong ta tìm thấy được
* ![{06F6F137-BF3C-4F8A-A2F8-54C046E8CEEA}](https://github.com/user-attachments/assets/a1a19b6d-bc26-4667-b71d-51cb0c926966)
* Đây là URL đầy đủ của file php mà kẻ tấn công đã truy cập
## Câu hỏi 7: Đường dẫn đầy đủ của tệp thực thi độc hại là gì?
* Chúng ta tận dụng file `strings_output.txt` như ở câu trên và thay đổi 1 chút thành
* `Select-String ".exe" -Path "C:\Users\Admin\Downloads\strings_output.txt"`
* Và chúng ta tìm theo tên tiến trình đáng ngờ ở câu 1 là `oneetx.exe` và chúng ta tìm thấy
* ![{EAE1BDFE-34C8-483C-8B00-79E570F225D6}](https://github.com/user-attachments/assets/fd9ca8f4-96a5-4326-994a-3b8c8bb1cf94)
* Suy ra ta có câu trả lời là `C:\Users\Tammam\ AppData\Local\Temp\c3912af058\oneetx.exe` 




  
