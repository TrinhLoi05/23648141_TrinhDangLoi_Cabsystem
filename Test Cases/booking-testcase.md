# TEST CASE – BOOKING

> Bộ Test Case cơ bản cho người mới học. Chỉ giữ các case quan trọng để đủ độ phủ theo yêu cầu.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-BOOK-001 | TS-BOOK-01 – Kiểm tra và tạo yêu cầu đặt chuyến | Dữ liệu đặt chuyến hợp lệ | Customer đã đăng nhập. | 1. POST /bookings/validate.<br>2. Gửi đủ điểm đón, điểm đến, loại xe. | pickupLocation: IUH<br>destination: Sân bay<br>vehicleType: CAR_4_SEAT | Dữ liệu được xác nhận hợp lệ. | High |
| TC-BOOK-002 | TS-BOOK-01 – Kiểm tra và tạo yêu cầu đặt chuyến | Điểm đón rỗng | Customer đã đăng nhập. | 1. Để pickupLocation rỗng.<br>2. Gửi validate. | pickupLocation: empty | Hệ thống báo dữ liệu không hợp lệ. | High |
| TC-BOOK-003 | TS-BOOK-01 – Kiểm tra và tạo yêu cầu đặt chuyến | Điểm đến rỗng | Customer đã đăng nhập. | 1. Để destination rỗng.<br>2. Gửi validate. | destination: empty | Hệ thống báo dữ liệu không hợp lệ. | High |
| TC-BOOK-004 | TS-BOOK-01 – Kiểm tra và tạo yêu cầu đặt chuyến | Loại xe rỗng | Customer đã đăng nhập. | 1. Để vehicleType rỗng.<br>2. Gửi validate. | vehicleType: empty | Hệ thống báo dữ liệu không hợp lệ. | High |
| TC-BOOK-005 | TS-BOOK-01 – Kiểm tra và tạo yêu cầu đặt chuyến | Tạo chuyến với dữ liệu hợp lệ | Customer đã đăng nhập; dữ liệu đã hợp lệ. | 1. POST /bookings.<br>2. Gửi dữ liệu đặt xe.<br>3. Kiểm tra Trip. | pickupLocation: IUH<br>destination: Sân bay<br>vehicleType: CAR_4_SEAT | Tạo chuyến thành công; lưu thông tin đặt xe; bắt đầu tìm tài xế. | High |
| TC-BOOK-006 | TS-BOOK-01 – Kiểm tra và tạo yêu cầu đặt chuyến | Tạo chuyến khi chưa đăng nhập | Không có token. | 1. POST /bookings không có token.<br>2. Kiểm tra kết quả. | Authorization: missing | Hệ thống từ chối theo BRULE01. | High |
