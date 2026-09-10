# TEST CASE – PAYMENT

> Bộ Test Case cơ bản cho người mới học. Chỉ giữ các case quan trọng để đủ độ phủ theo yêu cầu.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-PAY-001 | TS-PAY-01 – Tính và lưu cước | Tính cước cho chuyến hoàn thành | Trip tồn tại và COMPLETED. | 1. POST /trips/{tripId}/fare/calculate.<br>2. Kiểm tra kết quả. | tripId: TRIP001 | Hệ thống tính và lưu cước cuối cùng. | High |
| TC-PAY-002 | TS-PAY-01 – Tính và lưu cước | Tính cước khi chuyến chưa hoàn thành | Trip đang IN_PROGRESS. | 1. Gửi yêu cầu tính cước cuối cùng.<br>2. Kiểm tra kết quả. | tripId: TRIP002 | Hệ thống từ chối theo BRULE06. | High |
| TC-PAY-003 | TS-PAY-01 – Tính và lưu cước | Trip không tồn tại | User đã đăng nhập. | 1. Tính cước TRIP999.<br>2. Kiểm tra kết quả. | tripId: TRIP999 | Hệ thống báo không tìm thấy. | High |
| TC-PAY-004 | TS-PAY-02 – Chọn phương thức và thanh toán | Chọn CASH | Payment tồn tại. | 1. PATCH /payments/{paymentId}/method.<br>2. Gửi CASH. | method: CASH | Hệ thống ghi nhận CASH theo BRULE07. | High |
| TC-PAY-005 | TS-PAY-02 – Chọn phương thức và thanh toán | Chọn ELECTRONIC | Payment tồn tại. | 1. PATCH method.<br>2. Gửi ELECTRONIC. | method: ELECTRONIC | Hệ thống ghi nhận ELECTRONIC theo BRULE07. | High |
| TC-PAY-006 | TS-PAY-02 – Chọn phương thức và thanh toán | Method rỗng | Payment tồn tại. | 1. Gửi method rỗng.<br>2. Kiểm tra kết quả. | method: empty | Hệ thống báo dữ liệu không hợp lệ. | High |
| TC-PAY-007 | TS-PAY-02 – Chọn phương thức và thanh toán | Method ngoài enum | Payment tồn tại. | 1. Gửi method không hợp lệ.<br>2. Kiểm tra kết quả. | method: CRYPTO | Hệ thống từ chối; chỉ hỗ trợ CASH/ELECTRONIC. | High |
| TC-PAY-008 | TS-PAY-02 – Chọn phương thức và thanh toán | Thanh toán tiền mặt hợp lệ | Trip đã hoàn thành; có số tiền cần thanh toán. | 1. POST /payments/cash.<br>2. Gửi tripId và amount hợp lệ. | tripId: TRIP001<br>amount: 50000 | Ghi nhận thanh toán tiền mặt. | High |
| TC-PAY-009 | TS-PAY-02 – Chọn phương thức và thanh toán | Thanh toán điện tử hợp lệ | Trip đã hoàn thành; provider hoạt động. | 1. POST /payments/electronic.<br>2. Gửi tripId, amount.<br>3. Kiểm tra kết quả. | tripId: TRIP001<br>amount: 50000 | Gửi yêu cầu đến provider và nhận kết quả. | High |
| TC-PAY-010 | TS-PAY-02 – Chọn phương thức và thanh toán | Amount rỗng | Trip tồn tại. | 1. Gửi payment nhưng bỏ amount.<br>2. Kiểm tra kết quả. | amount: null | Hệ thống báo dữ liệu không hợp lệ. | High |
| TC-PAY-011 | TS-PAY-03 – Xử lý thanh toán thất bại và retry | Provider trả kết quả thất bại | Có thanh toán điện tử. | 1. Provider trả FAILED.<br>2. Ghi nhận lỗi.<br>3. Kiểm tra trạng thái. | result: FAILED | Giao dịch được ghi FAILED; không ghi đã thanh toán. | High |
| TC-PAY-012 | TS-PAY-03 – Xử lý thanh toán thất bại và retry | Thông báo khi thanh toán thất bại | Payment đã FAILED. | 1. Ghi nhận failed.<br>2. Kiểm tra notification. | reason: Payment failed | Khách hàng nhận thông báo theo EX04. | High |
| TC-PAY-013 | TS-PAY-03 – Xử lý thanh toán thất bại và retry | Retry thanh toán thất bại | Payment FAILED; chính sách cho phép xử lý lại. | 1. POST /payments/{paymentId}/retry.<br>2. Kiểm tra kết quả. | paymentId: PAY001 | Hệ thống cho phép xử lý lại theo EX04. | High |
| TC-PAY-014 | TS-PAY-03 – Xử lý thanh toán thất bại và retry | Provider mất kết nối | Provider không phản hồi. | 1. Mô phỏng mất kết nối.<br>2. Thử thanh toán.<br>3. Kiểm tra hệ thống. | Provider: unavailable | Xử lý theo EX05; hệ thống chính vẫn hoạt động. | High |
| TC-PAY-015 | TS-PAY-03 – Xử lý thanh toán thất bại và retry | Không lưu dữ liệu thanh toán nhạy cảm | Đã thanh toán điện tử. | 1. Kiểm tra dữ liệu Payment/log.<br>2. Kiểm tra thông tin nhạy cảm. | Dữ liệu thẻ/tài khoản thanh toán | CAB không lưu trực tiếp dữ liệu nhạy cảm theo BRULE08. | Medium |
