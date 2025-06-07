## Câu hỏi 1: Xác định địa chỉ IP của người gửi với các giá trị SPF và DKIM cụ thể giúp theo dõi nguồn gốc của email lừa đảo. Địa chỉ IP của người gửi có giá trị SPF là softfail và giá trị DKIM là fail là gì ?
* ![{C6A95069-8125-49CF-BCD6-D2F6DAE94311}](https://github.com/user-attachments/assets/485329f8-0a28-4e7a-96d5-9d39c8354b56)
* Vào trang `https://app.phishtool.com/` và upfile .elm lên ta sẽ thấy được địa chỉ IP gửi với giá trị SPF.
## Câu hỏi 2: Hiểu đường dẫn trả về của email là điều cần thiết để truy tìm nguồn gốc của email. Đường dẫn trả về được chỉ định trong email này là gì?
* ![{69503550-86BB-40CD-860F-9C383D04AEF0}](https://github.com/user-attachments/assets/9999c621-99d1-4df9-b142-d4d3e693f0a3)
## Câu hỏi 3: Xác định nguồn gốc của phần mềm độc hại là rất quan trọng để giảm thiểu và ứng phó mối đe dọa hiệu quả. Địa chỉ IP của máy chủ lưu trữ tệp độc hại liên quan đến việc phân phối phần mềm độc hại là gì?
* ![{DF919756-864B-4A96-A426-EE4B6B5D9525}](https://github.com/user-attachments/assets/ac79160e-865d-4f35-a772-56c72b0e9d29)
## Câu hỏi 4: Việc xác định phần mềm độc hại khai thác tài nguyên hệ thống để khai thác tiền điện tử là rất quan trọng để ưu tiên các nỗ lực giảm thiểu mối đe dọa. URL độc hại có thể phân phối một số loại phần mềm độc hại. Họ phần mềm độc hại nào chịu trách nhiệm khai thác tiền điện tử?
* `http://107.175.247.199/loader/install.exe` tôi thử search từ khóa này trên `https://urlhaus.abuse.ch/` không hiểu sao lại ko tìm ra nhưng thử tìm với mỗi ip `107.175.247.199` thì ra kết quả như bên dưới
* ![{EEC3668E-E517-418B-AE1B-C34387F5CDB6}](https://github.com/user-attachments/assets/529067e1-5842-45b0-9aee-760ffcc26b1c)
* Thì biết được malware này có họ là `CoinMiner`
## Câu hỏi 5: Xác định các URL cụ thể mà phần mềm độc hại yêu cầu là chìa khóa để phá vỡ các kênh truyền thông của nó và giảm tác động của nó. Dựa trên phân tích trước đây về mẫu phần mềm độc hại tiền điện tử, phần mềm độc hại này yêu cầu URL gì?
* `453fb1c4b3b48361fa8a67dcedf1eaec39449cb5a146a7770c63d1dc0d7562f0`
* ![{05E41777-0BFC-46D1-B289-D05794451B46}](https://github.com/user-attachments/assets/d400f751-baad-49b9-beae-b7138e9bd5ee)
* ![{2A7B91C8-4C9A-494D-85D9-766B44FC1EF6}](https://github.com/user-attachments/assets/c7db7906-df8c-4993-b49c-4318facbaca9)
* `http://ripley.studio/loader/uploads/Qanjttrbv.jpeg`
## Câu hỏi 6: Hiểu các mục đăng ký được phần mềm độc hại thêm vào khóa tự động chạy là rất quan trọng để xác định cơ chế tồn tại của nó. Dựa trên phân tích mẫu phần mềm độc hại BitRAT , tên tệp thực thi trong giá trị đầu tiên được thêm vào khóa tự động chạy của sổ đăng ký là gì?
* ![{4EFC1E78-1BC0-4D54-847B-39A94540BD88}](https://github.com/user-attachments/assets/53178a9a-19db-4c1d-91ea-175f3c927cbe)
* Từ report ta kiếm được câu 4 copy mã SHA256 
* Vào trang `MalwareBazaar Database` ta dán như sau
* ![image](https://github.com/user-attachments/assets/1903698c-063f-484f-bd70-7c0920ddb45d)
* Vào report bên dưới và vào với anyrun
* ![{CD45136A-865C-47B6-A98A-EDE343E4CFD7}](https://github.com/user-attachments/assets/bdb092ec-215b-4123-aa1b-33f70fa4da0d)
* ![{A507FA8A-C95A-41AC-B486-29838B51CDC3}](https://github.com/user-attachments/assets/25e28990-a9ed-4d26-9307-001247944f2e)
* Theo hình ảnh ta thấy được tiến trình gốc là `86c57967785fe8dbcdf209fb564f9a85.exe` có đường dẫn là `C:\Users\admin\AppData\Local\Temp\86c57967785fe8dbcdf209fb564f9a85.exe` nó đang Modified files với file `Jzwvix.exe`
## Câu hỏi 7: Việc xác định băm SHA-256 của các tệp được tải xuống từ URL độc hại là điều cần thiết để theo dõi và phân tích hoạt động của phần mềm độc hại. Dựa trên phân tích BitRAT , băm SHA-256 của tệp đã tải xuống trước đó và được thêm vào khóa tự động chạy là gì?
* ![{B86468CD-1655-4FBE-A804-50F91DAFE7EF}](https://github.com/user-attachments/assets/cbaaa8db-b9a9-4b74-8cd4-605f7222eb37)
## Câu hỏi 8: Phân tích các yêu cầu HTTP do phần mềm độc hại tạo ra giúp xác định các mẫu giao tiếp của nó. URL trong yêu cầu HTTP được trình tải sử dụng để truy xuất phần mềm độc hại BitRAT là gì?
* ![{4D73FE6D-DB9D-4BCF-A5C7-90F2F6A8FD41}](https://github.com/user-attachments/assets/394e9a82-6c6f-483c-a47a-caf83cc2cabd)
* Copy mã Hash này vào Virus Total ta được như hình ảnh bên dưới
* ![image](https://github.com/user-attachments/assets/819aa716-0e4a-4fd7-98b4-3ca220ae120d)
* Đáp án là `http://107.175.247.199/loader/server.exe`
## Câu hỏi 9: Việc đưa ra độ trễ trong quá trình thực thi phần mềm độc hại có thể giúp tránh được các cơ chế phát hiện. Độ trễ (tính bằng giây) do lệnh PowerShell gây ra theo phân tích của BitRAT là bao nhiêu?
* ![{E6DAB580-EEDD-4197-A04F-C0D1277CCD00}](https://github.com/user-attachments/assets/b0912712-3139-4c81-bb53-e423427ea664)
* Ta thấy có một mã base64 đã bị mã hóa
* Đưa vào `CyberChef` ta được như hình ảnh bên dưới
* ![{7D8155E2-3E06-4DB9-8A36-AD44D928B956}](https://github.com/user-attachments/assets/0e8c5772-d42a-4e77-ac0f-b4557e4ecb56)
* `start sleep seconds 50`
## Câu hỏi 10: Theo dõi các miền lệnh và kiểm soát (C2) được phần mềm độc hại sử dụng là điều cần thiết để phát hiện và chặn các hoạt động độc hại. Miền C2 được phần mềm độc hại BitRAT sử dụng là gì?
* ![{0539D0AC-9DD3-4248-A001-40135E022853}](https://github.com/user-attachments/assets/f5e54c54-e53d-45d7-be7b-f71425bf127a)
## Câu hỏi 11: Hiểu cách phần mềm độc hại đánh cắp dữ liệu là điều cần thiết để phát hiện và ngăn chặn vi phạm dữ liệu. Theo phân tích của AsyncRAT , Telegram Bot ID được phần mềm độc hại này sử dụng là gì?
* ![{1BC147F2-E901-48A5-9A2E-7B4EC7CAF60D}](https://github.com/user-attachments/assets/e7e5d50c-5db9-46a1-88c0-89738decfc6b)
* Về lại trang `urlhaus` và chọn `AsyncRAT` những tôi vẫn không thể tìm thấy cái gì. Nên tôi đã thử vào đọc report của 1 trang khác là `https://tria.ge/` và search theo mã `SHA256:5ca468704e7ccb8e1b37c0f7595c54df4e2f4035345b6e442e8bd4e11c58f791`
* ![{39AE29D5-5316-412C-9BE7-E24F8ED68493}](https://github.com/user-attachments/assets/8e3eaec9-daf4-4580-8da7-af06cb975f41)
* Nó đang cố kết nối đến con Bot Telegram có ID là 5610920260: để nhận lệnh từ atacker


