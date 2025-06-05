![{317F2463-DF72-47F8-A9CE-34094EA7466B}](https://github.com/user-attachments/assets/9e52009f-cd1b-4d6d-bff0-61c4212ac080)## Câu hỏi 1: Quá trình thu thập có bao nhiêu gói tin?
* ![{70F89119-63C2-442D-8CB8-279896B3CD46}](https://github.com/user-attachments/assets/cbf9cc99-5a4a-4b26-8973-aafe7e59c8de)
* Lướt xuống dưới cùng ta thấy gói pcap này có tổng cộng 4003 gói tin.
## Câu hỏi 2: Gói tin đầu tiên được bắt vào thời điểm nào?
* ![{819FA93D-CE10-46EC-BC75-8B80A92C094A}](https://github.com/user-attachments/assets/4bad6933-8828-4b97-886e-f542b5d7db86)
* `2019-04-10 20:37:07 utc`
## Câu hỏi 3: Thời gian chụp ảnh là bao lâu?
* ![image](https://github.com/user-attachments/assets/08405d67-cb02-4487-91f6-90c6a89679c9)
* ![image](https://github.com/user-attachments/assets/914f251b-4035-4317-9411-73e8d72ed4f1)
* Lấy thời gian gói đầu trừ gói cuối -> `01:03:41` là thời gian capture của gói pcap này
## Câu hỏi 4: Máy tính nào hoạt động tích cực nhất ở cấp độ liên kết?
* ![{317F2463-DF72-47F8-A9CE-34094EA7466B}](https://github.com/user-attachments/assets/caa2e3c5-572c-4835-a06f-b6a1c1eb445c)
* Vào statistic -> endpoints ta sẽ thấy máy `00:08:02:1c:47:ae` này đang giao tiếp nhiều nhất và gửi tới tận `4003` packet
## Câu hỏi 5: Nhà sản xuất NIC của hệ thống hoạt động tích cực nhất ở cấp độ liên kết?
* ![{7099BB96-CBEF-4458-AABD-DABF7C4DC60E}](https://github.com/user-attachments/assets/9599bfe2-47c6-4e95-818d-7629301a476e)
* Tích vào Name resolution ta sẽ thấy được NIC là HewlettPacka nhưng tôi nhập vào lại không đúng nên tôi đã thử search `NIC HewlettPack` trên mạng và được thông tin như này
* ![{C907D29C-BF3C-43F7-9164-26B497D710A7}](https://github.com/user-attachments/assets/ab4baffc-83b8-44f1-8312-0bcafefc41e0)
* ![{0299C247-1763-4DD7-ACBE-C919C3CCA2D4}](https://github.com/user-attachments/assets/b4c197f6-5b4b-4a14-a3c2-60a22a682ea1)
* `https://maclookup.app/macaddress/000802`
## Câu hỏi 6: Trụ sở chính của công ty sản xuất NIC của máy tính hoạt động tích cực nhất ở cấp độ liên kết nằm ở đâu?
* Tiếp tục vào link Wiki trên câu 5 ta sẽ thấy được thông tin công ty này và trụ sở của nó được đặt tại `Palo Alto`
* ![{C45CAF25-8171-479A-A670-A9AFD3CD807D}](https://github.com/user-attachments/assets/ec8384b6-4f51-4a97-9359-6e74725ecf7d)
## Câu hỏi 7: Tổ chức hoạt động với địa chỉ riêng và netmask /24. Có bao nhiêu máy tính trong tổ chức tham gia vào việc thu thập?
* ![image](https://github.com/user-attachments/assets/e2e3ff22-b0b5-48f0-85b0-9e5915275fd2)
* Tổ chức này hoạt động với địa chỉ ip riêng nên là nó chỉ thuộc trong dải 
* Từ `10.0.0.0` đến `10.255.255.255`
* Từ `172.16.0.0` đến `172.31.255.255`
* Từ `192.168.0.0` đến `192.168.255.255`
* Nên trong này hình ảnh này có 3 địa chỉ nội bộ là `10.4.10.2` `10.4.10.4` `10.4.10.132` còn `10.4.10.255` là địa chỉ broadcast
## Câu hỏi 8: Tên của máy tính hoạt động tích cực nhất ở cấp độ mạng là gì?
* ![{32B15C71-B630-4180-A1CE-EBCD1EA52F50}](https://github.com/user-attachments/assets/ece713ba-2363-423a-aa82-a2c55eaf9773)
* Ta thấy địa chỉ ip này `10.4.10.132` đang hoạt động tích cực nhất trong mục conservation nên ta thử lọc những góp tin có ip này và biết được tên máy tính của địa chỉ `10.4.10.1321+` như hình ảnh trên 
## Câu hỏi 9: Địa chỉ IP của máy chủ DNS của tổ chức là gì?
* ![{9D7C3FD7-9190-4B2B-A84D-E1E0A2688B3E}](https://github.com/user-attachments/assets/626c2586-c848-468c-8cde-e53487de0f4e)
* Lọc gói dns ra ta có thể thấy được địa chỉ ip đích của máy chủ DNS
## Câu hỏi 10: Nạn nhân đang hỏi về miền nào trong gói tin 204?
* ![{2A25700E-7C4A-48CB-938E-C4826F49E49F}](https://github.com/user-attachments/assets/db2d32fb-f2e3-4b38-8710-0652fdb95849)
* Chọn gói tin 204 và chọn Flow -> TCP Stream ta có thể thấy được đại chỉ mà victim đang yêu cầu.
## Câu hỏi 11: Địa chỉ IP của tên miền trong câu hỏi trước là gì?
* ![{B93CD59F-89FA-4E0F-854E-148034C92975}](https://github.com/user-attachments/assets/6a2e2a56-f6db-4d56-9e1b-66895404210a)
## Câu hỏi 12: Chỉ ra quốc gia mà IP ở phần trước thuộc về.
* ![{C86F6357-4728-4DF3-9D8C-3E62F2713671}](https://github.com/user-attachments/assets/a47ceb77-0410-4c6f-ad96-8dd0cdbfd267)
## Câu hỏi 13: Máy tính của nạn nhân chạy hệ điều hành nào?
* ![{85849ABB-F142-4F40-ADF9-DD4A7D983E2B}](https://github.com/user-attachments/assets/fc18062d-0522-4693-a440-00fcb72ccf84)
## Câu hỏi 14: Tên của tệp tin độc hại mà kế toán viên tải xuống là gì?
* ![{B66C9F27-AFAB-4536-98A8-08A1424C0588}](https://github.com/user-attachments/assets/d1b2068a-2133-4fb0-ba30-d9aa5dd5eabd)
* Phân tích gói pcap này bằng `NetworkMiner` ta có thể thấy được tệp mà kế toán viên đã tải xuống là `tkraw_Protected99.exe`
## Câu hỏi 15: Mã băm md5 của tệp đã tải xuống là gì?
* ![{F0460DFA-1B75-45E7-A62B-EEAF5A256AD6}](https://github.com/user-attachments/assets/3bb0a41f-e369-404f-9e63-f0de6179f9d4)
* Đưa tệp này lên trang VirusTotal ta có thể thấy được mã MD5 của tệp độc hại.
## Câu hỏi 16: Phần mềm nào chạy máy chủ web lưu trữ phần mềm độc hại?
* ![{BB16858E-B30A-4C75-8703-82B2F132C1D6}](https://github.com/user-attachments/assets/ccaaba8c-cd72-4dd8-8c9f-1d47567e0669)
* Vào tab prameters ở `NetworkMiner` ta có thể thấy nó bắt được prameters Server ở có vulue là `LiteSpeed` ở `HTTP Header`
## Câu hỏi 17: Địa chỉ IP công khai của máy tính nạn nhân là gì?
* ![{652572C5-F526-4A75-95E2-0041DB0390BA}](https://github.com/user-attachments/assets/fe5f82fb-fd27-4423-8ac3-8a955e9242c4)
* Mở tệp html ở `NetworkMiner` ta có thể thấy IP PUBLIC của máy tính nạn 
## Câu hỏi 18: Máy chủ email mà thông tin bị đánh cắp được gửi đến nằm ở quốc gia nào?
* ![{CA3F0873-DC92-4700-941C-8E39A1F4B0D9}](https://github.com/user-attachments/assets/faba97e3-46c3-48be-adc2-9f80d285388a)
## Câu hỏi 19: Phân tích thông tin trích xuất đầu tiên. Phần mềm nào chạy máy chủ email mà dữ liệu bị đánh cắp được gửi đến?
* ![{24BF9419-DA29-4B8F-8654-0A3452C90E76}](https://github.com/user-attachments/assets/e5335e42-7a66-4792-83a8-4c2bd1ed5cc3)
* Ban đầu tôi thử lọc các giao thức SMB và SMB2 để lọc những gói tin gửi tập tin với hi vọng tìm được tên máy chủ nhưng không tìm thấy gì.
* Đọc kỹ lại câu hỏi thì tôi thấy là `máy chủ email` nên tôi đã thử lọc phương thức `smtb` viết tắt là `Simple Mail Transfer Protocol` nên tôi tìm được `ESMTP Exim 4.91`
* Theo tôi tìm hiểu thì đây là 1 phần mềm máy chủ thư điện tử `Mail Transfer Agent` được dùng để gửi và nhận chuyển tiếp emaill trên internet hoặc mạng nội bộ.
* `ESMTP` là viết tắt của Extended Simple Mail Transfer Protocol nó là một phương thức mở rộng của `SMTB` tiêu chuẩn bổ sung nhiều tính năng hơn như là xác thực người gửi, truyền dữ liệu an toàn, hỗ trợ các lệnh mở rộng.
## Câu hỏi 20: Thông tin bị đánh cắp được gửi đến tài khoản email nào?
* ![{CD50D770-C210-4A4B-8DA0-0B6AD5D65472}](https://github.com/user-attachments/assets/021ea4e8-b09e-45d1-9779-476b263081d1)
* Ta có thể thấy được email đã được gửi đến trong phần Credenticals của NetWorkMiner
## Câu hỏi 21: Mật khẩu mà phần mềm độc hại sử dụng để gửi email là gì?
* ![{CD50D770-C210-4A4B-8DA0-0B6AD5D65472}](https://github.com/user-attachments/assets/021ea4e8-b09e-45d1-9779-476b263081d1)
* Ta có thể tìm thấy phân này trong phần Credenticals của NetWorkMiner 
## Câu hỏi 22: Biến thể phần mềm độc hại nào đã đánh cắp dữ liệu?
* ![{41E03D23-7A1B-44F0-8462-A88B10692E68}](https://github.com/user-attachments/assets/dfc47e53-c263-42fb-a7df-d1be6a00170d)
* Xem trong gói TCP ta thấy được gói TCP này có 1 phần mã hóa BASE64, đưa nó vào CyberChef.
* ![{0F23CB9E-8E93-4362-860F-36F41AA134D3}](https://github.com/user-attachments/assets/c71bb83a-701b-4848-93dc-f2d887623e58)
* Ta có thể thấy `Reborn v9` là một phần mềm của 1 biến thể độc hại `Reborn`.
## Câu hỏi 23: Thông tin đăng nhập vào bankofamerica là gì? (tên người dùng:mật khẩu)
* ![{BBBBDEA5-7B50-4FDA-8BB2-FFAC413347BF}](https://github.com/user-attachments/assets/9d826e17-52ce-41c6-97b5-2f5e6b0f3415)
* Cũng trong phần đấy ta thấy được mật khẩu và tài khoản đăng nhập vào `https://www.bankofamerica.com/`
## Câu hỏi 24: Cứ mỗi bao nhiêu phút thì dữ liệu thu thập được lại bị rò rỉ?
* Câu này thì ta sẽ lọc các gói kết nối đến những Server lạ hoặc bên ngoài nên tôi đã thử lọc `http.request.method == "POST"` nhưng không có gói nào nên tôi đổi sang phương thức get `http.request.method == "GET"`
* Trong gói có phương thức "GET" tôi thấy gói này đang gửi yêu cầu  `GET HTTP` đến trang `whatismyipaddress.com`
* Trang web này thường dùng để lấy địa chỉ ip và xem địa chỉ ip đấy đang ở đâu 
* ![{6CDDC702-B5AD-4341-A523-BBCF9A9269F4}](https://github.com/user-attachments/assets/a48e034d-2e5b-458b-857b-d9b87fa33ab0)
* ![{4023B81F-ACB2-4613-BCA5-C20F37E7C576}](https://github.com/user-attachments/assets/231116b8-5dbc-41b5-b37a-babbeafab7cb)
* Ta có thể thấy được cái gói này cách nhau 10 phút


