# Project Requirements Document: Sales Insight Copilot

**Version:** 1.1  
**Phase:** Discovery & Requirements Engineering (Week 1 — Updated)  
**Target Platform:** Web Application  

---

## 1. Executive Summary & Business Problem (Tổng quan dự án)
Hộ kinh doanh và các doanh nghiệp nhỏ thường gặp khó khăn trong việc bám sát dòng tiền, cơ cấu nguồn vốn và đánh giá hiệu quả bán hàng do dữ liệu phân tán trong các file bảng tính rời rạc. 

**Sales Insight Copilot** là ứng dụng web phân tích số liệu kinh doanh thông minh, cho phép người dùng nạp dữ liệu từ file Excel/CSV, tự động trích xuất các chỉ số tài chính - tồn kho cốt lõi, và tích hợp trợ lý ảo (AI Copilot) hỗ trợ tra cứu số liệu cũng như trực quan hóa biểu đồ qua ngôn ngữ tự nhiên.

---

## 2. Target Audience & Stakeholders (Đối tượng người dùng)
* **Chủ doanh nghiệp / Quản lý (Business Owner / Manager):** Cần nắm bắt nhanh bức tranh tài chính tổng quát, dòng tiền, sản phẩm chủ lực và các cảnh báo rủi ro (tồn kho thấp) thông qua giao diện trực quan, dễ thao tác mà không đòi hỏi chuyên môn kế toán sâu.
* **Kế toán (Accountant):** Cần công cụ nạp dữ liệu linh hoạt, xử lý dữ liệu chuẩn xác, theo dõi biến động thu - chi và đối chiếu số liệu định kỳ.

---

## 3. Scope of Work (Phạm vi dự án)

### 3.1. In-Scope (Nội dung chính thức trong phạm vi)
#### A. Quản lý & Nạp dữ liệu (Data Ingestion)
* **[Xác nhận]** Hỗ trợ nhập dữ liệu từ file định dạng Microsoft Excel (`.xlsx`, `.xls`) và `.csv`.
* **[Xác nhận]** Cung cấp 2 cơ chế nạp dữ liệu:
  1. Tải lên thủ công (Manual Upload) qua giao diện.
  2. Đồng bộ/cập nhật định kỳ tự động (Scheduled/Periodic Sync).
* **[Giả định kỹ thuật]** Kiểm tra tính hợp lệ của cấu trúc file (Schema Validation) trước khi nạp: Ngày giao dịch, Mã sản phẩm, Số lượng, Đơn giá/Thành tiền.

#### B. Phân tích Tài chính & Dòng tiền (Financial & Cash Flow Tracking)
* **[Xác nhận]** Theo dõi biến động dòng tiền (tiền vào - tiền ra) và tình trạng nguồn vốn lưu động.
* **[Đề xuất đã duyệt]** Phân tích xu hướng doanh thu theo thời gian (Ngày, Tuần, Tháng, Quý).
* **[Đề xuất đã duyệt]** Tính toán tỷ lệ tăng trưởng so với kỳ trước (Month-over-Month - MoM).

#### C. Thống kê Bán hàng & Tồn kho (Sales & Inventory Intelligence)
* **[Xác nhận]** Bảng điều khiển (Dashboard) hiển thị các chỉ số KPI doanh thu, lợi nhuận.
* **[Xác nhận]** Thống kê sản phẩm bán chạy nhất và xác định nguồn doanh thu lớn nhất (Nguyên lý Pareto 80/20).
* **[Đề xuất đã duyệt]** Quản lý mức tồn kho cơ bản: tự động trừ tồn kho theo số lượng bán và kích hoạt cảnh báo khi chạm ngưỡng tối thiểu.
* **[Bổ sung v1.1]** Biểu đồ phân tích đa chiều theo **Khu vực địa lý (Region)** và **Danh mục sản phẩm (Category)** — cho phép người dùng lọc và so sánh hiệu quả bán hàng theo từng vùng hoặc nhóm hàng cụ thể.

#### D. Trợ lý ảo (AI Copilot Chatbot)
* **[Xác nhận]** Chatbot hỗ trợ giải đáp thắc mắc về số liệu kinh doanh bằng ngôn ngữ tự nhiên.
* **[Xác nhận]** Khả năng tự động vẽ biểu đồ trực quan cơ bản (biểu đồ cột, biểu đồ đường) dựa trên kết quả truy vấn.
* **[Bổ sung v1.1]** AI chủ động **giải thích xu hướng** (Trend Explanation): sau khi hiển thị số liệu hoặc biểu đồ, AI tự động cung cấp đoạn văn bản phân tích ngắn giải thích nguyên nhân tăng/giảm, so sánh kỳ trước và đề xuất điểm cần chú ý.

#### E. Tra cứu Tài liệu Nghiệp vụ bằng RAG (Business Document Retrieval — RAG)
* **[Bổ sung v1.1]** Tích hợp cơ chế **RAG (Retrieval-Augmented Generation)** cho phép người dùng tra cứu thông tin từ các tài liệu nội bộ (quy định chiết khấu, chính sách bán hàng, hướng dẫn sản phẩm, hợp đồng) bằng câu hỏi ngôn ngữ tự nhiên.
* **[Bổ sung v1.1]** Hệ thống RAG sẽ trích xuất và trích dẫn chính xác đoạn văn bản nguồn từ tài liệu gốc khi trả lời, kèm theo tham chiếu (tên tài liệu, số trang).
* **[Giả định kỹ thuật]** Tài liệu nghiệp vụ được nạp dưới dạng file `.pdf`, `.docx` hoặc `.txt`; được vector hóa (embedding) và lưu vào Vector Database (ví dụ: ChromaDB, FAISS).

#### F. AI Tool Calling với Phân quyền (RBAC-restricted AI Tool Calling)
* **[Bổ sung v1.1]** AI Copilot có khả năng **chủ động gọi các công cụ phân tích dữ liệu** (Function Calling / Tool Use) thay vì chỉ trả lời bằng văn bản — ví dụ: gọi hàm tính tổng doanh thu, hàm lọc dữ liệu theo kỳ, hàm xuất báo cáo PDF.
* **[Bổ sung v1.1]** Áp dụng cơ chế **phân quyền dựa trên vai trò (RBAC — Role-Based Access Control)** để giới hạn công cụ AI được phép gọi:
  * **Chủ doanh nghiệp**: Có quyền gọi tất cả công cụ (đọc, xuất báo cáo, xem dự báo).
  * **Kế toán**: Chỉ được gọi công cụ đọc/truy vấn dữ liệu; không được phép gọi công cụ sửa/xóa dữ liệu gốc.
* **[Giả định kỹ thuật]** Danh sách công cụ cho phép được định nghĩa trong file cấu hình phân quyền; mọi lần gọi công cụ đều được ghi nhật ký (audit log).

---

### 3.2. Out-of-Scope (Ngoài phạm vi dự án - Tránh Scope Creep)
* Kết nối API trực tiếp theo thời gian thực với các hệ thống POS, ngân hàng hoặc phần mềm ERP chuyên dụng bên ngoài (chỉ tiếp nhận qua file Excel/CSV).
* Hỗ trợ thanh toán trực tuyến hoặc xử lý đa tiền tệ (Multi-currency).
* Tính năng tự động đặt hàng mua từ nhà cung cấp khi hết hàng (chỉ dừng ở mức cảnh báo tồn kho).
* AI Tool Calling với quyền **ghi/xóa** dữ liệu gốc (chỉ cho phép đọc và truy vấn đối với Kế toán).

---

## 4. Non-Functional Requirements (Yêu cầu phi chức năng)
1. **Tính khả dụng (Usability):** Giao diện tối giản, trực quan, thân thiện với người dùng không chuyên kỹ thuật.
2. **Độ chính xác (Data Integrity):** Tuyệt đối không làm tròn sai lệch dòng tiền; Chatbot chỉ trả lời dựa trên dữ liệu đã nạp (không bịa số liệu / hallucination).
3. **Hiệu năng (Performance):** 
   * Xử lý file dữ liệu dung lượng tiêu chuẩn (< 50MB) trong vòng dưới 5 giây.
   * Chatbot phản hồi câu hỏi và hiển thị biểu đồ trong vòng dưới 3 giây.
4. **Bảo mật (Security):** Dữ liệu tài chính của doanh nghiệp được lưu trữ cục bộ/phân quyền an toàn.
