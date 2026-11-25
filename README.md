# Sales Insight Copilot (ESS)

**Sales Insight Copilot** là ứng dụng web phân tích số liệu kinh doanh thông minh dành cho hộ kinh doanh và doanh nghiệp nhỏ, giúp Chủ doanh nghiệp và Kế toán theo dõi sát sao dòng tiền, nguồn vốn, hiệu quả bán hàng, tồn kho và tương tác trực tiếp với dữ liệu qua trợ lý AI.

---

## 🎯 Mục tiêu & Tính năng cốt lõi

* **Quản lý & Nạp dữ liệu linh hoạt:** Hỗ trợ file Excel (`.xlsx`, `.xls`) và `.csv` qua cả tải lên thủ công và đồng bộ định kỳ tự động, kèm kiểm tra tính hợp lệ (Schema Validation).
* **Theo dõi Tài chính & Dòng tiền:** Giám sát biến động dòng tiền thu/chi, nguồn vốn lưu động, doanh thu và biên lợi nhuận gộp.
* **Thống kê & Biểu đồ đa chiều:** Xem biểu đồ trực quan theo ngày, tháng, khu vực (Region) và danh mục (Category); nhận diện sản phẩm chủ lực (Pareto 80/20) và cảnh báo tồn kho thấp.
* **AI Copilot & Giải thích xu hướng:** Đặt câu hỏi bằng ngôn ngữ tự nhiên để truy vấn số liệu, tự động vẽ biểu đồ cơ bản và giải thích xu hướng tăng/giảm.
* **Tra cứu Tài liệu Nghiệp vụ (RAG):** Tìm kiếm và trích dẫn chính xác chính sách, quy định nội bộ từ tài liệu (`.pdf`, `.docx`, `.txt`).
* **AI Tool Calling với Phân quyền (RBAC):** AI chủ động gọi các công cụ phân tích dữ liệu được giới hạn quyền theo vai trò người dùng (Chủ doanh nghiệp / Kế toán) và ghi nhận audit log.

---

## 📂 Cấu trúc dự án

```text
ESS/
├── docs/                         # Tài liệu phân tích & thiết kế (Tuần 1 - Discovery)
│   ├── requirements.md           # Yêu cầu chức năng, phi chức năng & phạm vi dự án
│   ├── user_stories.md           # Các câu chuyện người dùng theo chuẩn Agile
│   ├── acceptance_criteria.md    # Tiêu chuẩn nghiệm thu & cơ sở viết test case
│   └── kpi_definitions.md        # Định nghĩa công thức KPI kinh doanh & kỹ thuật
├── .gitignore                    # Chặn file nhạy cảm (.env), dữ liệu thật & rác hệ thống
└── README.md                     # Tài liệu giới thiệu tổng quan dự án
```

---

## 📚 Tài liệu Kỹ thuật (Phase 1: Project Discovery)

1. [**Project Requirements (`docs/requirements.md`)**](docs/requirements.md) — Bài toán, đối tượng sử dụng, In-Scope / Out-of-Scope và yêu cầu phi chức năng.
2. [**User Stories (`docs/user_stories.md`)**](docs/user_stories.md) — Đặc tả giá trị người dùng qua 8 Epics (từ US-01 đến US-17).
3. [**Acceptance Criteria (`docs/acceptance_criteria.md`)**](docs/acceptance_criteria.md) — Tiêu chuẩn kiểm thử Đúng/Sai dạng Given-When-Then (AC-01 đến AC-14).
4. [**KPI Definitions (`docs/kpi_definitions.md`)**](docs/kpi_definitions.md) — Công thức chỉ số tài chính, vận hành, RAG và AI Tool Calling.

---

## 🚦 Trạng thái hiện tại
* **Tuần 1 (Project Discovery):** ✅ Đã hoàn thành bộ tài liệu đặc tả (v1.1) và cấu hình chuẩn hóa repository.
