# Báo cáo Lab: 3CX Supply Chain Attack – CyberDefender

## Câu hỏi 1: Có bao nhiêu phiên bản 3CX chạy trên Windows đã được gắn cờ là phần mềm độc hại?

Tôi đã thử tìm kiếm với từ khóa 3CX trên Google để xem coi có bao nhiêu phiên bản của 3CX chạy trên Windows có dính malware.  
![](https://github.com/user-attachments/assets/e1ee3d0c-fc4c-46ce-a6a8-01f4520ec30c)  
![](https://github.com/user-attachments/assets/0f925e56-429a-4c0e-a7cb-25a159912913)

**Kết luận:** Có **2 phiên bản** 3CX bị nhiễm độc.

---

## Câu hỏi 2: Thời gian tạo UTC của phần mềm độc hại .msi là bao lâu?

![](https://github.com/user-attachments/assets/52cfe504-88fa-4e9c-b182-b8252358ed06)

**Trả lời:** Ta có thể đơn giản tìm được ngày khởi tạo của nó trên VirusTotal.

---

## Câu hỏi 3: Các tệp DLL độc hại nào đã bị .msi tệp này loại bỏ?

![](https://github.com/user-attachments/assets/1239a279-b378-4010-9dd6-0d28aaa5e031)

**Trả lời:** Hai file DLL là:
- `ffmpeg.dll`
- `d3dcompiler_47.dll`

---

## Câu hỏi 4: ID kỹ thuật MITRE được sử dụng để tải DLL độc hại?

![](https://github.com/user-attachments/assets/e35277a0-4bd2-4d19-a0f8-ac45a2aeb1f8)

Tôi tìm thấy kỹ thuật phù hợp nhất là **T1574: Hijack Execution Flow**.  
Đây là kỹ thuật rất quan trọng với các cuộc tấn công chuỗi cung ứng như vụ 3CX.

---

## Câu hỏi 5: Loại mối đe dọa của hai DLL độc hại là gì?

Tôi đã dùng SHA-256 của 2 DLL và tra cứu trên VirusTotal.  
![](https://github.com/user-attachments/assets/a59ac720-85de-4639-b4e3-1fdc74ccf845)  
![](https://github.com/user-attachments/assets/1b3c8486-66b0-4f55-bb56-dedf7a7a9003)

**Trả lời:** Cả hai DLL đều bị phân loại là **Trojan**.

---

## Câu hỏi 6: ID MITRE cho kỹ thuật trốn tránh hộp cát là gì?

![](https://github.com/user-attachments/assets/02620861-6beb-46d2-9524-f0184cf828b1)

Truy cập https://attack.mitre.org và tìm kiếm với từ khóa “sandbox”, tôi xác định được mã kỹ thuật là **T1497**.

---

## Câu hỏi 7: Hypervisor nào là mục tiêu của kỹ thuật chống phân tích trong ffmpeg.dll?

![](https://github.com/user-attachments/assets/527481f3-32fe-428a-93ef-8737346c4ca3)

Trong phần Behavior -> Defense Evasion của VirusTotal, tôi thấy nó dùng máy ảo **VMware** để tránh phân tích.

---

## Câu hỏi 8: ffmpeg.dll sử dụng thuật toán mã hóa nào?

![](https://github.com/user-attachments/assets/05654aff-afa3-412f-aa45-46dcd82614eb)

Từ ảnh write-up và phân tích trong VirusTotal, ta xác định thuật toán mã hóa được dùng là **RC4** với key `"3jB(2bsG#@c7"`.

---

## Câu hỏi 9: Nhóm nào chịu trách nhiệm cho cuộc tấn công?

Dựa theo bài viết tại: https://www.coalitioninc.com/blog/security-incident-retrospective-3CX-supply-chain  
![](https://github.com/user-attachments/assets/88cae539-8556-410b-b33e-8d352ed0291d)

**Kết luận:** Nhóm **Lazarus** (Bắc Triều Tiên) được cho là đứng sau cuộc tấn công này.

---
