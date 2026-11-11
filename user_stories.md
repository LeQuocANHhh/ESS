# User Stories: Sales Insight Copilot

**Version:** 1.0  
**Phase:** Discovery (Week 1)  

---

## Epic 1: Data Management & Ingestion (Quản lý & Nạp dữ liệu)

* **US-01: Tải lên file dữ liệu thủ công**  
  * **As a** Chủ doanh nghiệp / Kế toán,  
  * **I want to** tải lên file Excel (`.xlsx`, `.xls`) hoặc `.csv` chứa lịch sử bán hàng qua giao diện,  
  * **So that** hệ thống cập nhật số liệu mới nhất vào cơ sở dữ liệu phân tích.

* **US-02: Tự động đồng bộ file định kỳ**  
  * **As a** Kế toán,  
  * **I want to** thiết lập lịch đồng bộ dữ liệu tự động từ thư mục/nguồn lưu trữ,  
  * **So that** dữ liệu luôn được làm mới mà không tốn công thao tác thủ công hàng ngày.

* **US-03: Kiểm tra tính hợp lệ của file (File Validation)**  
  * **As an** Hệ thống / Người dùng,  
  * **I want** nhận thông báo lỗi chi tiết khi file tải lên bị hỏng, sai định dạng hoặc thiếu các cột bắt buộc,  
  * **So that** dữ liệu bẩn không làm sai lệch các báo cáo tài chính.

---

## Epic 2: Financial & Cash Flow Monitoring (Giám sát Tài chính & Dòng tiền)

* **US-04: Giám sát dòng tiền và vốn lưu động**  
  * **As a** Chủ doanh nghiệp,  
  * **I want to** theo dõi biến động dòng tiền thu vào - chi ra và nguồn vốn hiện hữu theo thời gian thực,  
  * **So that** tôi chủ động điều phối vốn và tránh rủi ro hụt dòng tiền thanh toán.

* **US-05: Đánh giá tăng trưởng định kỳ (MoM)**  
  * **As a** Chủ doanh nghiệp,  
  * **I want to** so sánh doanh thu và chi phí của tháng hiện tại với tháng trước,  
  * **So that** tôi biết doanh nghiệp đang tăng trưởng hay sụt giảm để kịp thời điều chỉnh kế hoạch.

---

## Epic 3: Sales Intelligence & Inventory Tracking (Thống kê Bán hàng & Tồn kho)

* **US-06: Xem Dashboard chỉ số KPI**  
  * **As a** Quản lý / Chủ doanh nghiệp,  
  * **I want to** xem màn hình tổng quan hiển thị các chỉ số cốt lõi (Doanh thu, Lợi nhuận gộp, Số đơn hàng),  
  * **So that** tôi nắm bắt tức thì hiệu quả kinh doanh mà không cần đọc báo cáo chi tiết.

* **US-07: Thống kê sản phẩm chủ lực (Pareto 80/20)**  
  * **As a** Quản lý bán hàng,  
  * **I want to** xem danh sách Top sản phẩm đóng góp phần lớn doanh thu,  
  * **So that** tôi tối ưu hóa danh mục sản phẩm và chiến lược tiếp thị.

* **US-08: Cảnh báo tồn kho thấp**  
  * **As a** Chủ doanh nghiệp,  
  * **I want to** nhận được cảnh báo trực quan khi số lượng tồn kho của một mặt hàng giảm xuống dưới ngưỡng an toàn,  
  * **So that** tôi chủ động lên kế hoạch nhập hàng, tránh đứt gãy kinh doanh.

---

## Epic 4: AI Copilot Assistant (Trợ lý ảo phân tích)

* **US-09: Truy vấn số liệu bằng ngôn ngữ tự nhiên**  
  * **As a** Chủ doanh nghiệp,  
  * **I want to** đặt câu hỏi cho Chatbot (ví dụ: *"Doanh thu tuần qua thế nào?"* hoặc *"Mặt hàng nào bán chạy nhất tháng 10?"*),  
  * **So that** tôi nhận được câu trả lời chính xác ngay lập tức mà không cần tự lọc bảng số liệu.

* **US-10: Tự động vẽ biểu đồ từ câu hỏi**  
  * **As a** Người dùng,  
  * **I want** Chatbot tự động tạo biểu đồ trực quan (biểu đồ đường, biểu đồ cột) kèm theo câu trả lời,  
  * **So that** tôi dễ dàng hình dung xu hướng dữ liệu một cách trực quan.
