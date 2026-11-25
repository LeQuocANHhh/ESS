# Acceptance Criteria: Sales Insight Copilot

**Version:** 1.1  
**Phase:** Discovery (Week 1 — Updated)  

---

## 1. Feature: Data Ingestion (US-01, US-02, US-03)

### AC-01: Kiểm tra định dạng và cấu trúc file (File Validation)
* **Given** người dùng chọn tải lên một file dữ liệu,
* **When** file có phần mở rộng `.xlsx`, `.xls` hoặc `.csv` và chứa đầy đủ các cột bắt buộc (`Transaction_Date`, `Product_ID`, `Quantity`, `Unit_Price`, `Revenue`),
* **Then** hệ thống chấp nhận file, hiển thị thông báo "Tải lên thành công" và nạp dữ liệu vào bộ nhớ xử lý.
* **When** file thiếu ít nhất một cột bắt buộc hoặc có định dạng không được hỗ trợ (ví dụ `.pdf`, `.json`),
* **Then** hệ thống từ chối file, hiển thị thông báo lỗi cụ thể (ví dụ: *"Thiếu cột bắt buộc: Transaction_Date"*), và giữ nguyên trạng thái dữ liệu cũ.

### AC-02: Đồng bộ định kỳ (Periodic Sync)
* **Given** cấu hình đồng bộ tự động được bật,
* **When** đến mốc thời gian quy định,
* **Then** tiến trình ngầm (background job) tự động đọc nguồn file mới nhất và cập nhật database mà không gây gián đoạn hay đóng băng màn hình của người dùng.

---

## 2. Feature: Financial & Sales Analytics Dashboard (US-04, US-05, US-06, US-07)

### AC-03: Cập nhật chỉ số KPI thời gian thực
* **Given** dữ liệu mới vừa được nạp thành công,
* **When** người dùng mở màn hình Dashboard,
* **Then** các thẻ KPI (Tổng doanh thu, Lợi nhuận gộp, Tổng số đơn) phải được cập nhật lại theo số liệu mới nhất trong vòng dưới 2 giây.

### AC-04: Thống kê Top sản phẩm & Xu hướng thời gian
* **Given** tập dữ liệu bán hàng đã nạp,
* **When** người dùng chọn khoảng thời gian (Ngày / Tuần / Tháng / Quý),
* **Then** biểu đồ đường xu hướng doanh thu và bảng xếp hạng Top 5 sản phẩm có doanh thu cao nhất phải hiển thị chính xác theo khoảng thời gian đã lọc.

---

## 3. Feature: Inventory Tracking (US-08)

### AC-05: Khấu trừ tồn kho & Cảnh báo ngưỡng an toàn
* **Given** mỗi sản phẩm có số lượng tồn kho ban đầu và ngưỡng tối thiểu (ví dụ: 10 đơn vị),
* **When** một giao dịch bán phát sinh với số lượng $N$,
* **Then** hệ thống tự động trừ $N$ vào tồn kho hiện tại:
  * Nếu tồn kho còn lại $\le$ ngưỡng tối thiểu: Đánh dấu trạng thái cảnh báo màu đỏ/vàng trên màn hình.
  * Nếu số lượng bán vượt quá số lượng tồn kho ($N > \text{Stock}$): Hệ thống vẫn ghi nhận doanh thu nhưng gắn cờ cảnh báo *"Tồn kho âm - cần kiểm tra nhập kho"*.

---

## 4. Feature: AI Copilot Chatbot (US-09, US-10)

### AC-06: Xử lý ngôn ngữ tự nhiên & Tính chính xác số liệu
* **Given** người dùng gửi câu hỏi tra cứu dữ liệu (ví dụ: *"Tổng doanh thu tháng này là bao nhiêu?"*),
* **When** Chatbot xử lý câu hỏi,
* **Then** câu trả lời phải trích xuất chính xác con số tính toán từ dữ liệu nội bộ (tuyệt đối không suy diễn số liệu ngoài dữ liệu), phản hồi hoàn tất trong vòng $\le 3$ giây.

### AC-07: Tạo biểu đồ trực quan tự động
* **Given** người dùng hỏi một câu hỏi mang tính so sánh hoặc xu hướng (ví dụ: *"Vẽ biểu đồ doanh thu theo tuần"*),
* **When** Chatbot phản hồi,
* **Then** bên dưới đoạn văn bản giải thích phải tự động hiển thị một biểu đồ (Bar Chart hoặc Line Chart) tương ứng với dữ liệu được trích xuất.

---

## 5. Feature: Regional & Category Analytics (US-11, US-12)

### AC-08: Lọc biểu đồ theo Khu vực (Region)
* **Given** dữ liệu đầu vào có cột `Region` hoặc tương đương,
* **When** người dùng chọn một hoặc nhiều khu vực từ bộ lọc (filter) trên Dashboard,
* **Then** tất cả biểu đồ và chỉ số KPI phải cập nhật lại chỉ hiển thị dữ liệu thuộc (các) khu vực đã chọn trong vòng dưới 2 giây.
* **When** file dữ liệu không có cột `Region`,
* **Then** hệ thống ẩn bộ lọc khu vực và hiển thị thông báo: *"Dữ liệu không có thông tin khu vực."*

### AC-09: Lọc biểu đồ theo Danh mục sản phẩm (Category)
* **Given** dữ liệu đầu vào có cột `Category` hoặc tương đương,
* **When** người dùng chọn một hoặc nhiều danh mục từ bộ lọc,
* **Then** biểu đồ Top sản phẩm và bảng thống kê phải lọc và hiển thị chỉ dữ liệu thuộc danh mục đã chọn, với các số liệu tổng hợp được tính lại chính xác.

---

## 6. Feature: AI Trend Explanation (US-13)

### AC-10: Giải thích xu hướng tự động sau mỗi phản hồi biểu đồ
* **Given** AI Copilot vừa tạo một biểu đồ hoặc bảng số liệu theo yêu cầu người dùng,
* **When** phản hồi hoàn tất,
* **Then** AI **tự động** hiển thị thêm một đoạn phân tích (tối đa 5 câu) bao gồm ít nhất 2 trong 3 yếu tố sau:
  1. Nhận xét về xu hướng (tăng/giảm) so với kỳ trước.
  2. Xác định điểm bất thường (anomaly) nếu có.
  3. Đề xuất 1 hành động cụ thể dựa trên xu hướng quan sát được.
* **Then** đoạn phân tích phải dựa hoàn toàn vào dữ liệu đã nạp — không được suy diễn số liệu ngoài dữ liệu.

---

## 7. Feature: RAG Business Document Retrieval (US-14, US-15)

### AC-11: Tra cứu tài liệu nghiệp vụ bằng ngôn ngữ tự nhiên
* **Given** ít nhất một tài liệu nghiệp vụ đã được nạp vào hệ thống RAG,
* **When** người dùng đặt câu hỏi liên quan đến nội dung tài liệu (ví dụ: *"Chính sách hoàn hàng là gì?"*),
* **Then** hệ thống phải:
  1. Trả lời bằng nội dung được trích xuất trực tiếp từ tài liệu.
  2. Kèm theo **trích dẫn nguồn** (tên tài liệu + số trang/đoạn tương ứng).
  3. Phản hồi hoàn tất trong vòng dưới 5 giây.
* **When** không tìm thấy thông tin liên quan trong tài liệu,
* **Then** AI phải trả lời: *"Không tìm thấy thông tin liên quan trong tài liệu nội bộ."* — tuyệt đối không tự bịa câu trả lời.

### AC-12: Nạp tài liệu nghiệp vụ vào hệ thống RAG
* **Given** quản trị viên tải lên file tài liệu định dạng `.pdf`, `.docx` hoặc `.txt`,
* **When** quá trình xử lý hoàn tất,
* **Then** tài liệu được lập chỉ mục (indexed/embedded) và sẵn sàng để tra cứu trong vòng dưới 60 giây.
* **When** file bị hỏng hoặc không thể trích xuất văn bản (ví dụ: PDF scan ảnh không có OCR),
* **Then** hệ thống thông báo lỗi rõ ràng và không nạp file đó vào chỉ mục.

---

## 8. Feature: AI Tool Calling with RBAC (US-16, US-17)

### AC-13: AI thực thi công cụ phân tích dữ liệu chính xác
* **Given** người dùng đặt câu hỏi kích hoạt Tool Calling (ví dụ: *"Tổng doanh thu tháng 10 là bao nhiêu?"*),
* **When** AI xác định cần gọi công cụ để trả lời,
* **Then** AI phải gọi đúng công cụ phù hợp, truyền đúng tham số (khoảng thời gian, bộ lọc), và hiển thị kết quả tính toán từ dữ liệu thực — không ước tính.
* **Then** mỗi lần gọi công cụ phải được ghi vào **audit log** (thời gian, người dùng, tên công cụ, tham số).

### AC-14: Phân quyền công cụ theo vai trò (RBAC)
* **Given** người dùng đăng nhập với vai trò **Kế toán**,
* **When** AI cố gắng gọi công cụ có quyền ghi/xóa dữ liệu (ví dụ: `delete_record`, `modify_transaction`),
* **Then** hệ thống phải chặn lời gọi công cụ đó, trả về thông báo lỗi phân quyền rõ ràng, và **không thực thi** hành động.
* **Given** người dùng đăng nhập với vai trò **Chủ doanh nghiệp**,
* **When** AI gọi bất kỳ công cụ nào trong danh sách đã được phê duyệt,
* **Then** hệ thống thực thi bình thường và trả về kết quả.
