# TỔNG QUAN THƯ MỤC TÀI LIỆU DỰ ÁN (PROJECT DOCUMENTATION CATALOG)

> **Dự án**: MOE Education Account & Fee Management System (Agile Project)  
> **Nguồn gốc**: Trích xuất và đồng bộ từ Google Drive (`1wry8P-LjWUMaXIg70qa4spuGU4VJc42a`)  
> **Thư mục lưu trữ**: `/home/baudui/Projects/fs/document/`  
> **Cập nhật ngày**: 17/10/2026  
> **Định dạng lưu trữ**: **100% Markdown (.md)** phục vụ quản lý mã nguồn, tìm kiếm toàn văn và theo dõi biến động trên GitHub.

---

## 1. HƯỚNG DẪN CẬP NHẬT TÀI LIỆU (MAINTENANCE WORKFLOW)

> [!TIP]
> **Quy tắc cập nhật phân tán theo Module:**  
> Hệ thống tài liệu đã được chuẩn hóa thành các tệp Markdown độc lập từ **FS-01 đến FS-10**.
> - **Khi có cập nhật nghiệp vụ:** Đội ngũ BA / Dev / QA **chỉ cần chỉnh sửa trực tiếp vào file `FS-XX_<Name>.md` tương ứng**.
> - Không sửa đổi tập trung trên một tệp duy nhất nhằm tránh xung đột code/tài liệu (merge conflicts).

---

## 2. MA TRẬN PHÂN RÃ ĐẶC TẢ CHỨC NĂNG (MODULAR FS MATRIX: R1 – R10)

| Mã FS | Yêu Cầu (Tender) | Tên Phân Hệ & Chức Năng | Tác Tử Chính (Actor) | Phân Hệ (Portal) | Phân Bổ Sprint | Tài Liệu Markdown (.md) |
| :---: | :---: | :--- | :---: | :---: | :---: | :---: |
| **FS-01** | **R1** | **Vòng đời Tài khoản Giáo dục (Lifecycle & Closure)**<br>Tự động tạo & kích hoạt lúc 7 tuổi, tất toán chuyển sang CPF lúc 16 tuổi. | System / Batch | Admin Portal | **Sprint 1** | [FS-01.md](FS%20document/FS-01_Education_Account_Lifecycle.md) |
| **FS-02** | **R2** | **Nạp tiền Tài khoản (Top-Up Management)**<br>Nạp theo lô (Batch Top-Up) theo rule độ tuổi, số dư, học lực; Nạp đột xuất cho từng cá nhân. | MOE HQ | Admin Portal | **Sprint 2** | [FS-02.md](FS%20document/FS-02_Education_Account_TopUp.md) |
| **FS-03** | **R3** | **Quản lý Trường học, Học sinh & Cấu hình Phí**<br>Quản lý School, Class, Student, Enrolment, Fee Component, Rate Rules & Generation. | MOE HQ, School User | Admin Portal | **Sprint 1** (Enrolment)<br>**Sprint 2** (Fees) | [FS-03.md](FS%20document/FS-03_School_Student_Fee_Management.md) |
| **FS-04** | **R4** | **Trợ cấp Tài chính (FAS) & Phân loại AI**<br>Tự động cấp MOEFAS (Rule-based); AI/ML phân loại rủi ro (Low/Med/High); Trường xét duyệt SBFAS. | School User, MOE HQ | Admin Portal | **Sprint 3** | [FS-04.md](FS%20document/FS-04_Financial_Assistance_Scheme_FAS.md) |
| **FS-05** | **R5** | **Xử lý Đơn giấy Ngoại tuyến (Hardcopy FAS)**<br>Nhập đơn giấy thay phụ huynh, đính kèm bản quét scan, tự động kiểm tra trùng đơn trực tuyến. | School User | Admin Portal | **Sprint 3** | [FS-05.md](FS%20document/FS-05_Hardcopy_Applications_Offline.md) |
| **FS-06** | **R6** | **Quản lý Ngân sách & Thống kê Trợ cấp**<br>MOE HQ quản lý ngân sách MOEFAS; Trường quản lý ngân sách SBFAS; Cảnh báo hạn mức. | MOE HQ, School User | Admin Portal | **Sprint 3** | [FS-06.md](FS%20document/FS-06_FAS_Budget_and_Statistics.md) |
| **FS-07** | **R7** | **Giả lập Giao diện Người dùng (View-As Simulation)**<br>MOE HQ đóng vai School User hoặc Phụ huynh để hỗ trợ xử lý sự cố (chế độ Read-only). | MOE HQ Support | Admin Portal | **Post-MVP** | [FS-07.md](FS%20document/FS-07_User_Simulation_ViewAs.md) |
| **FS-08** | **R8** | **Cổng Dịch vụ Phụ huynh (Parent Portal & Profile)**<br>Đăng nhập SingPass, On-demand Sync dữ liệu con, Bento cards xem số dư EA và cập nhật My Details. | Parent / Guardian | e-Service Portal | **Sprint 1** | [FS-08.md](FS%20document/FS-08_Parent_Portal_SingPass_Profile.md) |
| **FS-09** | **R9** | **Công nợ Học phí & Thanh toán (Fee Payment)**<br>Xem công nợ, Thanh toán qua EA, Cổng trực tuyến Sandbox, Chia đôi (Split payment) & Tự động hoàn tiền. | Parent / Guardian | e-Service Portal | **Sprint 1** | [FS-09.md](FS%20document/FS-09_Outstanding_Fees_and_Payment.md) |
| **FS-10** | **R10** | **Nộp đơn FAS theo Hộ gia đình (Family Unit & AI)**<br>Nộp đơn trợ cấp chung cho các con trong gia đình; AI Auto-Fill tự động điền đơn từ hồ sơ. | Parent / Guardian | e-Service Portal | **Sprint 3** | [FS-10.md](FS%20document/FS-10_FAS_Family_Application_Portal.md) |

---

## 3. CẤU TRÚC THƯ MỤC TÀI LIỆU (100% MARKDOWN)

```
document/
├── README.md                                       # Bảng chỉ mục và hướng dẫn này
├── FSD_R3_GAP_AUDIT_REPORT.md                      # Báo cáo kiểm toán khoảng cách đặc tả R3
├── REQUIREMENTS_AND_BACKLOG_SUMMARY.md             # Báo cáo phân tích Backlog & Questionnaire
├── FS_SPECIFICATIONS_SUMMARY.md                    # Báo cáo phân tích kỹ thuật chuyên sâu FS-08 & FS-09
├── MEETINGS_AND_DECISIONS_SUMMARY.md               # Báo cáo biên bản họp & Decisions Log
├── First_meeting_questions.md                      # Bộ câu hỏi sơ khởi phiên làm việc đầu tiên
├── Noi_dung_Overview_Sprint_1.md                   # Kế hoạch thực hiện Sprint 1
│
├── Documentation/                                  # Biên bản họp, Transcript, Glossary
│   ├── Agile_Glossary.md                           # Từ điển thuật ngữ chuẩn hóa
│   ├── Kickoff_Transcript_refined.md               # Bản ghi chi tiết cuộc họp Kickoff
│   ├── MoM_Kickoff_meeting_12_10.md                # Biên bản họp Kickoff ngày 12/10
│   ├── MoM_Sprint_1_16_10.md                       # Biên bản họp tổng kết Sprint 1 ngày 16/10
│   └── Sprint_1_Review_Transcript.md               # Bản ghi âm rà soát Sprint 1
│
├── FS document/                                    # Hồ sơ đặc tả chức năng Module hóa (R1 – R10)
│   ├── FS-01_Education_Account_Lifecycle.md        # [R1] Vòng đời EA
│   ├── FS-02_Education_Account_TopUp.md            # [R2] Nạp tiền Top-Up
│   ├── FS-03_School_Student_Fee_Management.md      # [R3] Quản lý Trường & Phí
│   ├── FS-04_Financial_Assistance_Scheme_FAS.md    # [R4] Trợ cấp FAS & AI
│   ├── FS-05_Hardcopy_Applications_Offline.md      # [R5] Đơn giấy offline
│   ├── FS-06_FAS_Budget_and_Statistics.md          # [R6] Ngân sách & Thống kê
│   ├── FS-07_User_Simulation_ViewAs.md             # [R7] Giả lập giao diện
│   ├── FS-08_Parent_Portal_SingPass_Profile.md     # [R8] Cổng Phụ huynh
│   ├── FS-09_Outstanding_Fees_and_Payment.md       # [R9] Công nợ & Thanh toán
│   └── FS-10_FAS_Family_Application_Portal.md      # [R10] Đơn FAS hộ gia đình
│
└── Requirement analysis/                           # Tài liệu phân tích yêu cầu & kiến trúc giải pháp
    ├── High-level_Solution.md                      # Giải pháp kỹ thuật 10 Functions
    ├── Function_Requirements.md                    # Yêu cầu chức năng song ngữ
    └── Functional_Requirement_3.md                 # Phân tích chi tiết Requirement 3
```
