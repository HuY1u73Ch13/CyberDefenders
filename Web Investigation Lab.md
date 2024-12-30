#### Câu hỏi 1 : Bằng cách biết được ip của kẻ tấn công, chúng ta có thể phân tích được tất cả nhật kí và hành động liên quan đến IP đó và mức độ tấn công, thời gian tấn công và kĩ thuật đã sử dụng. Bạn có thể cung cấp IP kẻ tấn công ?
![{348A1287-C82F-46F8-B929-569109774198}](https://github.com/user-attachments/assets/b8e53611-9b04-4e87-a8d4-be1786742834)
* Dựa vào gói 357 ta có thể thấy IP 111.224.250.131 đang tiêm SQLi và gửi đến địa chỉ IP 73.124.22.98 nên ta có thể xác định đây là địa chỉ của kẻ tấn công.
#### Câu hỏi 2 : Nếu nguồn gốc của địa chỉ IP đến từ 1 khu vực và không có hoạt động kinh doanh hoặc là truy cập đến mạng của chúng ta, đây có thể là dấu hiệu của một cuộc tấn công có chủ đích. Bạn có thể xác định nguồn gốc thành phố của địa chỉ ip đấy không ?
![{CAB1A105-E3EE-45CA-A208-FE4B9EADFC2F}](https://github.com/user-attachments/assets/3e8aa013-6c20-448c-9af7-deac31de0747)
* Sử dụng ipinfo chúng ta có thể biết được ip đấy đến từ đâu.
#### Câu hỏi 3 : Bằng cách  phân tích các tệp tin cho phép đội phòng thủ hiểu được chính xác lỗ hổng nào đã bị tấn công. Kiến thức này rất quan trọng để tìm ra cách vá lỗ hổng và ngăn chặn khai thác trong tương lai. Bạn có thể cung cấp tệp tin bị tấn công ?
![{06CB67F6-F21A-4DC9-82FE-97F307A3AE8D}](https://github.com/user-attachments/assets/907826c7-7bd4-48b7-a5ce-5f27f05c384b)
* Ta có thể thấy tệp tin bị tấn công là search.php.
#### Câu hỏi 4 : Theo dòng thời gian của cuộc tấn công, bắt nguồn từ nỗ lực khai thác ban đầu. Yêu cầu URI hoàn chỉnh của SQLi được gửi bởi kẻ tấn công là gì ?
![image](https://github.com/user-attachments/assets/f2cb230d-b748-4293-b5a6-a721dc582e27)
* Theo hình ảnh ta thấy kẻ tấn công đang cố tiêm vào url mệnh đề hợp lệ 1=1.
#### Câu hỏi 5 : Bạn có thể cung cấp một URI hoàn chỉnh để đọc được dữ liệu có sẵn trên máy chủ không ?
* Để đọc được dữ liệu trên máy chủ ta thường dùng mệnh đề UNION ALL SELECT NULL để tiêm vào url, nên đầu tiên chúng ta nên lọc ra nhưng gói tin chứa UNION ALL SELECT NULL trên URL bằng cách sử dụng `http contains "UNION%20ALL%20SELECT%20NULL"`. <br>
![{F1237739-456A-4500-B828-475C5A189E62}](https://github.com/user-attachments/assets/764f7474-192d-4327-92ca-c805412f358e)
* Xem lần lượt các gói tin chúng ta thấy được gói tin này đã trả về kết quả của bảng dữ liệu trên sever.
#### Câu hỏi 6 : Đánh giá được tác động và dữ liệu liên quan đến tổ chức, bao gồm các mỗi nguy hiểm tiềm tàng đến với danh tiếng của tổ chức. Bạn có đưa ra bảng dữ liệu chứa dữ liệu của người dùng trang web.
![{468517A5-5B95-490D-9850-4AA0D40896D0}](https://github.com/user-attachments/assets/992f7b0a-60b2-4154-93b4-f7196c8d9434)
* Có thể thấy ở gói tin 1548 nó đã lấy được về tên bảng customers chứ thông tin của khách hàng sử dụng trang web.
#### Câu hỏi 7 : Các thư mục của trang web bị ẩn khỏi công chúng có thể trở thành một điểm truy cập trái phép hoặc chứa các chức năng nhạy cảm không được thiết kế để truy cập công khai. Bạn có thể cung cấp tên của thư mục mà kẻ tấn công đã phát hiện không?
![{7776D622-2561-4EBD-8EEF-4F1D852EFE2E}](https://github.com/user-attachments/assets/2a68631a-518f-4b43-93ad-622ec0c72954)
* Ta có thể thấy kẻ tấn công đã truy cập vào được đường dẫn /admin/
#### Câu hỏi 8 : Việc biết tên tài khoản người dùng nào đã bị tấn công cho phép chúng tôi biết mức độ xâm phạm tài khoản. Thông tin xác thực mà kẻ tấn công dùng để đăng nhập là gì ?
![{5E59F80F-AF23-483F-8D4B-5CFEBD23FD9A}](https://github.com/user-attachments/assets/72e86b69-7c50-4dd0-a449-49856d08ecf8)
Ta có thể thấy đây là tên tài khoản và mật khẩu kẻ tấn công đã sử dụng.
#### Câu hỏi 9 : Chúng tôi cần xác định xem kẻ tấn công có thể dành được quyền kiểm soát trang web trên sever tôi không. Tên tập tin được tải lên bởi người tấn công là gì ?
![image](https://github.com/user-attachments/assets/b03c1cb1-c1e5-498b-8f1f-c77b43ba32af)
* Xem thẻ này ta có thể biết kẻ tấn công đang tải lên tệp NVri2vhp.php 
