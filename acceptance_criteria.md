# Acceptance Criteria: Sales Insight Copilot

**Version:** 1.0  
**Phase:** Discovery (Week 1)  

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
