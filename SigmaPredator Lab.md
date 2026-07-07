# Báo cáo Lab: SigmaPredator Lab – CyberDefender 
## Đây là 1 bài thực hành thú vị thuộc mảng Detection Engineering, tập trung vào chiến thuật Defense Evasion. Mục tiêu cốt lõi của chúng ta là phân tích và xây dụng các luật sigma để phát hiện hành vi xóa Windows Event Log (kỹ thuật T1070.001) - một thủ đoạn thường được các nhóm APT như APT28, APT41 hay Aquatic Panda sử dụng để che dấu vết.

## Câu hỏi 1: Phát hiện tạo tiến trình: Tiện ích dòng lệnh tích hợp nào của Windows hỗ trợ trực tiếp việc quản lý—và đặc biệt là xóa—nhật ký sự kiện?
* Kẻ thù có thể xóa nhật ký sự kiện Windows để che giấu hoạt động xâm nhập. Nhật kí sự kiện windows ghi lại các cảnh báo và thông tin của máy tính. Có 3 nguồn sự kiện do hệ thống định nghĩa: **SYSTEM**, **APPLICATION**, **SECURITY**
## Câu hỏi 2: Phát hiện tạo tiến trình:  Lớp WMI nào thường xuất hiện trong nhật ký khi kẻ tấn công sử dụng các lệnh WMIC để xóa nhật ký sự kiện Windows quan trọng thông qua dòng lệnh?
* Chúng ta biết dược là kẻ tấn công sẽ dùng WMI để xóa log, và phương thức được gọi ra chắc chắn sẽ chứa từ khóa 'cleareventlog'. Vậy ta sẽ dùng chuỗi này làm mồi nhử.
* Bước 2: <img width="1161" height="270" alt="image" src="https://github.com/user-attachments/assets/fc4ebb56-105f-40c4-bed3-888ee2011ea5" />
* Nhưng mà kết quả trả về là Found 0 hits.
* <img width="1041" height="372" alt="image" src="https://github.com/user-attachments/assets/e86f9231-f20d-4235-8460-0014962f2dbd" />
* Thử với search từ khóa "nteventlog" thì đã tìm được là đúng chính xác là WMIC đã dùng đúng chính nó để để xóa nhật lý window
* Công cụ chainsaw là công cụ gì. Thì chainsaw là công cụ mã nguồn mở dùng để phân tích và săn lùng các dấu vết độc hại bên trong các tệp nhật ký sự kiện Window Event Log - evtx
## Câu hỏi 3: Phát hiện PowerShell : Kênh ghi nhật ký PowerShell nào cần được bật để ghi lại quá trình thực thi kỹ thuật này, và ID sự kiện nào cần được theo dõi theo khuyến nghị trong trang kỹ thuật MITRE ATT&CK?
* <img width="1397" height="203" alt="image" src="https://github.com/user-attachments/assets/c2508956-7bf1-4826-ad9b-92e66af1cab6" />
* **PowerShell Script Block Logging , 4104**
## Câu hỏi 4: Phát hiện PowerShell:  Những lệnh PowerShell tích hợp nào thường được kẻ tấn công lợi dụng để xóa nhật ký sự kiện Windows?
* `Clear-EventLog,Remove-EventLog`
## Câu hỏi 5 : Phát hiện PowerShell:  Kẻ tấn công có thể gọi những phương thức API .NET gốc nào trong không gian tên System.Diagnostics.Eventing.Reader và System.Diagnostics từ PowerShell để xóa nhật ký sự kiện Windows?
* EventLogSession.ClearLog,EventLog.Clear
## Câu hỏi 6 : Phát hiện xóa tập tin:   Cần theo dõi những ID sự kiện Windows nào để phát hiện việc xóa nhật ký sự kiện Hệ thống hoặc Bảo mật, đây có thể là dấu hiệu cho thấy nhật ký đã bị xóa?
* 104.1102
