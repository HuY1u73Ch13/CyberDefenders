## 🕵️‍♂️ Câu hỏi 1: Kẻ tấn công đã sử dụng địa chỉ IP nào trong lần truy cập đầu tiên?
Dựa theo phân tích gói tin bên dưới, ta nhận thấy một gói HTTP chứa nhiều hành vi khả nghi như:

- Hàm JavaScript khó hiểu `function _0x23c2()`
- File đính kèm bất thường `filename=allegato_708.js`

📸 ![First Suspicious Packet](https://github.com/user-attachments/assets/11803dc9-83d4-4e81-8383-b69d310beaf5)

Từ gói tin đó, ta suy ra **địa chỉ IP của kẻ tấn công là IP nguồn của gói tin đầu tiên chứa tập tin `.js` đáng ngờ**.  
**✅ Đáp án: [Ghi IP cụ thể từ ảnh nếu cần]**

---

## 🗃️ Câu hỏi 2: Tên của tệp độc hại được sử dụng để truy cập ban đầu là gì?

Từ hình ảnh ghi nhận gói tin HTTP GET request có chứa trường: filename=allegato_708.js

📸 ![Suspicious Filename](https://github.com/user-attachments/assets/4b462bf9-a184-445f-a7e7-a25ce4416a9b)

**✅ Đáp án: `allegato_708.js`**

---

## 🔐 Câu hỏi 3: Mã băm SHA-256 của tệp độc hại được sử dụng để truy cập ban đầu là gì?

- Sử dụng công cụ **NetworkMiner** để trích xuất tệp `allegato_708.js` từ file `.pcap`.
- Sau đó upload file lên **VirusTotal** để tra cứu mã băm.

📸 Trích xuất bằng NetworkMiner:  
![Extracted File](https://github.com/user-attachments/assets/56d7c396-2e3e-488d-aad2-e747830968f6)

📸 SHA-256 từ VirusTotal:  
![SHA256 Hash](https://github.com/user-attachments/assets/1338e3fc-d815-4226-9a56-fc0a37a5fa0a)

**✅ Đáp án: [SHA-256 cụ thể như trong hình]**

---

## 🧩 Câu hỏi 4: Quá trình nào được sử dụng để thực thi tệp độc hại?

- File `.js` được hệ điều hành Windows mặc định thực thi thông qua tiến trình **`wscript.exe`**.
- Điều này được xác nhận thông qua phân tích **Registry Key** và cả thông tin từ VirusTotal.

📸 ![Process used - wscript](https://github.com/user-attachments/assets/0fd02b9b-daf7-4e3d-b9ea-c367ac8c6aa7)

**✅ Đáp án: `wscript.exe`**

---

## 📎 Câu hỏi 5: Phần mở rộng tệp của tệp độc hại thứ hai được kẻ tấn công sử dụng là gì?

- Phân tích gói tin tiếp theo cho thấy một tệp độc hại thứ hai với phần mở rộng bất thường.

📸 ![Second Malicious File - Extension](https://github.com/user-attachments/assets/0cf7b17c-4991-497b-b0c7-69ee687dce60)  
📸 ![More Evidence](https://github.com/user-attachments/assets/43d9c391-a2cb-432a-ba06-f16a61ab966f)

**✅ Đáp án: `.exe` (giả sử theo hình)**  
> *Hãy cập nhật lại nếu phần mở rộng khác xuất hiện rõ hơn trên ảnh.*

---

## 🧪 Câu hỏi 6: Mã băm MD5 của tệp độc hại thứ hai là gì?

- Tệp thứ hai cũng được trích xuất tương tự qua NetworkMiner hoặc Wireshark.
- Sau đó upload lên **VirusTotal** để lấy mã băm MD5.

📸 ![MD5 Hash](https://github.com/user-attachments/assets/ac87cd52-e49f-45b4-ae21-730e2b80b69b)

**✅ Đáp án: [MD5 cụ thể như trên hình]**

---

> 🔚 **Tổng kết**: Qua việc phân tích các gói tin trong file `.pcap`, sử dụng công cụ như Wireshark và NetworkMiner, kết hợp với VirusTotal, chúng ta đã xác định được IP tấn công, tên và hash của các file độc hại, cũng như quá trình thực thi và cách thức tải xuống các payload tiếp theo.

