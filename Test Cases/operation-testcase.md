# TEST CASE – OPERATION

> Bộ Test Case cơ bản cho người mới học. Chỉ giữ các case quan trọng để đủ độ phủ theo yêu cầu.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-OPS-001 | TS-OPS-01 – Xem dữ liệu vận hành | Operator xem dữ liệu khi có dữ liệu | Operator đã đăng nhập và có quyền. | 1. Gọi một API GET /operations/*.<br>2. Kiểm tra danh sách. | Ví dụ: GET /operations/trips | Hiển thị dữ liệu phù hợp. | High |
| TC-OPS-002 | TS-OPS-01 – Xem dữ liệu vận hành | Danh sách không có dữ liệu | Operator có quyền; dữ liệu rỗng. | 1. Gọi API danh sách.<br>2. Kiểm tra kết quả. | Dataset: empty | Trả danh sách rỗng; không lỗi. | Medium |
| TC-OPS-003 | TS-OPS-01 – Xem dữ liệu vận hành | Người không có quyền truy cập | Customer đã đăng nhập. | 1. Customer gọi /operations/*.<br>2. Kiểm tra kết quả. | Token Customer | Hệ thống từ chối theo BRULE10/EX07. | High |
| TC-OPS-004 | TS-OPS-01 – Xem dữ liệu vận hành | Không đăng nhập | Không có token. | 1. Gọi /operations/* không có token.<br>2. Kiểm tra kết quả. | Authorization: missing | Hệ thống từ chối theo BRULE01. | High |
| TC-OPS-005 | TS-OPS-02 – Xử lý sự cố và tra cứu giao dịch | Xử lý sự cố hợp lệ | Operator có quyền; incident tồn tại. | 1. PATCH /operations/incidents/{incidentId}.<br>2. Gửi action hợp lệ.<br>3. Kiểm tra dữ liệu. | incidentId: INC001<br>action: REASSIGN_DRIVER | Lưu kết quả xử lý. | High |
| TC-OPS-006 | TS-OPS-02 – Xử lý sự cố và tra cứu giao dịch | Action rỗng | Operator có quyền; incident tồn tại. | 1. Để action rỗng.<br>2. Gửi request. | action: empty | Hệ thống báo dữ liệu không hợp lệ. | High |
| TC-OPS-007 | TS-OPS-02 – Xử lý sự cố và tra cứu giao dịch | Incident không tồn tại | Operator có quyền. | 1. PATCH incidentId không tồn tại.<br>2. Kiểm tra kết quả. | incidentId: INC999 | Hệ thống báo không tìm thấy. | High |
| TC-OPS-008 | TS-OPS-02 – Xử lý sự cố và tra cứu giao dịch | Tra cứu giao dịch tồn tại | Operator có quyền; transaction tồn tại. | 1. GET /operations/transactions/{transactionId}.<br>2. Kiểm tra kết quả. | transactionId: PAY001 | Hiển thị đúng trạng thái giao dịch. | High |
| TC-OPS-009 | TS-OPS-02 – Xử lý sự cố và tra cứu giao dịch | Ghi log thao tác xử lý sự cố | Operator vừa xử lý sự cố thành công. | 1. Xử lý incident.<br>2. Kiểm tra Audit Log. | action: HANDLE_INCIDENT | Thao tác được ghi log theo BRULE11. | Medium |
