## Câu hỏi 1: Trong quá trình điều tra lưu lượng mạng, các mẫu hoạt động bất thường đã được quan sát thấy trong nhật ký Suricata, cho thấy khả năng truy cập trái phép. Một địa chỉ IP bên ngoài đã khởi tạo các nỗ lực truy cập và sau đó được phát hiện đang tải xuống một tệp thực thi đáng ngờ. Hoạt động này cho thấy rõ ràng nguồn gốc của cuộc tấn công. Vậy địa chỉ IP nào là nguồn gốc của truy cập trái phép ban đầu?
* <img width="1185" height="121" alt="{34838927-F502-49C5-B138-DEE8AA9D68FE}" src="https://github.com/user-attachments/assets/60e2b741-c8c2-4a04-b7b7-3a249f56508f" />
* index=* sourcetype=suricata eventtype=suricata_eve_ids_attack http.url=*.exe* | table _time src_ip dest_ip http.url file_name | sort _time
* Tôi thử dùng câu query này tôi thấy được file exe lạ đang được tải xuống tập tin tmp.
* Nên tôi nghi ngờ địa chỉ ip của nó là địa chỉ ip tấn công
## Câu hỏi 2: Việc điều tra tên miền của kẻ tấn công giúp xác định cơ sở hạ tầng được sử dụng cho cuộc tấn công, đánh giá kết nối của nó với các mối đe dọa khác và thực hiện các biện pháp giảm thiểu các cuộc tấn công trong tương lai. Tên miền của máy chủ của kẻ tấn công là gì?
* index=* sourcetype=suricata eventtype=suricata_eve_ids_attack http.url=*.exe* src_ip=195.88.191.59 | table _time src_ip dest_ip http.url file_name http.hostname dns.qry_name | sort _time
* <img width="1421" height="323" alt="{C30D4DFD-CB5B-4183-9D32-9B7970D1FA73}" src="https://github.com/user-attachments/assets/a98359f7-cc40-492a-aa80-6bc15a48d3d0" />
* Dùng câu lệnh này ta thấy được câu trả lời cho câu hỏi này .
## Câu hỏi 3: Việc biết địa chỉ IP của hệ thống bị nhắm mục tiêu giúp tập trung nỗ lực khắc phục và đánh giá mức độ xâm phạm. Địa chỉ IP của hệ thống bị nhắm mục tiêu trong vụ xâm phạm này là gì?
* Như ảnh bên trên ta có dest_ip
## Câu hỏi 4: Xác định tất cả các tệp duy nhất được tải xuống máy chủ bị xâm nhập. Có bao nhiêu tệp trong số này có khả năng là tệp độc hại?
* `index=* sourcetype=zeek:files tx_hosts="195.88.191.59" | table _time seen_bytes md5 sha1 sha256` dùng query này để phân tích xem được mã hash của các tệp đã được zeek phát hiện có liên quan đến máy chủ 195.88.191.59 
* Tôi đã check cả 5 mã hash này trên virus total và tôi đã tìm đc đáp án là 5.
## Câu hỏi : Mã băm SHA256 của tệp độc hại được ngụy trang dưới dạng .txt tệp là gì?
* 
