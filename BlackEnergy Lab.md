## Readme
* Đầu tiên tôi tải về file raw nhưng tôi cũng không biết file raw là file gì.
* Thì sau 1 lúc tìm hiểu tôi biết được file .raw trong forensic là file ảnh bộ nhớ RAM(Memory Dump)
* Nó là bản sao byte-to-byte của RAM tại thời điểm dump
## Câu hỏi 1: Hồ sơ độ biến động nào sẽ tốt nhất cho máy này?
* ![{50DC84CA-357E-4E8F-A236-0582FAFE9DC4}](https://github.com/user-attachments/assets/a03c7ceb-00ea-44f9-8c6a-f5fb0b19fcd9)
* Ta có thể thấy được nó đã được dump từ máy `WinXPSP2x86` `WinXP`
## Câu hỏi 2: Có bao nhiêu tiến trình đang chạy khi hình ảnh được chụp?
* 
## Câu hỏi 3: ID tiến trình của là gì cmd.exe?
* ![{6D2B9DC5-6958-4196-BC6F-32211062D9A1}](https://github.com/user-attachments/assets/9c9a605e-6e44-42de-bb09-4ecb8371446a)
## Câu hỏi 4: Tên của tiến trình đáng ngờ nhất là gì?
* ![{21F4DDF7-93DA-4D73-BA98-F4C63DCAE259}](https://github.com/user-attachments/assets/3c8dd560-674e-4955-99df-e820b5ccf7e1)
* Ta thấy rootkit.exe ta có thể thấy được là thời gian khởi tạo nó là `2023-02-13 18:25:26` và thời gian thoát là `2023-02-13 18:25:26` rất khả nghi vì hành vi tự xóa ở malware rất phổ biến.
* Tiến trình thông thường (user mở notepad, trình driver, service) ít khi tồn tại 0s.
## Câu hỏi 5: Tiến trình nào có khả năng bị chèn mã cao nhất?
* ![{7F42339E-D824-4A95-9D5E-1FF6C4E2D489}](https://github.com/user-attachments/assets/069b814f-2732-4bc4-aac3-6f80eb044f5d)
* Vì `svchost.exe` là một tiến trình hệ thống quan trong của window, nó đươc thiết kế để trở thành 1 phần không thiếu của hệ điều hành và nhóm nhiều dịch vụ window vào 1 tiến trình
* Nó thường được các attacker dùng để chạy các thư viện và liên kết động(DLL) dưới dạng dịch vụ hợp pháp.
## Câu hỏi 6: Có một tệp lạ được tham chiếu trong quy trình gần đây. Cung cấp đường dẫn đầy đủ của tệp đó.
* 
## Câu hỏi 7: Tên của tệp DLL được đưa vào từ tiến trình gần đây là gì?
*
## Câu hỏi 8: Địa chỉ cơ sở của DLL được tiêm là gì?
*
