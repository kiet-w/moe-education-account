# FS-02: Education Account Top-Up (Requirement 2)

> **Phân hệ**: Admin Portal (MOE HQ Users)  
> **Requirement**: R2 – Education Account Top-Up  
> **Product Backlog**: PB-14 (Sprint 2) | **User Story**: US-02 (FR2)  
> **Trạng thái**: Specification Ready  

---

## 1. TỔNG QUAN (OVERVIEW)
Chức năng cho phép người dùng Trụ sở chính Bộ Giáo dục (MOE HQ Users) thực hiện cấu hình và nạp tiền (Top-Up) vào các tài khoản giáo dục (Education Accounts - EA) của học sinh. Việc nạp tiền có thể thực hiện theo lô (Batch Top-Up) theo các quy tắc nghiệp vụ định sẵn hoặc nạp trực tiếp cho từng cá nhân (Ad-hoc Individual Top-Up).

### 1.1. Phạm vi nghiệp vụ
- **Batch Top-Up định kỳ (Scheduled):** Tự động nạp tiền hàng loạt theo lịch ngân sách nhà nước đã phê duyệt (ví dụ đầu năm học hoặc đầu học kỳ).
- **Batch Top-Up đột xuất (Ad-hoc):** Nạp tiền theo các gói hỗ trợ đặc biệt của chính phủ (ví dụ gói cứu trợ kinh tế, thưởng học tập).
- **Individual Top-Up:** Nạp tiền riêng cho từng chủ tài khoản cụ thể trong các trường hợp ngoại lệ (giải quyết khiếu nại, bổ sung ngân sách khẩn cấp).

---

## 2. QUY TRÌNH NGHIỆP VỤ (BUSINESS PROCESS FLOWS)

### 2.1. Quy trình Batch Top-Up (Nạp tiền theo lô)
1. **Thiết lập tiêu chí lọc đối tượng (Rule Configuration):**
   - **Độ tuổi (Age Criteria):** Khoảng tuổi từ 7 đến dưới 16 (ví dụ chỉ nạp cho học sinh từ 7 đến 12 tuổi - bậc Tiểu học).
   - **Số dư hiện tại (Account Balance Criteria):** Lọc theo số dư (ví dụ số dư dưới 100 SGD, hoặc nạp không phân biệt số dư).
   - **Tình trạng đi học (Schooling Status):** Đang ghi danh tại trường công lập, bán công lập hoặc trường chuyên biệt (`enrolment_status = 'ENROLLED'`).
   - **Cấp học / Khối lớp (Academic Level):** Lọc theo bậc học (Primary, Secondary, Pre-University).
2. **Ước tính ngân sách & Xem trước danh sách (Preview & Estimation):**
   - Hệ thống quét cơ sở dữ liệu và hiển thị:
     - Tổng số lượng tài khoản thụ hưởng thỏa mãn điều kiện.
     - Số tiền nạp trên mỗi tài khoản (Top-Up Amount per Account).
     - Tổng ngân sách dự kiến giải ngân (Total Budget Required = Số lượng × Số tiền nạp).
   - Hiển thị danh sách mẫu (Sample list) có phân trang và tìm kiếm để HQ User rà soát.
3. **Phê duyệt & Kích hoạt (Approval & Execution):**
   - Yêu cầu kiểm soát 2 bước (Maker-Checker): Chuyên viên HQ tạo đợt nạp tiền -> Lãnh đạo HQ Finance phê duyệt.
   - Khi được kích hoạt, hệ thống chạy Background Job ghi có (Credit) vào sổ cái tài khoản `education_accounts`.
4. **Ghi sổ cái & Nhật ký kiểm toán (Ledger Posting & Audit Trail):**
   - Chỉ nạp cho các tài khoản đang ở trạng thái `ACTIVE`. Bỏ qua các tài khoản `CLOSED` hoặc `SUSPENDED`.
   - Sinh giao dịch trong bảng `education_account_transactions` với loại giao dịch `TOP_UP`.
   - Cập nhật số dư `current_balance = current_balance + topup_amount`.

---

## 3. RÀNG BUỘC NGHIỆP VỤ & BẢO TOÀN DỮ LIỆU (BUSINESS RULES)
- **BR-R2-01 (Active Account Constraint):** Tiền Top-up chỉ được ghi có vào tài khoản có `account_status = 'ACTIVE'`.
- **BR-R2-02 (Citizen Eligibility):** Chủ tài khoản phải là công dân Singapore (SC) còn hiệu lực tại thời điểm nạp tiền.
- **BR-R2-03 (Idempotency in Batch Run):** Mỗi đợt Batch Top-Up có một mã `batch_reference_id` duy nhất. Hệ thống ngăn chặn chạy trùng lặp hai lần cho cùng một batch.
- **BR-R2-04 (Balance Cap / Overflow):** Nếu chính sách có quy định hạn mức số dư tối đa (Balance Cap), hệ thống cảnh báo hoặc điều chỉnh số tiền nạp theo cấu hình.
- **BR-R2-05 (Audit Trail):** Mọi giao dịch nạp tiền bắt buộc ghi nhận: `created_by`, `approved_by`, `created_at`, `topup_reason`, `source_budget_code`.

---

## 4. TIÊU CHÍ CHẤP NHẬN (ACCEPTANCE CRITERIA)
- **AC-01:** Given cấu hình rule nạp tiền (Tuổi 7-12, đang học Tiểu học, nạp 200 SGD), When bấm xem trước, Then hệ thống trả về chính xác tổng số học sinh thỏa mãn và tổng ngân sách cần giải ngân.
- **AC-02:** Given một tài khoản cụ thể, When HQ User thực hiện nạp 150 SGD kèm lý do hợp lệ, Then số dư tài khoản tăng 150 SGD ngay lập tức và lịch sử giao dịch hiển thị dòng Top-Up.
