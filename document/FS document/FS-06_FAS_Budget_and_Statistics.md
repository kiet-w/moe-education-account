# FS-06: FAS Budget & Statistics Tracking (Requirement 6)

> **Phân hệ**: Admin Portal (MOE HQ & School Users)  
> **Requirement**: R6 – FAS Budget & Statistics  
> **Product Backlog**: PB-21 (Sprint 3) | **User Story**: US-07 (FR7)  
> **Trạng thái**: Specification Ready  

---

## 1. TỔNG QUAN (OVERVIEW)
Chức năng cung cấp công cụ quản trị tài chính, cho phép MOE HQ và các trường thiết lập hạn mức ngân sách trợ cấp, theo dõi tiến độ giải ngân theo thời gian thực và phát cảnh báo khi số tiền trợ cấp vượt ngưỡng an toàn.

---

## 2. PHÂN HỆ QUẢN LÝ NGÂN SÁCH

### 2.1. Ngân sách cấp Bộ (MOEFAS Budget - MOE HQ)
- MOE HQ thiết lập tổng hạn mức ngân sách MOEFAS cho toàn quốc theo năm tài chính.
- Báo cáo phân tích:
  - Tỷ lệ giải ngân theo vùng, theo cấp học (Tiểu học, THCS, THPT).
  - Thống kê số lượng học sinh được nhận MOEFAS toàn quốc.
  - Dự báo tốc độ tiêu hao ngân sách theo các đợt phát hành học phí.

### 2.2. Ngân sách cấp Trường (SBFAS Budget - School Users)
- Hiệu trưởng hoặc Ban giám hiệu trường thiết lập hạn mức ngân sách SBFAS riêng của trường trong năm học.
- Cán bộ trường theo dõi trực quan:
  - Số dư ngân sách SBFAS còn lại khả dụng.
  - Danh sách học sinh đã được cấp học bổng SBFAS và tổng số tiền đã miễn giảm.

### 2.3. Cơ chế cảnh báo vượt ngưỡng (Budget Threshold Alerts)
- **Cảnh báo Vàng (Warning):** Khi ngân sách đạt 80% hạn mức phê duyệt.
- **Cảnh báo Cam (Critical):** Khi ngân sách đạt 95% hạn mức.
- **Khóa phê duyệt (Hard Stop / Escalation):** Khi ngân sách vượt 100%, hệ thống yêu cầu xác nhận đặc biệt từ Lãnh đạo hoặc chặn duyệt thêm đơn SBFAS mới.
