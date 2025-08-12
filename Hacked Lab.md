## Câu hỏi 1: Múi giờ hệ thống là gì?
* <img width="1441" height="517" alt="{79A8AFCB-8CEA-410F-9EC7-BB52DAFFD2F1}" src="https://github.com/user-attachments/assets/6c20b069-f6aa-4c9f-a745-930e38a6b2db" />
* Dựa theo hint của câu này ta được câu trả lời là máy này đang set timezone là giờ châu âu và là nước bỉ.
## Câu hỏi 2: Người dùng cuối cùng đăng nhập vào hệ thống là ai?
* <img width="922" height="60" alt="{5BDAE116-EFE7-4C25-BF83-8EDAF539F006}" src="https://github.com/user-attachments/assets/306cfa80-847b-4e75-8cd8-579d86d46f4d" />
* Tôi tìm theo từ khóa `accepted` trong tệp auth.log trong đường dẫn /root/var/log/auth.log thì tìm được là người dùng đăng nhập mail và được chấp nhận.
## Câu hỏi 3: Người dùng 'mail' kết nối từ cổng nguồn nào?
* Cổng port là 57708
## Câu hỏi 4: Phiên cuối cùng của người dùng 'mail' kéo dài bao lâu? (Chỉ tính bằng phút)
* Phiên cuối cùng người dùng đăng nhập vào khoảng 1 phút
* <img width="955" height="160" alt="{56F311AE-79B7-4D9C-A0C3-43C0DC8B3D91}" src="https://github.com/user-attachments/assets/e3721920-c5e2-4b11-b666-2334e4567871" />
## Câu hỏi 5: Người dùng cuối cùng đã sử dụng dịch vụ máy chủ nào để đăng nhập vào hệ thống?
* Theo hình ảnh trên thì là sshd
## Câu hỏi 6: Loại tấn công xác thực nào đã được thực hiện trên máy mục tiêu?
* Đọc log ta thấy được 1 loạt log có ghi nhận là đăng nhập fail nên chúng ta đoán và người tấn công đang cố tình tấn công bruteforce vào máy nạn nhân này.
## Câu hỏi 7: Có bao nhiêu địa chỉ IP được liệt kê trong tệp '/var/log/lastlog'?
* Quan sát tệp đấy và tôi đếm được là có 2 địa chỉ ip. 
## Câu hỏi 8: Có bao nhiêu người dùng có shell đăng nhập?
* <img width="1263" height="983" alt="{1A99406E-3B4B-4DBB-B934-748A8CD57953}" src="https://github.com/user-attachments/assets/b59f505e-11c5-4ef4-b7df-fbc1e9ed2a87" />
* đáp án là 5
## Câu hỏi 9: Mật khẩu của người dùng email là gì?
* <img width="784" height="574" alt="{BAD195A5-03CB-41D8-A26F-B5412A0BF2EF}" src="https://github.com/user-attachments/assets/0baf74cf-571e-4cf7-a522-8bd4a51de9c0" />
* Tôi đã dùng john để hash mật khẩu với wordlist là rockyou
## Câu hỏi 10: Kẻ tấn công đã tạo ra tài khoản người dùng nào?
* <img width="1629" height="188" alt="{D21D80EE-0E7A-4A69-8C95-E42E3A40B15F}" src="https://github.com/user-attachments/assets/6f1bc2bf-fe85-439a-97ca-bab1092ac3c5" />
## Câu hỏi 11: Có bao nhiêu nhóm người dùng trên máy?
* <img width="978" height="513" alt="{7A6FC791-D143-4CB8-B9CA-5BB5BB2AA64A}" src="https://github.com/user-attachments/assets/d44240f3-a2bf-4c2d-99c4-fa0a9ac21923" />
* Vào file group ở đường dẫn var/etc/group. NOTE là group - là file gốc của file group trước khi dùng các công cụ như addgroup hoặc vigr để chỉnh sửa /etc/group, hệ thống sẽ tự tạo/ghi đè file group- để lưu trạng thái cũ.
* Theo như tôi đếm ở đây thì 1 dòng là 1 group thì có tất cả 58 group
## Câu hỏi 12: Có bao nhiêu người dùng có quyền truy cập sudo?
* <img width="316" height="115" alt="{61EE5F69-040E-467D-984B-68F1810774C4}" src="https://github.com/user-attachments/assets/0de00df7-e2a5-4600-80f5-1135f0a761ec" />
* Có 2 người dùng 
## Câu hỏi 13: Thư mục gốc của người dùng PHP là gì?
* <img width="418" height="65" alt="{E5FE6BF9-51A8-4D15-8D7B-155845D963DC}" src="https://github.com/user-attachments/assets/ccc51ad7-7383-413c-8a89-4f0216916579" />
* Tìm thư mục gốc của người dùng php ở trong thư mục 
## Câu hỏi 14: Kẻ tấn công đã sử dụng lệnh nào để giành được quyền root? (Câu trả lời chứa hai khoảng trắng).
* <img width="921" height="537" alt="{92D5E998-04D9-439D-9BF1-DF0F146998E4}" src="https://github.com/user-attachments/assets/bac2b33a-8fda-443c-ad7d-2b3dd4f011fc" />
* Tìm câu trả lời ở đường dẫn var/mail/ 
## Câu hỏi 15: Người dùng 'root' đã xóa tập tin nào?
* <img width="931" height="669" alt="{E4DD6941-6B23-4801-8E02-B7D9F35742EA}" src="https://github.com/user-attachments/assets/0333dfd9-75dd-4961-83bd-1b882bae88d6" />
* Vào đường dẫn root/var/log/.bash_history ta thấy được lệnh bash rm 37292.c
## Câu hỏi 16: Khôi phục tệp đã xóa, mở tệp đó và trích xuất tên tác giả của tệp khai thác.
* Tôi đã dùng R-Studio Recovery để recover lại file 37292.c 
* <img width="956" height="191" alt="{5B888340-B1CE-4C68-A006-BEE4BC053211}" src="https://github.com/user-attachments/assets/570237c5-fd16-4eac-a195-13976f6f7b93" />
* Sau khi recover lại file tôi có được đáp án như hình ảnh
## Câu hỏi 17: Hệ thống quản lý nội dung (CMS) được cài đặt trên máy là gì?
* <img width="785" height="536" alt="{64A9EEBF-FF43-47D9-97AD-816797AC5D07}" src="https://github.com/user-attachments/assets/b32d823a-286f-46e1-9378-1f557fcbc012" />
## Câu hỏi 18: Phiên bản CMS được cài đặt trên máy là gì?
* <img width="1645" height="1015" alt="{ABC3C628-3568-4E48-8E73-392A793E4DAA}" src="https://github.com/user-attachments/assets/951dfeb9-9175-460e-97ab-f155f99de042" />
## Câu hỏi 19: Cổng nào đang lắng nghe để nhận lệnh tấn công ngược của kẻ tấn công?
* <img width="2094" height="1032" alt="{188FED4C-96DC-4B7A-880E-38ABE7697F0C}" src="https://github.com/user-attachments/assets/dda78796-1f54-4684-93a2-d49fc6979e86" />

