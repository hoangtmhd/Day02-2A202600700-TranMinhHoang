# 01 — Individual Problem Scan

**Vai trò:** Lập trình viên / Chuyên viên CNTT tại Bệnh viện Bạch Mai  

---

## Scan rộng
Dưới đây là danh sách 10 vấn đề thực tế được quan sát trực tiếp từ công việc hàng ngày của một lập trình viên tại bệnh viện tuyến cuối Bạch Mai, phân tích qua 4 lăng kính cốt lõi.

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | AI có thể tốt hơn | Viết câu lệnh SQL phức tạp để trích xuất dữ liệu lâm sàng phục vụ nghiên cứu khoa học từ DB khổng lồ. | Dev/IT, Bác sĩ nghiên cứu | Mất 60-90 phút/yêu cầu. Dễ sai logic liên kết bảng (JOIN) hoặc gây treo DB production vì truy vấn nặng. |
| 2 | Tốn thời gian | Tóm tắt và lọc thông tin cốt lõi/action items từ các cuộc họp chuyên môn & giao ban dài dòng. | Lập trình viên (đi họp) | Họp 2-3 tiếng/buổi. Mất 45 phút sau họp để tổng hợp, ghi chép lại các việc cần làm. |
| 3 | Lặp lại | Hướng dẫn xử lý các lỗi máy tính/phần mềm nghiệp vụ cơ bản lặp đi lặp lại cho y bác sĩ (Helpdesk). | Nhân viên IT Helpdesk, Bác sĩ/Điều dưỡng | 30-40 cuộc gọi/ngày. Mất 15-20 phút giải thích từng bước qua điện thoại hoặc chạy xuống tận nơi. |
| 4 | Tốn thời gian | Đọc hiểu và phân tích văn bản, công văn, quy định y tế mới từ Bộ/Sở Y tế để cập nhật phần mềm HIS. | Lập trình viên hệ thống | Tốn 30-45 phút đọc một công văn dài dằng dặc để tìm ra đúng 2 dòng quy định ảnh hưởng đến code. |
| 5 | Tốn thời gian | Soạn thảo các tờ trình y tế, công văn đề xuất nâng cấp thiết bị, giải trình lỗi hệ thống theo chuẩn hành chính công. | Lập trình viên, Trưởng nhóm IT | Mất 60-120 phút/văn bản do phải căn chỉnh câu từ hành chính nghiêm ngặt và đúng form mẫu. |
| 6 | AI có thể tốt hơn | Sắp xếp, ưu tiên danh sách công việc (Task prioritization) khi bị ngập trong hàng tá task khẩn cấp đổ về cùng lúc. | Lập trình viên | Mất 15-20 phút loay hoay mỗi sáng. Dễ bỏ sót task quan trọng do bị phân tâm bởi các cuộc gọi khẩn. |
| 7 | Pain từ người khác | Bác sĩ phàn nàn quy trình click trên phân hệ HIS mới cập nhật quá phức tạp, làm chậm tốc độ khám bệnh. | Bác sĩ phòng khám, Lập trình viên | Bác sĩ phải click 7-8 lần để kê đơn. Phản ánh rải rác trên Zalo/điện thoại, IT khó tổng hợp điểm nghẽn chính xác. |
| 8 | Lặp lại | Đối soát dữ liệu xuất toán Bảo hiểm Y tế (BHYT) bị lệch giữa hệ thống HIS của viện và Cổng giám định BHYT. | Chuyên viên IT đối soát, Kế toán viện | Phải đối soát thủ công file Excel hàng ngàn dòng dữ liệu mỗi tuần. Mất 3-4 tiếng/lần. |
| 9 | Lặp lại | Viết báo cáo tuần gửi Trưởng phòng CNTT (danh sách lỗi đã sửa, tiến độ nâng cấp server, phân hệ HIS). | Lập trình viên | Mất 45 phút chiều thứ Sáu để gom việc từ Git/Jira và gõ báo cáo. |
| 10 | AI có thể tốt hơn | Đọc hiểu tài liệu API/SDK tích hợp với các đối tác bên ngoài (hệ thống thanh toán không tiền mặt, thiết bị xét nghiệm). | Lập trình viên tích hợp | Tài liệu kỹ thuật tiếng Anh hoặc tiếng Việt dịch máy sơ sài, tốn 2-3 tiếng để nắm bắt được cách call API đúng. |

---

## Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Weekly Report | Tần suất cao (Bạch Mai làm cực kỳ nhiều đề tài), giá trị lớn cho y học, giảm thiểu rủi ro treo DB hệ thống, nâng hiệu suất IT. | Làm sao để AI hiểu đúng schema DB khổng lồ mà vẫn bảo mật thông tin bệnh nhân (an toàn dữ liệu). |
| 2 | Review PRD | Đi họp quá nhiều, thời gian họp lấn át thời gian làm việc thực tế, thông tin cuộc họp y tế/kỹ thuật cực kỳ phức tạp. | Làm sao chuyển đổi âm thanh tiếng Việt hội thoại y khoa viết tắt/nói ngọng thành text chính xác để AI tóm tắt. |
| 3 | Slack Search | Lỗi rất lặp lại, tốn thời gian giao tiếp thủ công, có thể đóng gói thành tài liệu tự phục vụ để giảm tải cho IT. | Y bác sĩ lớn tuổi có chịu tự dùng công cụ hướng dẫn thay vì gọi điện bắt IT xuống phòng khám không. |

---

## Problem Card #1 — Trích xuất dữ liệu lâm sàng từ Database bệnh viện phục vụ nghiên cứu

**Problem 1 câu:**  
Lập trình viên mất từ 60-90 phút cho mỗi yêu cầu trích xuất dữ liệu nghiên cứu từ bác sĩ, dễ viết sai SQL query phức tạp trên database hàng ngàn bảng hoặc làm nghẽn/treo hệ thống production do chạy câu lệnh truy vấn chưa tối ưu.

**Actor:**  
Lập trình viên phòng CNTT chịu trách nhiệm quản trị và khai thác dữ liệu hỗ trợ nghiên cứu khoa học.

**Thời điểm / bối cảnh:**  
Khi các bác sĩ, tiến sĩ đăng ký đề tài nghiên cứu cấp cơ sở/bộ và yêu cầu trích xuất bộ dữ liệu bệnh án cũ theo các tiêu chí lâm sàng cụ thể (ví dụ: danh sách bệnh nhân >60 tuổi, chẩn đoán ICD-10 là tiểu đường, điều trị bằng thuốc X tại khoa Y trong 3 năm qua).

**Current workflow:**
1. Export dữ liệu thô hoặc mô tả yêu cầu lâm sàng của bác sĩ.
2. Tra cứu thủ công các bảng (tables) và trường (fields) tương ứng trên hệ thống HIS/EMR của viện.
3. Dev tự viết câu lệnh SQL (chứa nhiều lệnh JOIN, sub-query, điều kiện lọc phức tạp).
4. Review và tự tối ưu hóa câu lệnh để tránh full table scan hoặc deadlock.
5. Chạy truy vấn trên database và xuất kết quả ra Excel gửi bác sĩ.

**Bottleneck:**  
Bước viết SQL query phức tạp và tự tối ưu hóa câu lệnh. Việc nhớ chính xác cấu trúc schema của hàng ngàn bảng dữ liệu và đảm bảo câu lệnh chạy mượt mà trên database hàng triệu bản ghi rất căng thẳng và dễ sai sót.

**Impact:**  
Mỗi tuần phát sinh khoảng 5-7 yêu cầu trích xuất dữ liệu. Dev mất 8-10 tiếng/tuần chỉ để viết SQL. Bác sĩ phải chờ đợi từ 3-5 ngày mới có dữ liệu làm nghiên cứu.

**Success metric:**  
Giảm tổng thời gian xử lý một yêu cầu từ 90 phút xuống dưới 20 phút, không làm giảm tính chính xác của dữ liệu và đảm bảo an toàn truy vấn hệ thống.

**Non-AI alternative:**  
Xây dựng một hệ thống dashboard tự phục vụ (Self-service BI). Tuy nhiên phương án này rất khó vì yêu cầu nghiên cứu của mỗi bác sĩ là độc nhất và thay đổi liên tục, không cố định theo một vài chiều kích dashboard có sẵn.

**AI hypothesis:**  
Sử dụng LLM được cung cấp thông tin Schema DB dưới dạng Metadata (không chứa dữ liệu nhạy cảm của bệnh nhân) để chuyển đổi yêu cầu ngôn ngữ tự nhiên của bác sĩ thành câu lệnh SQL nháp an toàn và tối ưu. Lập trình viên chỉ cần kiểm tra logic, tối ưu nhẹ và thực thi.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 90 phút (Thủ công & Dễ rủi ro)

[1 Nhận y/c y khoa] 
→ [2 Gọi điện làm rõ thuật ngữ: 20'] 
→ [3 Tra cứu schema thủ công: 15'] 
→ [4 Tự viết SQL phức tạp: 30']  <-- bottleneck (Dễ sai sót)
→ [5 Tự tối ưu truy vấn: 15']    <-- bottleneck (Lo lắng treo DB)
→ [6 Run & Xuất Excel: 10']
```

### Draft future workflow

```text
FUTURE STATE — 18 phút (AI hỗ trợ - Con người kiểm duyệt)

[1 Nhận y/c y khoa] 
→ [2 Nhập mô tả y khoa + Prompt Context vào AI: 2'] 
→ [3 AI tự đối chiếu Metadata Schema & viết SQL mẫu: 1'] 
→ [4 AI tối ưu hóa truy vấn (Explain Plan): 1'] 
→ [5 Dev Review, chỉnh sửa & chạy thử trên DB Read-only: 12']  <-- human boundary (An toàn)
→ [6 Xuất Excel gửi bác sĩ: 2']

Fallback: AI sinh SQL sai hoặc chạy quá chậm -> Dev quay lại viết thủ công như cũ.
```

---

## Problem Cards #2 và #3 — tóm tắt

| Card | Actor | Bottleneck | Metric | Quick gut | Vì sao chưa chọn làm #1 |
|---|---|---|---|---|---|
| Tóm tắt cuộc họp | Lập trình viên y tế (thư ký họp) | Phải họp 2-3 tiếng, tốn nhiều thời gian chắt lọc biên bản họp sau đó. | 45 phút → 8 phút | Workflow | Yêu cầu tính chính xác tuyệt đối, rủi ro sai lệch từ ngữ viết tắt y khoa cần IT rà soát kỹ. |
| Trợ lý Helpdesk | Nhân viên IT Helpdesk | Phải trả lời thủ công các lỗi cơ bản lặp đi lặp lại nhiều lần cho bác sĩ. | 15 phút → 3 phút | Workflow | Giá trị y học và tính thử thách kỹ thuật không cao bằng trích xuất dữ liệu lâm sàng. |

---

## Chọn card muốn pitch nhất

**Card tôi muốn pitch nhất:**  
`Problem Card #1: Trích xuất dữ liệu lâm sàng từ Database bệnh viện phục vụ nghiên cứu`

**Vì sao:**  
* **Pain thật & Nghiệp vụ rõ:** Yêu cầu nghiên cứu khoa học của bác sĩ tại Bạch Mai cực kỳ nhiều. Mỗi đề tài cần dữ liệu lâm sàng rất đặc thù mà các dashboard có sẵn không thể đáp ứng nổi.
* **Tác động lớn:** Giảm thời gian chờ đợi của bác sĩ từ vài ngày xuống vài giờ, đồng thời giải phóng 8-10 tiếng viết SQL thủ công mỗi tuần của lập trình viên.
* **Tư duy AI-safe:** Thể hiện rõ nét ranh giới kiểm soát an toàn của con người (`Human Boundary`). AI chỉ đóng vai trò trợ lý viết code nháp, lập trình viên trực tiếp kiểm duyệt và chạy trên DB read-only nhằm tránh rủi ro bảo mật dữ liệu y tế và rủi ro treo hệ thống production.

**Câu hỏi tôi muốn nhóm challenge:**  
Làm thế nào để bảo mật thông tin nhạy cảm của bệnh nhân khi cung cấp ngữ cảnh Schema Database (Metadata) cho AI, đảm bảo tuân thủ nghiêm ngặt Luật An toàn thông tin mạng trong môi trường y tế?
