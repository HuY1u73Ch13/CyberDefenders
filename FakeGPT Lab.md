## Câu hỏi 1: Tiện ích mở rộng của trình duyệt sử dụng phương pháp mã hóa nào để che giấu URL mục tiêu, khiến chúng khó bị phát hiện hơn trong quá trình phân tích?
* ![{625656D7-2785-469E-BA5C-B7D19E55511A}](https://github.com/user-attachments/assets/227c4ff1-0242-4255-b803-260e615f8048)
* Đọc code ta thấy có 1 `const targets` có vẻ là mã hóa `base64` nên tôi đã đưa thử lên web `CyberChef` để check và đúng sau khi decode thì ta được `www.facebook.com`
* Và đọc code từ bên dưới thì ta có thể thấy được là có vẻ khi victim cài extension này vào thì atacker có thể đọc được `username` và `passwd`
## Câu hỏi 2: Tiện ích mở rộng nào theo dõi hành vi trộm cắp dữ liệu, nhắm vào tài khoản người dùng để đánh cắp thông tin nhạy cảm?
* ![{9626C70B-FBCA-4E7F-8D9E-53A79B5D25C9}](https://github.com/user-attachments/assets/4f917d28-3a2c-4ed6-97a5-43eba95c0d3e)
## Câu hỏi 3: Phần mở rộng này sử dụng loại phần tử HTML nào để gửi dữ liệu bị đánh cắp?
* ![{9683C258-0667-4343-9532-D2641EDA1A5D}](https://github.com/user-attachments/assets/d3127ea2-20b4-4977-a49b-31b8c11a6acf)
* Phần Extension này sử dụng dữ thẻ <img> + thuộc tính .src để gửi dữ liệu đã bị đánh cắp mã hóa base64 để gửi đi
## Câu hỏi 4: Điều kiện cụ thể đầu tiên trong mã kích hoạt tiện ích mở rộng tự hủy kích hoạt là gì?
* ![{0F579786-CE78-4A91-8250-233AF424DF98}](https://github.com/user-attachments/assets/b23db13d-92ce-482c-93a5-f4ad12ab4940)
* ![image](https://github.com/user-attachments/assets/66733369-983e-4429-9d3c-78ded4d45969)
* `navigator.plugins.length === 0` nó sẽ kiểm tra `plugins` trên gg nếu không có gì nó sẽ trả vể không hoặc là kiểm tra `/HeadlessChrome/.test(navigator.userAgent)`
* Kiểm tra coi chuỗi `navigator.userAgent` có chứa từ `"HeadlessChrome"` hay không nếu có 1 trong 2 cái trên thì nó sẽ tự động hủy
## Câu hỏi 5: Tiện ích mở rộng này nắm bắt sự kiện nào để theo dõi dữ liệu người dùng nhập qua biểu mẫu?
* ![{1015F417-AD53-4719-9499-93FAC344ACE0}](https://github.com/user-attachments/assets/f651175d-3dc0-4bd6-ae51-08c3a221fa45)
* Đọc theo câu lệnh thì ta sẽ biết được là nó sẽ bắt đầu đọc dữ liệu khi người dùng bấm `submit`
## Câu hỏi 6: Tiện ích mở rộng này sử dụng API hoặc phương pháp nào để ghi lại và theo dõi các lần nhấn phím của người dùng?
* Extension này sử dụng event là `keydown:là sự kiện xảy ra mỗi khi người dùng nhấn phím` `event.key:trả về kí tự sau mỗi lần nhấn phím` 
## Câu hỏi 7: Miền mà phần mở rộng truyền dữ liệu được lọc ra là gì?
* ![{D50A527C-B86C-4DF4-AC6B-96791810EAE7}](https://github.com/user-attachments/assets/36e687a9-cc32-4341-ba56-995ed2072d0a)
* `Mo.Elshaheedy.com`
## Câu hỏi 8: Hàm nào trong mã được sử dụng để đánh cắp thông tin đăng nhập của người dùng, bao gồm tên người dùng và mật khẩu?
* ![image](https://github.com/user-attachments/assets/c50bf9e8-2da4-4282-948d-7586ca30f95e)
* Hàm này sẽ nhận 2 tham số `username, password` tạo 1 tham số payload và encrypt nó sẽ gửi đến server.
## Câu hỏi 9: Thuật toán mã hóa nào được áp dụng để bảo mật dữ liệu trước khi gửi?
* ![{DDE63C8E-3060-4B65-8157-04AC81A04321}](https://github.com/user-attachments/assets/a4973d29-2b0c-48f3-b11d-0930f87f7502)
## Câu hỏi 10: Phần mở rộng này có chức năng gì trong việc lưu trữ hoặc xử lý dữ liệu liên quan đến phiên và thông tin xác thực?
* ![{FCBE78CD-ED55-4821-BF59-493786C92F8C}](https://github.com/user-attachments/assets/dbe25713-f0fc-4dac-bd04-cdc97040dba8)



