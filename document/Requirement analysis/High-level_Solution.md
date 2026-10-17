
## I. TỔNG THỂ HỆ THỐNG (SYSTEM OVERVIEW)

Hệ thống Education Account & FAS (MOE Singapore) bao gồm 2 phân hệ chính hợp nhất:

Admin Portal (F1 – F7): Phân hệ dành cho cán bộ Bộ Giáo dục (MOE HQ) và Cán bộ Nhà trường (School User) để quản lý cấu hình tài khoản EA, quy trình nạp tiền (Top-up), danh mục trường lớp, thiết lập học phí, xét duyệt trợ cấp tài chính (FAS), nhập đơn giấy offline, quản lý ngân sách và mô phỏng giao diện người dùng.

e-Service Portal (F8 – F10): Cổng dịch vụ công dành cho Phụ huynh (Parent) truy cập qua SingPass để tra cứu số dư tài khoản EA của con, thực hiện thanh toán học phí trực tuyến, nộp đơn trợ cấp FAS theo hộ gia đình, và được hỗ trợ tự động bởi Trợ lý AI.


## II. BẢN MÔ TẢ CHI TIẾT FULL 10 FUNCTION (FINAL VERSION)


### 🏛️ PHÂN HỆ ADMIN PORTAL (F1 – F7)


#### F1: Education Account Lifecycle (Quản lý vòng đời tài khoản EA)

Tự động hóa toàn bộ vòng đời tài khoản giáo dục của học sinh dựa trên dữ liệu đồng bộ khi Phụ huynh tương tác.

1.1 Kiểm tra & Đồng bộ Citizen từ Government API (On-demand Sync): Hệ thống gọi Government API để tra cứu và cập nhật dữ liệu công dân thời gian thực ngay khi Phụ huynh thực hiện đăng nhập vào cổng e-Service.

1.2 Tự động tạo và kích hoạt EA khi đủ 7 tuổi: Sau khi nhận dữ liệu đồng bộ lúc đăng nhập, hệ thống tự động kiểm tra điều kiện (Công dân Singapore - SC, đủ 7 tuổi và chưa có tài khoản) để khởi tạo và kích hoạt tài khoản EA tức thì.

1.3 Tự động đóng EA khi đến 16 tuổi: Tự động chuyển trạng thái tài khoản sang "Deactive" khi học sinh đạt 16 tuổi.

1.4 Quản lý trạng thái EA: Theo dõi và cập nhật trạng thái hoạt động của tài khoản (Active, Deactive).

1.5 Sổ cái EA (Ledger): Hệ thống kế toán ghi nhận chính xác mọi giao dịch Ghi có (Credit), Ghi nợ (Debit), Hoàn tiền (Reversal) và Trạng thái chờ xử lý (Pending).


#### F2: Top-up (Nạp tiền vào tài khoản EA)

Cho phép MOE HQ cấu hình và thực hiện nạp tiền vào các tài khoản EA.

2.1 Cấu hình rule chọn đối tượng: Cài đặt tiêu chí lọc danh sách nhận tiền (độ tuổi, số dư hiện tại, tình trạng đi học,...).

2.2 Xem trước danh sách tài khoản và tổng tiền: Xem bản tổng hợp chi tiết số lượng tài khoản thụ hưởng và tổng ngân sách dự kiến trước khi chốt nạp.

2.3 Batch top-up theo lịch định kỳ: Tự động thực hiện nạp tiền hàng loạt theo lịch đã thiết lập.

2.4 Batch top-up ad-hoc: Thực hiện nạp tiền hàng loạt đột xuất theo chính sách mới.

2.5 Top-up cho tài khoản cụ thể: Nạp tiền trực tiếp cho từng học sinh riêng lẻ trong các trường hợp đặc biệt.

2.6 Ghi có vào sổ cái EA: Thực hiện cộng tiền vào sổ cái cho các tài khoản đang ở trạng thái Active.

2.7 Lịch sử top-up và audit: Lưu trữ đầy đủ lịch sử giao dịch nạp tiền phục vụ công tác kiểm toán.


#### F3: School & Fee Maintenance (Quản lý Trường học & Cấu hình Phí)

Quản lý danh mục trường lớp, học sinh và thiết lập biểu phí dịch vụ giáo dục.

Cấu hình Trường học (School Setup):

3.1 Maintain schools: Quản lý thông tin danh mục các trường học.

3.2 Cấp tài khoản School User, assign vào trường: Khởi tạo tài khoản và phân quyền cho cán bộ từng trường.

3.3 Academic year, level/cohort, school level offering: Cấu hình năm học, khối lớp và các chương trình giảng dạy.

3.4 Maintain classes: Quản lý danh sách các lớp học.

3.5 Maintain students: Quản lý thông tin học sinh (Cán bộ trường nhập thủ công khi cần).

3.6 Enrolment và class assignment: Xử lý nhập học và xếp lớp cho học sinh.

3.7 Chuyển lớp, chuyển trường (HQ User): Xử lý luồng chuyển lớp hoặc chuyển trường cho học sinh.

3.8 Liên kết student SC với EA: Ánh xạ hồ sơ học sinh là công dân Singapore với tài khoản EA tương ứng.

Cấu hình Phí (Fee & Charge):

3.9 Fee types: Danh mục các loại phí (Học phí, phụ phí, hoạt động ngoại khóa,...).

3.10 Fee components (cả GST): Chi tiết các thành phần phí (bao gồm thuế GST).

3.11 Fee rate rules theo level và nhóm cư trú (SC/PR/IS): Thiết lập mức phí theo khối lớp và loại cư trú (Công dân Singapore, Thường trú nhân, Học sinh quốc tế).

3.12 Fee publication: Phát hành khoản phí (chọn đối tượng, kỳ thu, ngày phát sinh nợ, hạn thanh toán).

3.13 Resolve recipient, tạo Student Charge: Hệ thống tự động tạo khoản thu cho từng học sinh, quản lý các trạng thái (Issued / Due-dated / Paid / Cancelled).

3.14 Charge adjustment có audit: Điều chỉnh giảm/tăng khoản phí Outstanding và lưu nhật ký kiểm toán.


#### F4: Financial Assistance Scheme (Xét duyệt Trợ cấp Tài chính - FAS)

Tự động hóa kết hợp trí tuệ nhân tạo (AI/ML) để phân loại và cấp kinh phí hỗ trợ tài chính cho học sinh.

4.1 Cấu hình nhiều scheme (MOEFAS, SBFAS): Cấu hình tiêu chí cho gói trợ cấp toàn quốc (MOEFAS) và gói trợ cấp riêng của từng trường (SBFAS).

4.2 Eligibility criteria: Quy định điều kiện xét tuyển theo Quốc tịch, Thu nhập hộ gia đình (Gross Household Income) và Thu nhập bình quân đầu người (Per Capita Income).

4.3 Tier và mức subsidy theo từng fee component: Cài đặt các hạn mức và tỷ lệ miễn giảm cho từng thành phần phí.

4.4 Lấy dữ liệu income: Tích hợp thu thập dữ liệu thu nhập từ các cơ quan chính phủ.

4.5 Đánh giá rule-based, tự động cấp MOEFAS: Tự động duyệt và cấp MOEFAS nếu hồ sơ đạt đầy đủ các điều kiện cứng.

4.6 School User xét duyệt SBFAS: Nếu không đạt điều kiện MOEFAS, Cán bộ trường sẽ xem xét cấp SBFAS.

4.7 AI ML phân loại Low/Medium/High (Tính năng AI): Mô hình Machine Learning phân tích và dự báo mức độ khó khăn tài chính còn lại của gia đình (Thấp - Low Risk, Trung bình - Medium Risk, Cao - High Risk).

4.8 AI Gợi ý assistance tier (Tính năng AI): AI đề xuất cấp độ trợ cấp phù hợp để cán bộ nhà trường tham khảo đưa ra quyết định.

4.9 Áp kết quả FAS vào charge Outstanding qua adjustment: Tự động giảm trừ số tiền phải nộp trực tiếp trên các khoản phí Outstanding.

4.10 Hồ sơ và trạng thái FAS, audit: Lưu trữ toàn bộ lịch sử xét duyệt, trạng thái hồ sơ và nhật ký kiểm toán.


#### F5: Hardcopy Applications (Xử lý đơn giấy offline)

Giải pháp cho các phụ huynh không thể tiếp cận hoặc thao tác trên e-Service Portal.

5.1 School User nhập đơn giấy thay phụ huynh: Cán bộ trường nhập thông tin từ đơn giấy do phụ huynh nộp, xác thực định danh qua số NRIC.

5.2 Lưu bản scan: Đính kèm tệp tin quét (scan) của đơn giấy lên hệ thống.

5.3 Kiểm tra trùng với đơn online: Hệ thống tự động rà soát trùng lặp thông tin giữa đơn giấy và đơn online.

5.4 Đưa vào cùng flow xét duyệt FAS, gắn kênh = paper: Đưa hồ sơ vào luồng xét duyệt tập trung của F4 và đánh dấu nguồn nộp là "Paper".


#### F6: Budget & Statistics (Quản lý Ngân sách & Thống kê)

Theo dõi, phân bổ và cảnh báo hạn mức ngân sách trợ cấp.

6.1 HQ đặt budget MOEFAS: MOE HQ thiết lập hạn mức ngân sách trợ cấp toàn quốc.

6.2 HQ theo dõi thống kê MOEFAS: Xem báo cáo, tình hình giải ngân ngân sách MOEFAS theo thời gian thực.

6.3 School đặt budget SBFAS: Các trường tự thiết lập ngân sách trợ cấp riêng của trường.

6.4 School theo dõi thống kê SBFAS: Cán bộ trường theo dõi số liệu và báo cáo ngân sách SBFAS nội bộ.

6.5 Cảnh báo khi gần hết budget: Tự động gửi cảnh báo khi hạn mức chi trả trợ cấp vượt ngưỡng an toàn.


#### F7: Simulation (Giả lập giao diện)

Công cụ cho phép MOE HQ đóng vai người dùng khác để hỗ trợ xử lý sự cố/thắc mắc.

7.1 Chọn vai trò và đối tượng cần xem: Lựa chọn giả lập dưới góc nhìn của Cán bộ trường hoặc Phụ huynh cụ thể.

7.2 Màn hình "View as" chỉ đọc: Hiển thị chính xác màn hình mà người dùng đó đang thấy (chế độ Read-only), có banner nhận diện đang giả lập.

7.3 Ghi log simulation: Lưu lại toàn bộ thông tin phiên giả lập để đảm bảo an toàn hệ thống và bảo mật thông tin.


### 🌐 PHÂN HỆ e-SERVICE PORTAL (F8 – F10)


#### F8: Parent Account Access (Truy cập & Hỗ trợ Phụ huynh)

Cổng thông tin dành cho Phụ huynh, tích hợp trợ lý AI thông minh.

8.1 Đăng nhập SingPass: Phụ huynh xác thực danh tính an toàn qua cổng SingPass.

8.2 Tra cứu Parent và con qua Government API, tạo tài khoản lần đầu, cập nhật dữ liệu: ngay khi đăng nhập, hệ thống tự động gọi API Chính phủ để kiểm tra quan hệ nhân khẩu, cập nhật thông tin và tự động khởi tạo tài khoản EA cho con nếu đủ điều kiện (kích hoạt luồng 1.1 & 1.2).

8.3 Quản lý session: Tự động kết thúc phiên làm việc sau 15 phút không hoạt động để bảo mật.

8.4 Home - Danh sách con theo thứ tự quy định: Màn hình chính hiển thị danh sách các con theo quy chuẩn.

8.5 Xem EA: Tra cứu số dư khả dụng, số dư Pending, dòng tiền vào/ra và các khoản khấu trừ FAS.

8.6 Xem giao dịch: Tra cứu và lọc lịch sử giao dịch theo khoảng thời gian hoặc loại chi trả.

8.7 Sửa thông tin liên hệ: Cho phép cập nhật SĐT, Email, Địa chỉ nhận thư (Địa chỉ thường trú cố định từ SingPass).

8.8 AI Trả lời câu hỏi về e-Service (Tính năng AI): Trợ lý AI giải đáp thắc mắc liên quan đến các tính năng và dịch vụ trên e-Service.

8.9 AI Hỏi lại để hiểu ngữ cảnh (Tính năng AI): AI chủ động tương tác linh hoạt, đặt câu hỏi làm rõ nhu cầu để đưa ra câu trả lời chính xác nhất.


#### F9: Fee Payment (Thanh toán Học phí)

Quy trình tra cứu phí, gom hóa đơn và thanh toán trực tuyến.

9.1 Xác minh quyền Parent–Student, liệt kê con: Kiểm tra quyền hạn và hiển thị danh sách học sinh thuộc quản lý của phụ huynh.

9.2 Xem outstanding charges và số dư EA: Hiển thị chi tiết các khoản phí cần đóng và số dư tài khoản EA hiện có.

9.3a Chọn một hoặc nhiều charge của cùng student và trường: Gom các khoản phí cần thanh toán trong cùng một trường.

9.3b Tạo invoice cùng invoice items, chốt snapshot, khóa charge: Khởi tạo hóa đơn thanh toán, chốt số liệu tức thời và tạm khóa khoản phí để tránh thanh toán trùng.

9.4 Chọn phương thức thanh toán: Chọn thanh toán bằng tài khoản EA, thanh toán trực tuyến (Thẻ/PayNow) hoặc chia nhỏ thanh toán (Split payment - vừa EA vừa Online).

9.5 Thanh toán EA: Trực tiếp trừ tiền trong tài khoản EA, tự động hoàn tiền (Reversal) lập tức nếu xảy ra lỗi hệ thống.

9.6 Thanh toán online qua sandbox gateway: Kết nối thanh toán trực tuyến qua cổng thanh toán.

9.7 Nhận webhook và đối soát: Hệ thống nhận phản hồi thanh toán (Xác thực HMAC, cơ chế chống trùng lặp Idempotent).

9.8 Cập nhật trạng thái: Chuyển trạng thái hóa đơn sang "Paid" hoặc mở khóa charge nếu thanh toán thất bại.

9.9 Xác nhận, xem biên lai theo từng item, thử lại khi lỗi: Xem/tải biên lai chi tiết hoặc bấm thanh toán lại nếu gặp sự cố.

9.10 Hết hạn invoice: Tự động hủy các hóa đơn quá hạn chưa hoàn tất để giải phóng khoản phí bị khóa.


#### F10: FAS Application (Nộp đơn xin Trợ cấp Tài chính)

Quy trình nộp đơn FAS cho hộ gia đình có sự hỗ trợ của AI.

10.1 Chọn con đưa vào đơn (family unit): Lựa chọn danh sách các con trong gia đình cùng đứng tên trên một đơn đăng ký.

10.2 Khai thành viên và thu nhập hộ gia đình: Khai báo thông tin chi tiết nhân khẩu và thu nhập các thành viên trong nhà.

10.3 AI Tự điền form từ profile và câu trả lời đã thu thập (Tính năng AI): AI tự động trích xuất dữ liệu từ hồ sơ cá nhân và các thông tin thu thập được qua đoạn chat với AI (ở F8.8/F8.9) để tự động điền (Auto-fill) vào mẫu đơn FAS.

10.4 Xem lại, chỉnh sửa, xác nhận và nộp: Phụ huynh rà soát lại toàn bộ thông tin đã điền, thực hiện chỉnh sửa nếu cần và xác nhận nộp đơn.

10.5 Theo dõi trạng thái và xem kết quả: Phụ huynh chủ động theo dõi tiến độ thẩm định và xem kết quả phê duyệt FAS trực tiếp trên cổng.
