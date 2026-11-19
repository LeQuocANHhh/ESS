# KPI Definitions: Sales Insight Copilot

**Version:** 1.1  
**Phase:** Discovery (Week 1 — Updated)  

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

---

## 4. Regional & Category Analytics KPIs (Chỉ số Phân tích Khu vực & Danh mục)

### 4.1. Tỷ trọng Doanh thu theo Khu vực (Revenue Share by Region)
* **Ý nghĩa:** Phần trăm doanh thu mà mỗi khu vực địa lý đóng góp vào tổng doanh thu — giúp nhận diện thị trường trọng điểm.
* **Công thức tính:**
  $$\text{Region Revenue Share}_r = \frac{\text{Revenue of Region } r}{\text{Total Revenue}} \times 100\%$$
* **Nguồn dữ liệu:** Cột `Region` và `Revenue` trong file Excel/CSV.

### 4.2. Tỷ trọng Doanh thu theo Danh mục (Revenue Share by Category)
* **Ý nghĩa:** Phần trăm doanh thu mà mỗi danh mục sản phẩm đóng góp — giúp xác định nhóm hàng chủ lực.
* **Công thức tính:**
  $$\text{Category Revenue Share}_c = \frac{\text{Revenue of Category } c}{\text{Total Revenue}} \times 100\%$$
* **Mục tiêu:** Top 3 danh mục phải lý giải được tối thiểu 60% tổng doanh thu.

---

## 5. RAG System KPIs (Chỉ số Chất lượng Hệ thống RAG)

| Chỉ số (KPI) | Mục tiêu (Target) | Phương pháp đo lường |
| :--- | :--- | :--- |
| **Tỷ lệ truy xuất chính xác (RAG Retrieval Precision)** | $\ge 90\%$ | Tỷ lệ câu trả lời RAG có trích dẫn đúng nguồn tài liệu gốc trên tổng số câu hỏi kiểm thử. |
| **Tỷ lệ từ chối hallucination (Hallucination Rejection Rate)** | $100\%$ | AI phải từ chối (không bịa câu trả lời) trong mọi trường hợp không tìm thấy thông tin trong tài liệu. |
| **Thời gian phản hồi RAG (RAG Response Latency)** | $\le 5\text{s}$ | Thời gian từ khi nhận câu hỏi đến khi trả về kết quả có trích dẫn. |
| **Thời gian lập chỉ mục tài liệu (Document Indexing Time)** | $\le 60\text{s}$ cho file $< 10\text{MB}$ | Thời gian từ lúc upload đến khi tài liệu sẵn sàng để tra cứu. |

---

## 6. AI Tool Calling & RBAC KPIs (Chỉ số Chất lượng Tool Calling & Phân quyền)

| Chỉ số (KPI) | Mục tiêu (Target) | Phương pháp đo lường |
| :--- | :--- | :--- |
| **Tỷ lệ gọi công cụ đúng (Tool Selection Accuracy)** | $\ge 95\%$ | Tỷ lệ AI chọn đúng công cụ phù hợp với ý định câu hỏi của người dùng. |
| **Tỷ lệ chặn truy cập trái quyền (RBAC Block Rate)** | $100\%$ | Mọi lời gọi công cụ vượt quyền của vai trò phải bị chặn — không có ngoại lệ. |
| **Tỷ lệ ghi audit log đầy đủ (Audit Log Coverage)** | $100\%$ | Mọi lần AI thực thi công cụ đều phải có bản ghi nhật ký đầy đủ (thời gian, người dùng, công cụ, tham số). |
