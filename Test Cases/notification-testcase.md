# TEST CASE – NOTIFICATION

> Bộ Test Case cơ bản cho người mới học. Chỉ giữ các case quan trọng để đủ độ phủ theo yêu cầu.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-NOTI-001 | TS-NOTI-01 – Gửi thông báo theo sự kiện | Gửi thông báo BOOKING_RECEIVED | Yêu cầu đặt xe được tiếp nhận | 1. POST /notifications.<br>2. Gửi đúng userId, type, message.<br>3. Kiểm tra thông báo. | userId: CUS001<br>type: BOOKING_RECEIVED<br>message: hợp lệ | Thông báo được gửi đúng sự kiện và đúng người nhận. | High |
| TC-NOTI-002 | TS-NOTI-01 – Gửi thông báo theo sự kiện | Gửi thông báo DRIVER_ASSIGNED | Tài xế nhận chuyến | 1. POST /notifications.<br>2. Gửi đúng userId, type, message.<br>3. Kiểm tra thông báo. | userId: CUS001<br>type: DRIVER_ASSIGNED<br>message: hợp lệ | Thông báo được gửi đúng sự kiện và đúng người nhận. | High |
| TC-NOTI-003 | TS-NOTI-01 – Gửi thông báo theo sự kiện | Gửi thông báo DRIVER_ARRIVED | Tài xế đến điểm đón | 1. POST /notifications.<br>2. Gửi đúng userId, type, message.<br>3. Kiểm tra thông báo. | userId: CUS001<br>type: DRIVER_ARRIVED<br>message: hợp lệ | Thông báo được gửi đúng sự kiện và đúng người nhận. | High |
| TC-NOTI-004 | TS-NOTI-01 – Gửi thông báo theo sự kiện | Gửi thông báo TRIP_COMPLETED | Chuyến hoàn thành | 1. POST /notifications.<br>2. Gửi đúng userId, type, message.<br>3. Kiểm tra thông báo. | userId: CUS001<br>type: TRIP_COMPLETED<br>message: hợp lệ | Thông báo được gửi đúng sự kiện và đúng người nhận. | High |
| TC-NOTI-005 | TS-NOTI-01 – Gửi thông báo theo sự kiện | Gửi thông báo PAYMENT_RESULT | Có kết quả thanh toán | 1. POST /notifications.<br>2. Gửi đúng userId, type, message.<br>3. Kiểm tra thông báo. | userId: CUS001<br>type: PAYMENT_RESULT<br>message: hợp lệ | Thông báo được gửi đúng sự kiện và đúng người nhận. | High |
| TC-NOTI-006 | TS-NOTI-01 – Gửi thông báo theo sự kiện | Thiếu dữ liệu bắt buộc | API Notification hoạt động. | 1. Để userId hoặc type hoặc message rỗng.<br>2. Gửi request. | userId: empty | Hệ thống báo dữ liệu không hợp lệ. | High |
| TC-NOTI-007 | TS-NOTI-01 – Gửi thông báo theo sự kiện | Type ngoài enum | API Notification hoạt động. | 1. Gửi type không hợp lệ.<br>2. Kiểm tra kết quả. | type: UNKNOWN | Hệ thống từ chối dữ liệu. | High |
| TC-NOTI-008 | TS-NOTI-01 – Gửi thông báo theo sự kiện | Notification Provider mất kết nối | Có sự kiện cần gửi; provider lỗi. | 1. Phát sinh sự kiện.<br>2. Mô phỏng provider mất kết nối.<br>3. Kiểm tra chức năng chính. | Provider: unavailable | Xử lý theo EX05; chức năng chính không bị dừng. | High |
