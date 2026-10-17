# TỔNG QUAN THƯ MỤC TÀI LIỆU DỰ ÁN (PROJECT DOCUMENTATION CATALOG)

> **Dự án**: MOE Education Account & Fee Management System (Agile Project)  
> **Nguồn gốc**: Trích xuất và đồng bộ từ Google Drive (`1wry8P-LjWUMaXIg70qa4spuGU4VJc42a`)  
> **Thư mục lưu trữ**: `/home/baudui/Projects/fs/document/`  
> **Cập nhật ngày**: 17/10/2026  
> **Kiến trúc tài liệu**: **Module hóa theo từng Requirement (R1 đến R10)** nhằm loại bỏ phụ thuộc vào tệp nguyên khối `[Agile] FS.docx`, giúp theo dõi, phân nhánh và cập nhật độc lập dễ dàng.

---

## 1. HƯỚNG DẪN CẬP NHẬT TÀI LIỆU (MAINTENANCE WORKFLOW)

> [!TIP]
> **Quy tắc cập nhật phân tán:**  
> Trước đây, toàn bộ đặc tả R1, R3, R8, R9 bị gộp chung trong tệp `[Agile] FS.docx` (dung lượng 2.6 MB, hơn 1,000 phần tử) gây khó khăn khi theo dõi thay đổi.  
> Hiện tại, hệ thống đã được **tách rời hoàn toàn thành các tệp tài liệu chuyên biệt từ FS-01 đến FS-10**.
> - **Khi có cập nhật nghiệp vụ:** Đội ngũ BA / Dev / QA **chỉ cần chỉnh sửa trực tiếp vào file `FS-XX` tương ứng** (dạng `.docx` hoặc `.md`).
> - Tệp `[Agile] FS.docx` được giữ lại làm bản tham chiếu lưu trữ (Archive / Monolithic Baseline).

---

## 2. MA TRẬN PHÂN RÃ ĐẶC TẢ CHỨC NĂNG (MODULAR FS MATRIX: R1 – R10)

| Mã FS | Yêu Cầu (Tender) | Tên Phân Hệ & Chức Năng | Tác Tử Chính (Actor) | Phân Hệ (Portal) | Phân Bổ Sprint | Tệp Word (.docx) | Tệp Markdown (.md) |
| :---: | :---: | :--- | :---: | :---: | :---: | :---: | :---: |
| **FS-01** | **R1** | **Vòng đời Tài khoản Giáo dục (Lifecycle & Closure)**<br>Tự động tạo & kích hoạt lúc 7 tuổi, tất toán chuyển sang CPF lúc 16 tuổi. | System / Batch | Admin Portal | **Sprint 1** | [FS-01.docx](file:///home/baudui/Projects/fs/document/FS%20document/FS-01_Education_Account_Lifecycle.docx) | [FS-01.md](file:///home/baudui/Projects/fs/document/FS%20document/FS-01_Education_Account_Lifecycle.md) |
| **FS-02** | **R2** | **Nạp tiền Tài khoản (Top-Up Management)**<br>Nạp theo lô (Batch Top-Up) theo rule độ tuổi, số dư, học lực; Nạp đột xuất cho từng cá nhân. | MOE HQ | Admin Portal | **Sprint 2** | — | [FS-02.md](file:///home/baudui/Projects/fs/document/FS%20document/FS-02_Education_Account_TopUp.md) |
| **FS-03** | **R3** | **Quản lý Trường học, Học sinh & Cấu hình Phí**<br>Quản lý School, Class, Student, Enrolment, Fee Component, Rate Rules & Generation. | MOE HQ, School User | Admin Portal | **Sprint 1** (Enrolment)<br>**Sprint 2** (Fees) | [FS-03.docx](file:///home/baudui/Projects/fs/document/FS%20document/FS-03_School_Student_Fee_Management.docx) | [FS-03.md](file:///home/baudui/Projects/fs/document/FS%20document/FS-03_School_Student_Fee_Management.md) |
| **FS-04** | **R4** | **Trợ cấp Tài chính (FAS) & Phân loại AI**<br>Tự động cấp MOEFAS (Rule-based); AI/ML phân loại rủi ro (Low/Med/High); Trường xét duyệt SBFAS. | School User, MOE HQ | Admin Portal | **Sprint 3** | — | [FS-04.md](file:///home/baudui/Projects/fs/document/FS%20document/FS-04_Financial_Assistance_Scheme_FAS.md) |
| **FS-05** | **R5** | **Xử lý Đơn giấy Ngoại tuyến (Hardcopy FAS)**<br>Nhập đơn giấy thay phụ huynh, đính kèm bản quét scan, tự động kiểm tra trùng đơn trực tuyến. | School User | Admin Portal | **Sprint 3** | — | [FS-05.md](file:///home/baudui/Projects/fs/document/FS%20document/FS-05_Hardcopy_Applications_Offline.md) |
| **FS-06** | **R6** | **Quản lý Ngân sách & Thống kê Trợ cấp**<br>MOE HQ quản lý ngân sách MOEFAS; Trường quản lý ngân sách SBFAS; Cảnh báo hạn mức. | MOE HQ, School User | Admin Portal | **Sprint 3** | — | [FS-06.md](file:///home/baudui/Projects/fs/document/FS%20document/FS-06_FAS_Budget_and_Statistics.md) |
| **FS-07** | **R7** | **Giả lập Giao diện Người dùng (View-As Simulation)**<br>MOE HQ đóng vai School User hoặc Phụ huynh để hỗ trợ xử lý sự cố (chế độ Read-only). | MOE HQ Support | Admin Portal | **Post-MVP** | — | [FS-07.md](file:///home/baudui/Projects/fs/document/FS%20document/FS-07_User_Simulation_ViewAs.md) |
| **FS-08** | **R8** | **Cổng Dịch vụ Phụ huynh (Parent Portal & Profile)**<br>Đăng nhập SingPass, On-demand Sync dữ liệu con, Bento cards xem số dư EA và cập nhật My Details. | Parent / Guardian | e-Service Portal | **Sprint 1** | [FS-08.docx](file:///home/baudui/Projects/fs/document/FS%20document/FS-08_Parent_Portal_SingPass_Profile.docx) | [FS-08.md](file:///home/baudui/Projects/fs/document/FS%20document/FS-08_Parent_Portal_SingPass_Profile.md) |
| **FS-09** | **R9** | **Công nợ Học phí & Thanh toán (Fee Payment)**<br>Xem công nợ, Thanh toán qua EA, Cổng trực tuyến Sandbox, Chia đôi (Split payment) & Tự động hoàn tiền. | Parent / Guardian | e-Service Portal | **Sprint 1** | [FS-09.docx](file:///home/baudui/Projects/fs/document/FS%20document/FS-09_Outstanding_Fees_and_Payment.docx) | [FS-09.md](file:///home/baudui/Projects/fs/document/FS%20document/FS-09_Outstanding_Fees_and_Payment.md) |
| **FS-10** | **R10** | **Nộp đơn FAS theo Hộ gia đình (Family Unit & AI)**<br>Nộp đơn trợ cấp chung cho các con trong gia đình; AI Auto-Fill tự động điền đơn từ hồ sơ. | Parent / Guardian | e-Service Portal | **Sprint 3** | — | [FS-10.md](file:///home/baudui/Projects/fs/document/FS%20document/FS-10_FAS_Family_Application_Portal.md) |

---

## 3. CẤU TRÚC THƯ MỤC DỰ ÁN CHI TIẾT

```
document/
├── Documentation/                                   # Quản trị dự án, Backlog, QA & Biên bản họp
│   ├── Agile Glossary.docx                         # Từ điển thuật ngữ chuẩn hóa
│   ├── Agile requirements.xlsx                     # Ma trận User Stories & BDD Acceptance Criteria
│   ├── Kickoff Transcript refined.docx             # Bản ghi chi tiết cuộc họp Kickoff
│   ├── MoM - Kickoff meeting - 12_10.docx          # Biên bản họp Kickoff ngày 12/10
│   ├── MoM - Sprint 1 - 16_10.docx                 # Biên bản họp tổng kết Sprint 1 ngày 16/10
│   ├── Questionaire.xlsx                           # Danh sách câu hỏi làm rõ (Q&A) với Client
│   └── Sprint 1 Review Transcript.docx             # Bản ghi âm rà soát Sprint 1
│
├── FS document/                                    # Hồ sơ đặc tả chức năng Module hóa (R1 – R10)
│   ├── FS-01_Education_Account_Lifecycle.docx      # [R1] Word chính thức
│   ├── FS-01_Education_Account_Lifecycle.md        # [R1] Bản Markdown
│   ├── FS-02_Education_Account_TopUp.md            # [R2] Bản Markdown
│   ├── FS-03_School_Student_Fee_Management.docx    # [R3] Word chính thức
│   ├── FS-03_School_Student_Fee_Management.md      # [R3] Bản Markdown
│   ├── FS-04_Financial_Assistance_Scheme_FAS.md    # [R4] Bản Markdown
│   ├── FS-05_Hardcopy_Applications_Offline.md      # [R5] Bản Markdown
│   ├── FS-06_FAS_Budget_and_Statistics.md          # [R6] Bản Markdown
│   ├── FS-07_User_Simulation_ViewAs.md             # [R7] Bản Markdown
│   ├── FS-08_Parent_Portal_SingPass_Profile.docx   # [R8] Word chính thức
│   ├── FS-08_Parent_Portal_SingPass_Profile.md     # [R8] Bản Markdown
│   ├── FS-09_Outstanding_Fees_and_Payment.docx     # [R9] Word chính thức
│   ├── FS-09_Outstanding_Fees_and_Payment.md       # [R9] Bản Markdown
│   ├── FS-10_FAS_Family_Application_Portal.md      # [R10] Bản Markdown
│   └── [Agile] FS.docx                             # Tệp gốc tổng hợp (Lưu trữ tham chiếu)
│
├── Requirement analysis/                           # Phân tích yêu cầu & Kiến trúc giải pháp
│   ├── [Agile] High-level Solution.docx            # Kiến trúc giải pháp 10 Functions
│   ├── Function Requirements.docx                  # Yêu cầu chức năng song ngữ Anh - Việt
│   └── Functional Reqirement 3.docx                # Báo cáo phân tích chi tiết Requirement 3
│
├── First meeting questions.docx                    # Bộ câu hỏi sơ khởi phiên làm việc đầu tiên
├── Nội dung Overview Sprint 1.docx                 # Kế hoạch và phạm vi Sprint 1
├── Product Backlog.xlsx                            # Danh mục 28 Product Backlog Items (PBI)
│
├── README.md                                       # Bảng chỉ mục và hướng dẫn bảo trì này
├── REQUIREMENTS_AND_BACKLOG_SUMMARY.md             # Báo cáo phân tích Backlog, User Stories & Q&A
├── FS_SPECIFICATIONS_SUMMARY.md                    # Báo cáo phân tích sâu FS-08, FS-09, Schema & API
└── MEETINGS_AND_DECISIONS_SUMMARY.md               # Báo cáo quyết định cuộc họp, Decisions Log & Action Items
```

---

## 4. TÀI LIỆU BÁO CÁO TỔNG HỢP CHUYÊN SÂU

1. 📋 [REQUIREMENTS_AND_BACKLOG_SUMMARY.md](file:///home/baudui/Projects/fs/document/REQUIREMENTS_AND_BACKLOG_SUMMARY.md): Phân tích 14 User Stories, 28 PBIs, Sprint Shift và 12 quyết định của Client trong Questionnaire.
2. 🛠️ [FS_SPECIFICATIONS_SUMMARY.md](file:///home/baudui/Projects/fs/document/FS_SPECIFICATIONS_SUMMARY.md): Phân tích sâu mối nối kỹ thuật giữa R3 với FS-08 & FS-09, Schema Invoice, Sequential Split Payment, Idempotency và HMAC Webhook.
3. 📌 [MEETINGS_AND_DECISIONS_SUMMARY.md](file:///home/baudui/Projects/fs/document/MEETINGS_AND_DECISIONS_SUMMARY.md): Tổng hợp biên bản các cuộc họp, Decisions Log, CPF Transfer, SSO MOE Active Directory và Action Items.
