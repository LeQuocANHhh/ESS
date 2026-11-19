# User Stories: Sales Insight Copilot

**Version:** 1.1  
**Phase:** Discovery (Week 1 — Updated)  

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

---

## Epic 5: Advanced Analytics — Region & Category Filters (Phân tích theo Khu vực & Danh mục)

* **US-11: Xem biểu đồ theo Khu vực địa lý (Region)**  
  * **As a** Chủ doanh nghiệp / Quản lý bán hàng,  
  * **I want to** lọc và xem biểu đồ doanh thu theo từng khu vực địa lý (ví dụ: Miền Bắc, Miền Trung, Miền Nam hoặc từng tỉnh/thành phố),  
  * **So that** tôi xác định được thị trường trọng điểm và phân bổ nguồn lực kinh doanh hiệu quả hơn.

* **US-12: Xem biểu đồ theo Danh mục sản phẩm (Category)**  
  * **As a** Quản lý bán hàng,  
  * **I want to** lọc và xem thống kê doanh thu, lợi nhuận theo từng danh mục sản phẩm (Category),  
  * **So that** tôi biết nhóm hàng nào đang tăng trưởng và nhóm nào cần cải thiện chiến lược bán.

---

## Epic 6: AI Trend Explanation (AI Giải thích Xu hướng)

* **US-13: AI chủ động giải thích xu hướng dữ liệu**  
  * **As a** Chủ doanh nghiệp,  
  * **I want** AI Copilot tự động thêm đoạn văn bản phân tích (insight) sau khi hiển thị biểu đồ hoặc số liệu,  
  * **So that** tôi hiểu được nguyên nhân tăng/giảm, so sánh với kỳ trước, và nhận diện điểm bất thường (anomaly) mà không cần tự đọc dữ liệu thô.

---

## Epic 7: Business Document Retrieval — RAG (Tra cứu Tài liệu Nghiệp vụ)

* **US-14: Tra cứu tài liệu nội bộ bằng câu hỏi ngôn ngữ tự nhiên**  
  * **As a** Nhân viên kinh doanh / Kế toán,  
  * **I want to** đặt câu hỏi về chính sách và quy định nội bộ cho AI Copilot (ví dụ: *"Chính sách chiết khấu cho đơn hàng trên 10 triệu là bao nhiêu?"*),  
  * **So that** tôi nhận được câu trả lời chính xác, có trích dẫn nguồn tài liệu, mà không cần tìm kiếm thủ công trong hàng trăm file.

* **US-15: Nạp tài liệu nghiệp vụ vào hệ thống RAG**  
  * **As a** Quản trị viên hệ thống,  
  * **I want to** tải lên các file tài liệu nội bộ (`.pdf`, `.docx`, `.txt`) để hệ thống RAG lập chỉ mục và sẵn sàng tra cứu,  
  * **So that** kho kiến thức nghiệp vụ luôn được cập nhật và phản ánh đúng các chính sách mới nhất.

---

## Epic 8: AI Tool Calling with RBAC (AI Gọi Công cụ Phân tích có Phân quyền)

* **US-16: AI tự động gọi công cụ phân tích dữ liệu khi cần**  
  * **As a** Chủ doanh nghiệp,  
  * **I want** AI Copilot tự động thực thi các hàm phân tích (tổng doanh thu, top sản phẩm, xuất báo cáo) khi tôi đặt câu hỏi phù hợp,  
  * **So that** tôi nhận được kết quả tính toán chính xác từ dữ liệu thực, không chỉ là câu trả lời ước tính.

* **US-17: Giới hạn công cụ AI theo vai trò người dùng (RBAC)**  
  * **As a** Quản trị viên hệ thống,  
  * **I want** mỗi vai trò người dùng (Chủ doanh nghiệp, Kế toán) chỉ được phép yêu cầu AI gọi các công cụ phù hợp với quyền hạn của họ,  
  * **So that** dữ liệu gốc được bảo vệ, tránh rủi ro AI vô tình sửa hoặc xóa dữ liệu tài chính quan trọng.
