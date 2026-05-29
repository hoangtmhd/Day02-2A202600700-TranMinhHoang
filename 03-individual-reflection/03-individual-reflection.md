# 03 — Individual Reflection

**Vai trò trong nhóm:** Lập trình viên / Chuyên viên kỹ thuật (Đóng góp chính về tư duy bảo mật thông tin, kiến trúc SQL và an toàn hệ thống database).

---

## Đóng góp của tôi trong nhóm
Tự ghi nhận và đánh giá trung thực vai trò, đóng góp của bản thân vào thành quả chung của nhóm:

| Hoạt động soạn thảo trong nhóm | Chi tiết phần việc tôi đã làm | Kết quả / Ảnh hưởng đến quyết định của nhóm |
|---|---|---|
| **Hội tụ & Thảo luận chung (Mục 1)** | * Pitch 3 ý tưởng cá nhân và cùng cả nhóm thảo luận phân cụm 14 candidates.<br>* Đồng thuận chọn bài toán Trích xuất dữ liệu lâm sàng. | Giúp nhóm nhanh chóng đạt đồng thuận và chọn được đề tài có tính thử thách nghiệp vụ cao. |
| **Soạn thảo Problem Statement v1 (Mục 7)** | * Phụ trách viết trường **Boundary (Ranh giới)** và **Rủi ro & Quy trình kiểm tra**.<br>* Thiết kế ranh giới kiểm soát `Human Boundary` (cấm AI kết nối DB thật, cấm nạp thông tin bệnh nhân nhạy cảm). | Giúp nhóm thiết lập được hệ thống rào cản kỹ thuật an toàn, bảo vệ hiệu năng DB của bệnh viện và tuân thủ Luật An toàn thông tin mạng. |
| **Soạn thảo Kế hoạch Rollback (Mục 8.2)** | * Thiết kế điều kiện kích hoạt Rollback (nếu AI lỗi >50% sau 2 tuần) và phương án hoàn trả thủ công truyền thống. | Đảm bảo dự án của nhóm luôn có phương án phòng hờ an toàn khi AI thất bại. |
| **Hỗ trợ hoàn thiện tài liệu nhóm** | * Góp ý phản biện chéo phần Quick Validation và Research giải pháp do các thành viên khác phụ trách soạn thảo. | Tăng tính liên kết logic, giúp bản nộp nhóm thống nhất từ đầu đến cuối. |

---

## Bảng dùng AI trong reflection
Đánh giá trung thực và phản tư về cách tương tác với AI xuyên suốt các phase:

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi sửa lại bằng nhận định của mình thế nào? |
|---|---|---|---|---|
| **Scan cá nhân** | Gợi ý thêm các vấn đề thực tế theo lăng kính CNTT y tế. | Giúp nhớ ra các tác vụ như đối soát BHYT, đọc tài liệu API đối tác. | Gợi ý một số ý tưởng quá rộng mang tính "trợ lý AI vạn năng" không có workflow cụ thể. | Lọc bỏ toàn bộ các ý tưởng chung chung, chỉ giữ lại các tác vụ có workflow thật. |
| **Problem Card** | Phản biện Problem Card và workflow trước/sau để tìm lỗ hổng logic. | Chỉ ra các success metric còn mơ hồ (như "nhanh hơn") và rủi ro deadlock DB. | Đề xuất giải pháp tích hợp tự động hóa quá sâu (Agent) ngay từ đầu. | Giới hạn ranh giới an toàn (`Human Boundary`), hạ mức giải pháp xuống Workflow có IT duyệt. |
| **Workflow nhóm** | Chuyển đổi mô tả luồng công việc thành sơ đồ text/Mermaid. | Hỗ trợ vẽ nhanh và định dạng sơ đồ trực quan, tiết kiệm thời gian. | AI gộp chung bước viết SQL và chạy SQL làm một, bỏ qua khâu kiểm tra Explain Plan. | Tách rõ bước Vanna.ai sinh code nháp và bước IT rà soát Explain Plan trên DB replica trước khi thực thi. |
| **Research giải pháp** | Tìm kiếm thông tin về các framework Text-to-SQL bảo mật. | Gợi ý framework Vanna.ai và mô hình Azure OpenAI HIPAA-compliant. | Đưa ra một số số liệu quảng cáo thương mại chưa qua kiểm chứng về thời gian tiết kiệm. | Chỉ trích dẫn các tính năng kỹ thuật và tài liệu chính thức, không dùng số liệu quảng cáo không xác thực. |
| **AI Decision (R/W/A)** | Phản biện ma trận quyết định chọn Rule / Workflow / Agent. | Đặt ra các câu hỏi sắc bén về rủi ro bảo mật dữ liệu y tế nhạy cảm (PII). | Luôn hướng tới việc chọn mô hình Agent phức tạp để giải quyết toàn bộ quy trình. | Phản biện ngược lại AI, kiên quyết chọn mức Workflow để giữ con người ở vị trí kiểm soát an toàn. |

---

## Bài học của tôi
Phần suy nghĩ, cảm nhận và đúc kết cá nhân sau buổi lab:

*   **Tôi học được gì khi nghe top 3 problems của các bạn khác?**
    *   *Trả lời:* Các thành viên trong nhóm đến từ nhiều bối cảnh khác nhau (trường học, quản lý bệnh viện) nên góc nhìn của các bạn rất rộng và mới mẻ đối với tôi. Tôi học được rằng một vấn đề có vẻ rất phức tạp đối với người này nhưng lại có thể giải quyết nhanh bằng công nghệ đơn giản đối với người khác. Ví dụ, bài toán *"Tân sinh viên điền lặp lại form"* ban đầu nghe có vẻ rất phiền toái, nhưng thực chất chỉ cần chuẩn hóa cơ sở dữ liệu (`Rule/Database fix`) là giải quyết được 90%, chưa cần dùng đến AI. Bài học rút ra là phải luôn phân tích kỹ bản chất workflow trước khi nghĩ đến các giải pháp công nghệ phức tạp.
*   **Nhóm có lúc nào bị solution-first (nghĩ về giải pháp AI trước khi hiểu rõ vấn đề) không?**
    *   *Trả lời:* Có, nhóm từng bị solution-first khi thảo luận về bài toán *"Tân sinh viên hỏi lặp lại câu hỏi sinh hoạt"*. Ý kiến ban đầu của đa số thành viên là *"Xây dựng ngay một AI Agent thật thông minh để tự động chat giải đáp trên Zalo/Discord"*. Tuy nhiên, sau khi ngồi vẽ lại workflow và làm rõ điểm nghẽn, nhóm nhận ra vấn đề cốt lõi là tài liệu Handbook bản in/PDF bị tĩnh và thiếu cập nhật. Việc sử dụng một giải pháp Workflow đơn giản (AI hỗ trợ đọc tài liệu và trích xuất câu trả lời nháp) kết hợp cập nhật tài liệu định kỳ là đã đủ giải quyết, không cần đến một Agent tự động quá phức tạp và tiềm ẩn nhiều rủi ro trả lời sai quy chế.
*   **Tôi có thay đổi ý kiến sau khi bị các thành viên khác challenge (phản biện) không?**
    *   *Trả lời:* Có. Mặc dù ở bản scan cá nhân tôi đã xác định giải pháp ở mức Workflow và cần có con người kiểm duyệt, nhưng ban đầu tôi vẫn có xu hướng muốn sử dụng các API cloud trực tuyến của OpenAI/Gemini để dịch truy vấn cho nhanh và tối ưu. Tuy nhiên, các thành viên khác trong nhóm đã challenge tôi rất mạnh về Luật An toàn thông tin mạng trong y tế và rủi ro rò rỉ dữ liệu nhạy cảm của bệnh nhân ra bên ngoài. Nhờ những phản biện rất xác đáng đó, tôi đã thắt chặt ranh giới an toàn (`Human Boundary`) trong bản thiết kế của nhóm: kiên quyết đề xuất kiến trúc tự chạy offline nội bộ (như Vanna.ai), chỉ nạp Schema Metadata DDL đã được làm sạch hoàn toàn thông tin nhạy cảm và bắt buộc phải rà soát thủ công Explain Plan trước khi chạy thực tế trên cơ sở dữ liệu read-only.
*   **Tôi đóng góp gì thật sự vào artifact cuối cùng của nhóm?**
    *   *Trả lời:* Đóng góp lớn nhất của tôi là giữ cho nhóm đi đúng hướng và thực tế về mặt kỹ thuật. Nhờ kinh nghiệm làm việc với database lớn và các quy định bảo mật, tôi đã đóng góp chính vào việc thiết kế *"Ranh giới kiểm soát của con người" (Human Boundary)* và kế hoạch phòng hờ rút lui (`Rollback Plan`) cho giải pháp của nhóm. Tôi cũng giúp nhóm phân biệt rõ ràng giữa các phần việc nào nên làm bằng Rule/Tự động hóa thông thường (như trích xuất báo cáo tổng quan) và phần nào thực sự cần AI (dịch ngôn ngữ lâm sàng y tế sang cấu trúc SQL).
*   **Điều khó nhất khi viết Problem Statement là gì?**
    *   *Trả lời:* Điều khó nhất là định nghĩa trường **Success Metric (Thước đo thành công)** và **Boundary (Ranh giới)** một cách cụ thể, định lượng được chứ không chỉ viết chung chung là "giúp bác sĩ lấy dữ liệu nhanh hơn". Nhóm đã phải tranh luận rất nhiều để đưa ra baseline thời gian thực tế (90 phút thủ công trước đây và kỳ vọng 18 phút sau khi có AI) và ranh giới cụ thể là AI chỉ được phép đọc cấu trúc Metadata bảng chứ không được đọc dữ liệu thật của bệnh nhân để đảm bảo an toàn tuyệt đối.
*   **Nếu làm lại lab này từ đầu, tôi sẽ challenge nhóm mạnh hơn ở điểm nào để bài làm tốt hơn?**
    *   *Trả lời:* Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở khâu **Quick Validation**. Do thời gian trong buổi lab hạn chế, nhóm chỉ mới phỏng vấn và khảo sát được một số lượng mẫu nhỏ (15 người). Tôi muốn nhóm thiết kế một bảng khảo sát chi tiết hơn để gửi đến nhiều bác sĩ và điều dưỡng ở các khoa lâm sàng khác nhau nhằm thu thập dữ liệu baseline thời gian thực sự chính xác, từ đó làm cho success metric của Problem Statement thuyết phục hơn nữa.
