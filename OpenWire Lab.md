## Câu hỏi 1: Bằng cách xác định IP C2, chúng tôi có thể chặn lưu lượng đến và đi từ IP này, giúp ngăn chặn vi phạm và ngăn chặn việc rò rỉ dữ liệu hoặc thực thi lệnh tiếp theo. Bạn có thể cung cấp IP của máy chủ C2 đã giao tiếp với máy chủ của chúng tôi không?
* ![{ABF2BDE9-1919-4AA4-B978-879254265B2A}](https://github.com/user-attachments/assets/56ae6653-66ee-44a9-af42-70729c80f7ab)
* Vào phần Statistic -> Conversation để xem được lưu lượng packet mà 2 địa chỉ ip trao đổi với nhau.
## Câu hỏi 2: Điểm vào ban đầu rất quan trọng để theo dõi vectơ tấn công trở lại. Số cổng của dịch vụ mà kẻ tấn công khai thác là gì?
* ![{8DE1182C-F912-4585-BAB2-EF463BEC6A86}](https://github.com/user-attachments/assets/6ef67bf7-b110-45f3-b375-abbc73ba5f38)
## Câu hỏi 3: Tiếp theo câu hỏi trước, tên của dịch vụ được phát hiện có lỗ hổng là gì?
* ![{CB464E5D-8D64-4457-99FB-48B1DFEA850F}](https://github.com/user-attachments/assets/f3749e23-153b-48f8-a866-08944d0a8b82)
## Câu hỏi 4: Cơ sở hạ tầng của kẻ tấn công thường bao gồm nhiều thành phần. Địa chỉ IP của máy chủ C2 thứ hai là gì?
* ![{5218CDDE-6BF7-41BF-A66D-D32E565FC14A}](https://github.com/user-attachments/assets/934b0c58-fe36-40b6-b13e-7cecfa68ef53)
## Câu hỏi 5: Kẻ tấn công thường để lại dấu vết trên đĩa. Tên của tệp thực thi reverse shell được thả trên máy chủ là gì?
* ![{DEB06906-C6C9-4756-9BD0-B98EFC0BF347}](https://github.com/user-attachments/assets/6d53d960-c052-4ff7-8c9e-ea630b6432b0)
* Ta thấy actacker đang truy cập và tải về tệp docker và đang cấp quyền thực thi cho nó
## Câu hỏi 6: Lớp Java nào được tệp XML gọi để chạy khai thác?
* ![{597F2F18-E02A-410A-83B0-7DA7C42E1D77}](https://github.com/user-attachments/assets/e8d3045b-8415-4bb3-ac3e-0af52fa1c43f)
## Câu hỏi 7: Để hiểu rõ hơn về lỗ hổng bảo mật cụ thể bị khai thác, bạn có thể xác định mã định danh CVE liên quan đến lỗ hổng này không?
* Tra trên gg về lỗ hổng OpenWire ta có được `CVE-2023-46604`
## Câu hỏi 8: Nhà cung cấp đã giải quyết lỗ hổng bằng cách thêm bước xác thực để đảm bảo chỉ Throwablecó thể khởi tạo các lớp hợp lệ, ngăn chặn việc khai thác. Bước xác thực này được thêm vào lớp và phương thức Java nào?
* ![image](https://github.com/user-attachments/assets/9d3f3cb4-0d53-44cb-b09a-1e5be3816852)
* Dựa vào đoạn code tôi kiếm được trên mạng về bản vá của `CVE-2023-46604` ta thấy được nó đã khởi tạo method `private Throwable createThrowable` ở trong class là BaseDataStreamMarshaller.java
* Nên ta suy được ra là `Class.Method` là `BaseDataStreamMarshaller.createThrowable`

