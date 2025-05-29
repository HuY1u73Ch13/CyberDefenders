## Câu hỏi 1: Máy này đang sử dụng bản phân phối Linux nào? 
* ![{92A41DA8-1D3A-4644-BEB7-74DF3CB40866}](https://github.com/user-attachments/assets/e4d9dd43-7877-43c0-938e-a3dfb6fc4c95)
* Chúng ta vào thư mục /root/var/log/install để tìm thấy được máy linux này đang sử dụng bản phân phối nào.
## Câu hỏi 2: Mã băm MD5 của tệp access.log Apache là gì ?  
* ![{7095050D-76E0-4B68-87A9-D7B7E97C9DEB}](https://github.com/user-attachments/assets/e7e2e6b6-9a35-4959-8812-fcf41f6df7c7)
* Export file hashlist ta có  `d41d8cd98f00b204e9800998ecf8427e` 
## Câu hỏi 3: Người ta nghi ngờ rằng một công cụ đổ thông tin xác thực đã được tải xuống. Tên của tệp đã tải xuống là gì?
* Vào /root/download ta thấy được một tệp zip lạ đã được tải xuống như hình.
* ![{240CCC61-1340-4781-8E1F-08B3B6A0AF71}](https://github.com/user-attachments/assets/0248cfa0-bb16-4181-a7a7-0bef60a352f7)
## Câu hỏi 4: Một tập tin siêu bí mật đã được tạo. Đường dẫn tuyệt đối đến tập tin này là gì?
* ![{F41EB594-2FD4-4753-B4EB-35DA4F756318}](https://github.com/user-attachments/assets/716910d8-b8f7-40af-83a1-daf575be49b1)
* Vào root/root ta sẽ thấy tệp bashhistory nên ta sẽ thấy đường dẫn tuyệt đối của file bí mật đã được tạo
## Câu hỏi 5: Chương trình nào đã sử dụng tệp didyouthinkwedmakeiteasy.jpg  trong quá trình thực thi?
* ![{FFD089A3-DCDC-4F4B-8C2C-F18771639C75}](https://github.com/user-attachments/assets/6c268d5d-6448-45a4-af5e-f06288471607)
* Lướt thêm ta thấy được tệp đã sử dụng tệp `didyouthinkwedmakeiteasy.jpg` như trong ảnh
## Câu hỏi 6: Mục tiêu thứ ba trong danh sách kiểm tra mà Karen tạo ra là gì?
* ![{FC7AE9A7-084F-41AA-BCFB-E156C1ADC725}](https://github.com/user-attachments/assets/a1a6efcd-91e0-4928-8af1-92152da04263)
* Ta tìm được nó trong phần desktop vì người dùng đã lưu trữ nó trong desktop và checklist của họ
## Câu hỏi 7: Apache đã được chạy bao nhiêu lần?
* ![{BD8D6E2A-71EF-42E7-B613-C7371F2932DD}](https://github.com/user-attachments/assets/b8e52064-0570-4b68-8fef-7e9e69b97339)
* Ta thấy Apache này đã chạy được 0 lần
## Câu hỏi 8: Cỗ máy này được dùng để tấn công một máy khác. Tập tin nào chứa bằng chứng cho việc này?
* ![{A8C96C62-C902-44A1-9CD6-F0452D60CF8D}](https://github.com/user-attachments/assets/5c9286c9-63e9-4bef-8fed-703c3e51ab00)
## Câu hỏi 9: Người ta tin rằng Karen đã chế giễu một chuyên gia máy tính khác thông qua một tập lệnh bash trong thư mục Documents. Chuyên gia mà Karen đang chế giễu là ai? 
* `Heck yeah! I can write bash too Young`
## Câu hỏi 10: Một người dùng đã thực hiện lệnh su  để giành quyền truy cập root nhiều lần vào lúc 11:26. Người dùng đó là ai?
![image](https://github.com/user-attachments/assets/7f67b9ea-8ded-478f-8d03-c5b9c363cfa6)
* Theo quan sát ta thấy người dùng nào đó đã giành quyền root vào lúc 11:26 ngày 20/5 đã thực hiện thành công lệnh su và đổi root sang postgres.
## Câu hỏi 11: Dựa trên lịch sử bash, thư mục làm việc hiện tại là gì?
* ![{FBB92090-E62A-43A0-98F3-C23B38CBE31E}](https://github.com/user-attachments/assets/6595c107-f8d7-4b3b-8e5e-e3b39e95a368)
* Theo bash thì hiện tại ta đang ở thư mục `/root/Documents/myfirsthack/`
