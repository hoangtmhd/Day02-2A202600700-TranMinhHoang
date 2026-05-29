# 02 — Group Problem Statement

---

## Group convergence
Nhóm gồm các thành viên đến từ nhiều bối cảnh khác nhau (trường học, hành chính, kỹ thuật y tế) cùng trình bày các ý tưởng cá nhân để tìm ra vấn đề cốt lõi. Tổng cộng nhóm thu thập được 14 candidates.

### Cluster và pattern chung
*   **Cluster 1: Báo cáo & Tổng hợp dữ liệu phức tạp (Thông tin/Nội dung nhiều nguồn)**
    *   *Các ý tưởng bao gồm:* (1) SQL trích xuất dữ liệu lâm sàng; (2) Tóm tắt họp giao ban; (12) Tổng hợp báo cáo CME cuối tháng; (13) Kiểm tra hồ sơ E-CME; (14) Tổng hợp câu hỏi hội thảo.
    *   *Pattern chung:* Gom, xử lý và tóm tắt dữ liệu từ nhiều nguồn khác nhau phục vụ báo cáo hành chính hoặc đưa ra quyết định chuyên môn.
*   **Cluster 2: Hỗ trợ người dùng & Giải đáp thông tin (Chatbot / Helpdesk Q&A)**
    *   *Các ý tưởng bao gồm:* (3) Trợ lý Helpdesk thông minh lỗi lặp lại; (8) Chatbot giải đáp thông tin Handbook sinh viên; (10) Quá tải IT Helpdesk.
    *   *Pattern chung:* Thay thế các tương tác lặp đi lặp lại giữa người dùng và nhân viên hỗ trợ bằng các giải pháp tự phục vụ (Self-service) sử dụng AI.
*   **Cluster 3: Quy trình vận hành và đời sống (Không phù hợp AI hoặc giải quyết bằng Rule/CSDL)**
    *   *Các ý tưởng bao gồm:* (4) Họp giao ban 60 phút mỗi ngày; (5) Di chuyển đi làm xa; (6) Thông báo trường học phân tán; (7) Điền form lặp lại; (9) Bác sĩ ghi chép bệnh án quá tải; (11) Ít người vận hành hệ thống.
    *   *Pattern chung:* Vấn đề do quy trình hành chính, cự ly địa lý hoặc định biên nhân sự chưa hợp lý. Cần giải quyết bằng tái cấu trúc quy trình (`Process fix`), chính sách tổ chức hoặc thiết kế lại database dùng chung (`Rule/Database`).

---

## Shortlist và score
Chấm điểm theo thang điểm từ 1 - 5 cho từng tiêu chí để đạt đồng thuận chọn bài toán tốt nhất:

| Candidate | Actor rõ | Workflow rõ | Pain có chứng cứ | Impact đo được | Làm được trong lab | So sánh được R/W/A | Nhóm hiểu sâu domain | Tổng điểm |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **1. Trích xuất dữ liệu lâm sàng** | 5 | 5 | 5 | 5 | 4 | 5 | 4 | **33** |
| **2. Chatbot Tân sinh viên** | 5 | 5 | 4 | 4 | 5 | 4 | 5 | **32** |
| **3. Báo cáo CME cuối tháng** | 5 | 4 | 5 | 5 | 3 | 4 | 4 | **29** |

*   **Nhóm chọn:** `Trích xuất dữ liệu lâm sàng phục vụ nghiên cứu khoa học`
*   **Vì sao chọn:**
    1. **Nghiệp vụ kỹ thuật rõ ràng:** Đây là bài toán có luồng xử lý dữ liệu và cấu trúc nghiệp vụ kỹ thuật cực kỳ chuẩn xác, rất thích hợp để phân tích so sánh sâu các phương án Rule / Workflow / Agent.
    2. **Impact cực lớn:** Giúp giải phóng 8-10 tiếng viết SQL thủ công mỗi tuần của lập trình viên và rút ngắn thời gian chờ dữ liệu của bác sĩ nghiên cứu từ vài ngày xuống vài mươi phút.
    3. **Tư duy AI An toàn (AI-safe):** Đòi hỏi nhóm phải giải quyết được bài toán hóc búa về an toàn dữ liệu mạng và thiết lập ranh giới kiểm soát chặt chẽ của con người (`Human-in-the-loop`).
*   **Vì sao không chọn các bài khác:**
    *   *Chatbot Tân sinh viên:* Dù dễ triển khai nhưng giá trị thực tiễn và tính thử thách kỹ thuật không cao bằng bài toán y tế.
    *   *Báo cáo CME cuối tháng:* Quy trình lấy dữ liệu đầu vào quá hỗn tạp, khó chuẩn hóa trong thời gian ngắn của buổi lab.

---

## Quick validation
Nhóm thực hiện khảo sát hoặc phỏng vấn nhanh với 15 cán bộ nghiên cứu y khoa, 3 bác sĩ Bạch Mai và 2 nhân viên IT.

| Nguồn | Số người | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Phỏng vấn nhanh | 5 | Bác sĩ: Rất nản khi xin số liệu, phải đợi IT từ 3 - 7 ngày, số liệu nhận về hay bị lệch cột/thiếu tiêu chí lọc nên phải xin đi xin lại nhiều lần.<br>IT: Rất ngại viết SQL trích xuất vì cấu trúc DB y tế (HIS) quá rắc rối với hàng ngàn bảng liên kết, sợ viết câu lệnh nặng gây đơ/treo DB production. | Có bác sĩ phản hồi nếu chỉ cần xem số lượng ca bệnh tổng quan theo tháng/năm thì hệ thống dashboard chung của phòng Kế hoạch tổng hợp đã đáp ứng được, không cần trích xuất sâu. | **Thu hẹp phạm vi:** Không tự động hóa việc xuất báo cáo số liệu tổng quan đơn giản (đã có dashboard), tập trung giải quyết phân khúc **trích xuất tập dữ liệu lâm sàng chi tiết, có điều kiện lọc phức tạp** phục vụ đề tài nghiên cứu chuyên sâu. |
| Khảo sát online | 15 | 12/15 người khẳng định quy trình trích xuất hiện tại là "bottleneck" lớn nhất làm chậm tiến độ làm đề tài.<br>100% mong muốn nhận dữ liệu trong ngày. | 3 người lo ngại về tính chính xác của dữ liệu nếu hệ thống sinh tự động, sợ rằng AI viết SQL sai logic y khoa dẫn đến sai lệch kết quả công bố khoa học. | **Bổ sung chốt chặn con người (`Human-in-the-loop`):** Lập trình viên bắt buộc phải kiểm duyệt lại câu lệnh SQL của AI, chạy thử trên DB read-only và kiểm chứng mẫu ngẫu nhiên 5-10 bản ghi trước khi gửi bác sĩ. |
| Log / Ticket | 20 | Thời gian hoàn thành trung bình là 4.2 ngày/yêu cầu.<br>35% yêu cầu phải viết lại SQL hoặc trích xuất lại do hiểu nhầm ý của bác sĩ ở lần đầu. | Một số phiếu bị chậm do thủ tục phê duyệt hành chính (ký tờ trình giấy) chứ không hoàn toàn do IT viết SQL chậm. | **Xác định ranh giới can thiệp:** Chỉ can thiệp AI sau khi yêu cầu đã được phê duyệt hành chính, tập trung tối ưu hóa bước viết code và đối soát kỹ thuật. |

*   **Insight sau validation:**
    > *"Nỗi đau lớn nhất không nằm ở khâu phê duyệt hành chính hay xuất file Excel. Điểm nghẽn thực sự là **sự bất đồng ngôn ngữ** giữa 'ngôn ngữ lâm sàng' của bác sĩ và 'ngôn ngữ cấu trúc dữ liệu' của lập trình viên. AI có tiềm năng đóng vai trò thông dịch viên dịch yêu cầu lâm sàng sang SQL thô, nhưng bắt buộc phải có IT làm chốt chặn kiểm duyệt kỹ thuật để đảm bảo an toàn tuyệt đối cho hệ thống."*

---

## Research giải pháp
Nhóm tìm kiếm các giải pháp kỹ thuật, công cụ và mô hình đã có trên thị trường:

| Nguồn / Tool / Case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| **DBeaver AI Auto-completion** | https://dbeaver.io/ | Hỗ trợ viết nhanh câu lệnh SQL và sinh câu lệnh thô dựa trên mô tả text của Dev. | Tích hợp sẵn trong IDE quản trị database, tốc độ sinh SQL nhanh. | Không hiểu ngữ cảnh thuật ngữ chuyên môn y tế (như các mã ICD-10, các chỉ số xét nghiệm lâm sàng đặc thù) nếu không có context schema y tế rõ ràng. Có nguy cơ rò rỉ cấu trúc DB nếu dùng public AI. | Dùng như một công cụ hỗ trợ dev gõ phím nhanh, chưa giải quyết được khâu "dịch" yêu cầu y tế của bác sĩ. |
| **Vanna.ai (Text-to-SQL)** | https://vanna.ai/ | Cho phép huấn luyện AI dựa trên cấu trúc bảng (schema DDL), tài liệu hướng dẫn và câu lệnh SQL mẫu để dịch ngôn ngữ tự nhiên sang SQL. | Có thể tự chạy offline/mạng nội bộ (Self-hosted), độ chính xác tăng dần theo thời gian khi được train thêm dữ liệu mẫu. | Cần công sức chuẩn hóa DDL metadata ban đầu và viết tập câu hỏi/câu SQL mẫu để train. Vẫn có nguy cơ sinh câu lệnh chạy full-table scan nếu không giới hạn LIMIT hay INDEX. | **Rất đáng học hỏi:** Pattern tốt là train AI bằng Schema Metadata (không chứa thông tin bệnh nhân) để đảm bảo an toàn dữ liệu và tăng độ chính xác thuật ngữ y tế. |
| **Azure OpenAI in Healthtech** | https://azure.microsoft.com/en-us/products/cognitive-services/openai-service/ | Cung cấp cổng kết nối LLM tuân thủ tiêu chuẩn bảo mật y tế HIPAA/HITRUST. | Đảm bảo tuyệt đối không dùng dữ liệu/cấu trúc DB của bệnh viện để train lại model công cộng, bảo mật cao nhất. | Chi phí sử dụng cao, đòi hỏi cấu hình mạng VPN nội bộ phức tạp. | Bắt buộc phải sử dụng các API có cam kết bảo mật dữ liệu doanh nghiệp, không sử dụng các chatbot public miễn phí. |

*   **Research takeaway:**
    > *"Không bao giờ được đưa cấu trúc DB thật của bệnh viện lên các AI public miễn phí. Để triển khai thực tế, nhóm bắt buộc phải áp dụng kiến trúc **Vanna.ai** (tự chạy offline/nội bộ) hoặc sử dụng các cổng API doanh nghiệp bảo mật (như Azure OpenAI/Google Cloud Vertex AI) để bảo vệ an toàn thông tin y tế."*

---

## Workflow before/after

### Sơ đồ Workflow hiện tại (Current State — 6 bước, 90 phút thủ công)
```text
[1 Bác sĩ gửi y/c trích xuất: 5'] 
→ [2 Gọi điện làm rõ thuật ngữ lâm sàng/ICD-10: 20'] 
→ [3 Tra cứu thủ công Schema DB y tế: 15'] 
→ [4 IT tự viết SQL Query phức tạp: 30']       <-- BOTTLENECK (Dễ sai logic join bảng)
→ [5 IT tự tối ưu truy vấn để tránh treo DB: 15'] <-- BOTTLENECK (Nỗi lo deadlock DB thật)
→ [6 IT chạy lệnh & xuất file Excel gửi bác sĩ: 5']
```

### Sơ đồ Workflow tương lai (Future State — 5 bước, 18 phút AI hỗ trợ)
```text
[1 Nhập mô tả y khoa + Prompt Context (Schema DDL đã được làm sạch) vào Vanna.ai nội bộ: 2'] 
→ [2 AI đối chiếu Metadata Schema, tự động sinh SQL mẫu & đề xuất Explain Plan: 2']     -- AI intervention point
→ [3 IT Review, chỉnh sửa logic & tối ưu hóa câu lệnh trên Database Read-Only: 10']     -- HUMAN BOUNDARY (An toàn)
→ [4 IT đối soát dữ liệu ngẫu nhiên 5-10 dòng với bệnh án gốc: 3']                       -- HUMAN BOUNDARY (Chất lượng)
→ [5 IT thực thi & xuất file Excel gửi bác sĩ qua cổng bảo mật nội bộ: 1']

Fallback: AI sinh SQL sai cấu trúc hoặc chạy quá chậm -> IT hủy kết quả AI và quay lại viết code tay như cũ.
```

### Bảng so sánh tác động Before / After
| Chỉ số (Metric) | Trạng thái trước (Before) | Kỳ vọng sau (After) | Ghi chú kiểm soát |
|---|---:|---:|---|
| **Số bước thực hiện** | 6 bước | 5 bước | Tối giản bước trung gian làm rõ thuật ngữ nhờ AI dịch thô. |
| **Tổng thời gian xử lý** | 90 phút/yêu cầu | 18 phút/yêu cầu | **Tiết kiệm 80%** thời gian cho mỗi lượt trích xuất. |
| **Số bước thủ công** | 6/6 bước thủ công | 2/5 bước (Bước 3: Review & Bước 4: Đối soát là thủ công) | Lập trình viên tập trung vào khâu kiểm duyệt chất lượng thay vì gõ code thô. |
| **Điểm nghẽn chính** | IT tự viết SQL phức tạp và lo sợ chạy câu lệnh nặng gây deadlock hệ thống HIS của viện. | IT rà soát logic y khoa của câu lệnh SQL và đối soát dữ liệu mẫu thực tế. | Điểm nghẽn nằm ở khâu kiểm soát chất lượng (Human Boundary) - đây là điểm kiểm soát an toàn và chấp nhận được. |
| **Rủi ro mới phát sinh** | SQL viết tay bị sai logic y khoa; IT chạy truy vấn nặng làm chậm hệ thống HIS của viện. | AI bịa cấu trúc bảng (Hallucination); Nguy cơ rò rỉ dữ liệu nhạy cảm của bệnh nhân nếu dùng AI Cloud public. | Khắc phục triệt để bằng cách chỉ cung cấp Schema Metadata DDL cho AI nội bộ (Local/On-premise LLM). |

---

## Problem Statement v0

| Trường dữ liệu (Field) | Nội dung chi tiết |
|---|---|
| **Actor (Ai đau?)** | Lập trình viên phòng CNTT (chịu trách nhiệm trích xuất dữ liệu) và Bác sĩ/Dược sĩ đang làm nghiên cứu khoa học. |
| **Workflow hiện tại** | Tiếp nhận yêu cầu -> Gọi điện làm rõ thuật ngữ -> Tra cứu Schema DB -> Tự viết SQL Query -> Tối ưu hóa truy vấn -> Thực thi trên DB và xuất Excel gửi bác sĩ. |
| **Bottleneck (Bước nghẽn)** | Bước viết SQL phức tạp và tối ưu hóa câu lệnh để tránh deadlock/full-table scan trên cơ sở dữ liệu y tế cực kỳ đồ sộ. |
| **Impact (Tác động xấu)** | * IT mất 8-10 tiếng/tuần viết SQL thủ công.<br>* Bác sĩ phải chờ đợi từ 3 - 7 ngày mới có số liệu làm đề tài.<br>* Nguy cơ làm nghẽn/treo hệ thống DB đang vận hành thực tế nếu câu lệnh chạy chưa tối ưu. |
| **Success Metric (Thước đo)**| * Thời gian xử lý 1 yêu cầu giảm từ **90 phút xuống dưới 20 phút**.<br>* Thời gian bác sĩ nhận được dữ liệu giảm từ **vài ngày xuống dưới 1 ngày**.<br>* **0% sự cố** treo/nghẽn database do truy vấn nghiên cứu khoa học. |
| **Boundary (Ranh giới)** | * AI **không được kết nối trực tiếp** với DB production thật.<br>* AI **không được tiếp cận dữ liệu cá nhân** định danh bệnh nhân (họ tên, số định danh, địa chỉ).<br>* AI chỉ làm việc với cấu trúc Metadata (DDL). Lập trình viên chịu trách nhiệm phê duyệt cuối cùng. |

---

## Rule / Workflow / Agent

### Phân tích độ phù hợp với AI
*   **Vị trí bài toán:** Ô **Độ phức tạp cao — Độ mơ hồ cao** (hoặc tiệm cận Độ mơ hồ trung bình).
*   **Lập luận chi tiết:**
    *   *Độ phức tạp cao:* Cơ sở dữ liệu y tế của Bệnh viện Bạch Mai có hàng ngàn bảng liên kết cực kỳ phức tạp. Việc viết câu lệnh SQL đòi hỏi kết hợp nhiều câu lệnh JOIN, sub-query và xử lý kiểu dữ liệu lâm sàng đa dạng trên lượng bản ghi cực lớn.
    *   *Độ mơ hồ cao/trung bình:* Không có một câu lệnh SQL duy nhất đúng cho mỗi yêu cầu. Bác sĩ diễn đạt yêu cầu bằng ngôn ngữ lâm sàng tự nhiên, lập trình viên có thể viết SQL theo nhiều cách cấu trúc khác nhau (dùng CTE, subquery, temporary table) để trả về cùng một kết quả. Tuy nhiên, logic lọc kết quả cuối cùng bắt buộc phải chính xác 100% về mặt khoa học y tế.

### Bảng so sánh các phương án thiết kế
| Mức độ | Phương án thiết kế cụ thể cho bài toán | Khi nào phương án này là đủ? | Rủi ro đi kèm | Nhóm có chọn không? |
|---|---|---|---|---|
| **Rule** | Viết sẵn các template SQL (stored procedures) cố định cho các loại đề tài nghiên cứu phổ biến. | Đủ khi bác sĩ chỉ yêu cầu các báo cáo số lượng ca bệnh cơ bản, lặp đi lặp lại. | Không đáp ứng được các đề tài nghiên cứu chuyên sâu vốn luôn thay đổi tiêu chuẩn lâm sàng theo từng ca bệnh đặc thù. | Không chọn làm phương án chính (nhưng dùng để hỗ trợ các query lấy số thô cơ bản). |
| **Workflow** | Bác sĩ nhập y/c -> Hệ thống Vanna.ai dịch sang SQL thô -> Lập trình viên review, chỉnh sửa logic và tối ưu hóa -> Thực thi trên DB read-only. | Hợp lý vì quy trình tuyến tính, AI làm bước nặng nhất (sinh SQL thô từ schema), con người đóng vai trò chốt chặn an toàn (`Human-in-the-loop`). | AI bịa cấu trúc bảng (hallucination) dẫn đến lỗi cú pháp hoặc join sai cột. Cần lập trình viên cứng rà soát. | **CHỌN.** |
| **Agent** | AI Agent tự kết nối DB, tự chạy phân tích, tự xuất báo cáo gửi thẳng cho bác sĩ mà không cần IT can thiệp. | Chỉ đủ khi hệ thống AI cực kỳ thông minh, an toàn tuyệt đối và có thể tự debug lỗi SQL. | **Cực kỳ nguy hiểm.** AI có thể viết câu lệnh slow query gây treo DB HIS đang vận hành; hoặc vi phạm luật bảo mật y tế nếu xuất nhầm dữ liệu nhạy cảm. | **KHÔNG CHỌN.** |

*   **Mức chọn:** `Workflow`
*   **Lý do:** Đảm bảo sự cân bằng hoàn hảo giữa hiệu suất (giảm 80% thời gian gõ code thô) và tính an toàn tuyệt đối của hệ thống y tế nhờ chốt chặn kiểm duyệt kỹ thuật của con người trước khi thực thi lệnh.
*   **Lý do không chọn mức khác:**
    *   *Rule:* Không giải quyết được các yêu cầu nghiên cứu linh hoạt, thay đổi liên tục của bác sĩ.
    *   *Agent:* Rủi ro về an toàn hệ thống database và bảo mật thông tin y tế là quá lớn, không thể tự động hóa 100% không có sự giám sát của IT.

---

## Problem Statement v1

| Trường dữ liệu (Field) | Nội dung chi tiết |
|---|---|
| **Actor** | Lập trình viên phòng CNTT (vận hành dữ liệu) và Bác sĩ/Dược sĩ đang làm nghiên cứu khoa học tại viện. |
| **Workflow** | Nhập yêu cầu lâm sàng -> AI dịch thô và sinh SQL nháp -> IT review, sửa logic & tối ưu -> IT chạy thử nghiệm trên DB read-only -> IT đối soát mẫu -> Xuất file Excel gửi bác sĩ. |
| **Bottleneck** | Khâu viết SQL thô và tối ưu hóa truy vấn trên cơ sở dữ liệu y tế cực kỳ khổng lồ. |
| **Impact** | * IT mất nhiều giờ viết code thô tẻ nhạt mỗi tuần.<br>* Bác sĩ chờ đợi dữ liệu lâu làm chậm tiến độ nghiên cứu.<br>* Rủi ro treo hệ thống DB y tế đang chạy thực tế. |
| **Success Metric** | * Giảm thời gian xử lý yêu cầu từ **90 phút xuống dưới 20 phút**.<br>* **0% sự cố** đơ/treo DB do truy vấn nghiên cứu khoa học.<br>* Bác sĩ nhận dữ liệu trong vòng **24 giờ**. |
| **Boundary (AI không được làm gì)** | * AI **không được phép kết nối trực tiếp** với DB production đang chạy thật.<br>* AI **không được xem dữ liệu thật** định danh bệnh nhân.<br>* AI **không tự động gửi file** kết quả cho bác sĩ mà không qua IT duyệt. |
| **AI Intervention Point (Điểm AI can thiệp)** | AI can thiệp ngay sau khi tiếp nhận yêu cầu để tự động đối chiếu Metadata Schema DDL và sinh câu lệnh SQL nháp kèm Explain Plan. |
| **Mức giải pháp lựa chọn** | **Workflow** (Huấn luyện Text-to-SQL offline kết hợp Lập trình viên kiểm duyệt). |
| **Rủi ro & Quy trình người thật kiểm tra** | * *Rủi ro:* AI sinh sai tên bảng/trường (hallucination) hoặc sinh câu lệnh không tối ưu gây full-table scan.<br>* *Quy trình kiểm tra:* Lập trình viên bắt buộc phải chạy thử câu lệnh trên DB replica/read-only; rà soát Explain Plan để đảm bảo không bị slow query; đối soát ngẫu nhiên 5-10 dòng kết quả với bệnh án gốc để xác nhận tính chính xác logic y khoa. |

---

## Final decision

*   **Decision:** `Go với scope nhỏ`
*   **Exit / rollback:**
    *   AI liên tục sinh sai cấu trúc bảng (>50% số câu lệnh bị lỗi cú pháp nặng) sau 2 tuần hiệu chỉnh; hoặc phát hiện bất kỳ dấu hiệu truy vấn chậm/nghẽn hiệu năng trên DB replica.
    *   Phương án thay thế: Quay lại quy trình viết SQL thủ công truyền thống và sử dụng các template SQL/dashboard có sẵn để hỗ trợ bác sĩ.
*   **Decision rationale:**
    Bài toán có nỗi đau thật, workflow rất rõ ràng. Có sẵn giải pháp mã nguồn mở bảo mật chạy offline nội bộ (**Vanna.ai**) giúp triệt tiêu hoàn toàn rủi ro rò rỉ dữ liệu y tế, kiểm soát rủi ro hiệu năng cực tốt nhờ cơ chế chốt chặn con người kiểm duyệt kỹ thuật (`Human-in-the-loop`).

### Kế hoạch thử nghiệm nhỏ nhất (Pilot Plan)
*   **Dữ liệu mẫu sử dụng:** Metadata cấu trúc bảng DDL của 50 bảng dữ liệu chính trong phân hệ HIS/EMR và tập câu hỏi kèm SQL query mẫu của 10 đề tài nghiên cứu đã hoàn thành trong năm qua để huấn luyện AI.
*   **Quy trình chạy thử nghiệm:**
    1. IT cài đặt Vanna.ai cục bộ (chạy offline nội bộ).
    2. Nạp schema metadata vào hệ thống (tuyệt đối không nạp dữ liệu bệnh nhân).
    3. Chạy thử nghiệm dịch 10 yêu cầu nghiên cứu cũ sang SQL.
    4. IT đo lường tỷ lệ câu lệnh SQL sinh ra chạy được ngay và thời gian IT cần để sửa lại logic.
*   **Tiêu chí đánh giá pilot:** AI sinh đúng cú pháp SQL >70% ở lần đầu tiên; tổng thời gian IT xử lý yêu cầu thô giảm xuống dưới 10 phút.
