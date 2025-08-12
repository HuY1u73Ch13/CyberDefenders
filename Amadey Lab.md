## Câu hỏi 1: Trong phân tích kết xuất bộ nhớ, việc xác định gốc rễ của hoạt động độc hại là điều cần thiết để hiểu rõ mức độ xâm nhập. Tên của tiến trình mẹ đã kích hoạt hành vi độc hại này là gì?
* `python3 vol.py -f ~/Desktop/Start\ here/Artifacts/Windows\ 7\ x64-Snapshot4.vmem windows.pslist`
* Đầu tiên tôi dùng command trên để check những tiến trính đang chạy hoặc từng chạy trên hệ thống theo tôi được
* Sau khi xem qua 1 lượt các tiến trình dưới đây
* <img width="1387" height="793" alt="{0834625D-F77E-4086-B0DF-37FFDC4E5B80}" src="https://github.com/user-attachments/assets/e399a168-1376-4257-9da4-302c6758a655" />
* Thì tôi thấy cả 2 tiến trính lsass và lssass theo tôi biết thì chỉ có lsass là (Local security authority service) chứ không có lssass nên tôi nghi ngờ nó là tiến trình độc
## Câu hỏi 2: Khi tiến trình độc hại được xác định, vị trí chính xác của nó trên thiết bị có thể tiết lộ thêm về bản chất và nguồn gốc của nó. Tiến trình này được lưu trữ ở đâu trên máy trạm?
* * `python3 vol.py -f ~/Desktop/Start\ here/Artifacts/Windows\ 7\ x64-Snapshot4.vmem -p 2748 windows.dlllist`
* Dùng câu lệnh trên để phân tích và tìm được đáp án là
* * <img width="1371" height="171" alt="{7B275BEE-B020-405C-9D55-A9EE2F465856}" src="https://github.com/user-attachments/assets/0af13d5c-0d30-4244-a2c1-ad3c27642608" />
## Câu hỏi 3: Các giao tiếp bên ngoài liên tục cho thấy phần mềm độc hại đang cố gắng tiếp cận máy chủ C2C. Bạn có thể xác định địa chỉ IP của máy chủ C2C mà tiến trình này tương tác không?
* `python3 vol.py -f ~/Desktop/Start\ here/Artifacts/Windows\ 7\ x64-Snapshot4.vmem windows.netscan.NetScan `
* Dùng câu lệnh netscan để xem được là những phần mêm nào có kết nối ra bên ngoài
* <img width="1100" height="133" alt="{BC0BB3A1-0129-41C0-AA55-21066CF7D8BE}" src="https://github.com/user-attachments/assets/155406b5-293e-4ff5-add6-e94c8ac583ab" />
## Câu hỏi 4: Theo liên kết phần mềm độc hại với C2C, phần mềm độc hại có thể đang tìm nạp thêm các công cụ hoặc mô-đun. Nó đang cố gắng đưa bao nhiêu tệp riêng biệt vào máy trạm bị xâm nhập?
* Sau câu trên tôi biết tiến trình độc hại là lssass với pid là 2748 nên tôi đã dump tiến trình đấy ra với command sau.
* `python3 vol.py -f ~/Desktop/Start\ here/Artifacts/Windows\ 7\ x64-Snapshot4.vmem windows.memmap.Memmap --pid 2748 --dump`
* sau khi có file dump tôi đọc nó bằng string
* `strings pid.2748.dmp | grep -iE "GET |POST " -A 5`
* đọc nó coi là có kết nối với bên ngoài và tải cái gì về không thì tôi được kết quả như bên dưới
* <img width="581" height="232" alt="{991A4278-7773-4DB3-9138-6B3C04F279B5}" src="https://github.com/user-attachments/assets/0af0cbe4-3e42-4e5a-bbff-6f2e71286303" />
* Nó có tải về 2 file dll lạ (file dll là dynamic link library)  
## Câu hỏi 5: Việc xác định các điểm lưu trữ của các thành phần bổ sung này rất quan trọng cho việc ngăn chặn và dọn dẹp. Đường dẫn đầy đủ của tệp được phần mềm độc hại tải xuống và sử dụng trong hoạt động gây hại của nó là gì?
* <img width="1111" height="217" alt="image" src="https://github.com/user-attachments/assets/00d88d8d-1379-4415-b962-926d0e84751d" />
* Dùng command dlllist và grep dll trên ra tôi được kết quả như trên 
## Câu hỏi 6: Sau khi truy xuất, phần mềm độc hại sẽ kích hoạt các thành phần bổ sung của nó. Tiến trình con nào được phần mềm độc hại khởi tạo để thực thi các tệp này?
* `rundll32.exe` 
## Câu hỏi 7: Việc hiểu rõ toàn bộ các cơ chế tồn tại dai dẳng của Amadey có thể giúp giảm thiểu hiệu quả. Ngoài những vị trí đã được nêu bật, phần mềm độc hại còn có thể hiện diện liên tục ở đâu?
* `C:\Windows\System32\Tasks\lssass.exe`
* Dùng grep file lssass.exe để xem đường dẫn của nó
