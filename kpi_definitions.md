# KPI Definitions: Sales Insight Copilot

**Version:** 1.0  
**Phase:** Discovery (Week 1)  

Tài liệu này định nghĩa các chỉ số đo lường hiệu quả (Key Performance Indicators - KPIs) được hệ thống theo dõi và tính toán, chia thành **Chỉ số kinh doanh (Business KPIs)** và **Chỉ số chất lượng phần mềm (Engineering KPIs)**.

---

## 1. Business & Financial KPIs (Chỉ số Kinh doanh & Tài chính)

### 1.1. Tổng Doanh Thu (Total Revenue)
* **Ý nghĩa:** Tổng số tiền thu được từ việc bán sản phẩm/dịch vụ trong khoảng thời gian xác định.
* **Công thức tính:**  
  $$\text{Total Revenue} = \sum (\text{Quantity} \times \text{Unit Price})$$
* **Tần suất cập nhật:** Tức thì sau mỗi lần nạp/đồng bộ dữ liệu.
* **Nguồn dữ liệu:** Cột `Quantity` và `Unit_Price` trong file Excel/CSV.

### 1.2. Biên Lợi Nhuận Gộp (Gross Profit Margin)
* **Ý nghĩa:** Tỷ lệ phần trăm doanh thu còn lại sau khi trừ đi giá vốn hàng bán (Cost of Goods Sold - COGS), phản ánh hiệu quả sinh lời cốt lõi.
* **Công thức tính:**  
  $$\text{Gross Profit Margin} = \frac{\text{Total Revenue} - \text{COGS}}{\text{Total Revenue}} \times 100\%$$
* **Tần suất cập nhật:** Theo tháng hoặc theo kỳ báo cáo.

### 1.3. Biến Động Dòng Tiền Ròng (Net Cash Flow Variance)
* **Ý nghĩa:** Chênh lệch giữa tổng dòng tiền thu vào (Inflows) và tổng dòng tiền chi ra (Outflows) trong kỳ.
* **Công thức tính:**  
  $$\text{Net Cash Flow} = \sum \text{Cash Inflows} - \sum \text{Cash Outflows}$$
* **Ý nghĩa thực tiễn:** Giúp chủ doanh nghiệp biết dòng tiền khả dụng thực tế đang dương hay âm để chủ động thanh khoản.

---

## 2. Operational & Inventory KPIs (Chỉ số Vận hành & Tồn kho)

### 2.1. Tỷ trọng Sản phẩm Chủ lực (Top Revenue Contribution - Pareto 80/20)
* **Ý nghĩa:** Xác định nhóm sản phẩm đem lại tỷ trọng doanh thu cao nhất cho cửa hàng.
* **Công thức tính:**  
  $$\text{Product Revenue Share} = \frac{\text{Revenue of Product } i}{\text{Total Revenue}} \times 100\%$$
* **Ngưỡng theo dõi:** Nhận diện các mặt hàng thuộc nhóm tích lũy đạt 80% tổng doanh thu.

### 2.2. Số Lượng Cảnh Báo Tồn Kho (Low Stock Alert Count)
* **Ý nghĩa:** Số lượng mã hàng (SKU) có tồn kho hiện tại rơi xuống dưới ngưỡng an toàn ($\text{Current Stock} \le \text{Threshold}$).
* **Mục tiêu:** Càng thấp càng tốt (hạn chế tối đa đứt gãy nguồn cung).

---

## 3. Engineering & System KPIs (Chỉ số Chất lượng Phần mềm)

Đối với một kỹ sư phần mềm, việc xác định các KPI kỹ thuật giúp đánh giá hệ thống có đạt yêu cầu phi chức năng hay không:

| Chỉ số (KPI) | Mục tiêu (Target) | Phương pháp đo lường |
| :--- | :--- | :--- |
| **Độ chính xác Chatbot (Chatbot Accuracy)** | $\ge 95\%$ | Tỷ lệ câu trả lời trích xuất đúng số liệu từ cơ sở dữ liệu trên tổng số câu hỏi kiểm thử. |
| **Thời gian phản hồi AI (AI Response Latency)** | $\le 3\text{s}$ | Thời gian từ khi gửi prompt đến khi render xong văn bản + biểu đồ. |
| **Thời gian nạp dữ liệu (Ingestion Latency)** | $\le 5\text{s}$ cho file $< 50\text{MB}$ | Thời gian từ lúc nhận file đến khi hoàn tất validation và lưu trữ. |
| **Tỷ lệ lỗi nạp dữ liệu (Ingestion Failure Rate)** | $0\%$ trên file chuẩn | Không phát sinh ngoại lệ chưa xử lý (unhandled exception) với các file hợp lệ. |
