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
*
## Câu hỏi 15: Mã băm md5 của tệp đã tải xuống là gì?
*
## Câu hỏi 16: Phần mềm nào chạy máy chủ web lưu trữ phần mềm độc hại?
*
## Câu hỏi 17: Địa chỉ IP công khai của máy tính nạn nhân là gì?
*
## Câu hỏi 18: Máy chủ email mà thông tin bị đánh cắp được gửi đến nằm ở quốc gia nào?
*
## Câu hỏi 19: Phân tích thông tin trích xuất đầu tiên. Phần mềm nào chạy máy chủ email mà dữ liệu bị đánh cắp được gửi đến?
*
## Câu hỏi 20: Thông tin bị đánh cắp được gửi đến tài khoản email nào?
*
## Câu hỏi 21: Mật khẩu mà phần mềm độc hại sử dụng để gửi email là gì?
*
## Câu hỏi 22: Biến thể phần mềm độc hại nào đã đánh cắp dữ liệu?
*
## Câu hỏi 23: Thông tin đăng nhập vào bankofamerica là gì? (tên người dùng:mật khẩu)
*
## Câu hỏi 24: Cứ mỗi bao nhiêu phút thì dữ liệu thu thập được lại bị rò rỉ?
* 
