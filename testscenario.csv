# TEST SCENARIO – CAB SYSTEM

## 1. Nguyên tắc

Test Scenario được sinh từ API + Functional Requirement + Business Rule + Business Exception.

Với mỗi Test Scenario, Test Case sẽ bao phủ các nhóm **cơ bản, dễ hiểu** sau nếu có áp dụng:

- Dữ liệu đúng/hợp lệ.
- Dữ liệu rỗng hoặc thiếu trường bắt buộc.
- Dữ liệu không hợp lệ: sai kiểu, sai enum, ID không tồn tại.
- Giá trị biên **chỉ khi API có định nghĩa biên**.
- Business Rule liên quan.
- Business Exception liên quan.
- Chưa đăng nhập/không có quyền đối với API bảo vệ.

> Không tự đặt các con số đang TBD như thời gian phản hồi tài xế, số lần retry, công thức tính cước... Khi test sẽ dùng giá trị đã được xác nhận.

---

## 2. Danh sách Test Scenario

| Test Scenario ID | Nhóm | API | Test Scenario | Độ phủ cần có | Business Rule / Exception |
|---|---|---|---|---|---|
| TS-AUTH-01 | AUTH | POST /auth/register | Đăng ký tài khoản khách hàng | Đúng; rỗng; sai định dạng/kiểu; dữ liệu trùng | EX08 |
| TS-AUTH-02 | AUTH | POST /auth/login | Đăng nhập khách hàng | Đúng; rỗng; sai thông tin | BRULE01, EX08 |
| TS-AUTH-03 | AUTH | PATCH /customers/{customerId} | Cập nhật thông tin khách hàng | Đúng; sai dữ liệu; chưa đăng nhập; sai quyền | BRULE01, BRULE10, EX07, EX08 |
| TS-AUTHZ-01 | AUTHORIZATION | POST /authorization/verify + /authorization/check | Xác thực và kiểm tra quyền | Token đúng/sai/rỗng; được quyền/không được quyền | BRULE01, BRULE10, EX07 |
| TS-AUTHZ-02 | AUTHORIZATION | PUT /authorization/users/{userId}/role | Phân quyền người dùng | Role đúng/rỗng/sai enum; quyền; Audit Log | BRULE10, BRULE11, EX07, EX08 |
| TS-AUDIT-01 | AUTHORIZATION | POST/GET /audit-logs | Ghi và tra cứu Audit Log | Đúng; rỗng; tra cứu; phân quyền | BRULE11, BRULE10, EX07, EX08 |
| TS-BOOK-01 | BOOKING | POST /bookings/validate + POST /bookings | Kiểm tra và tạo yêu cầu đặt chuyến | Đúng; dữ liệu bắt buộc rỗng; chưa đăng nhập | BRULE01, EX08 |
| TS-DRIVER-01 | DRIVER | POST/PATCH /drivers | Quản lý hồ sơ tài xế | Đúng; dữ liệu rỗng; cập nhật; phân quyền | BRULE10, EX07, EX08 |
| TS-DRIVER-02 | DRIVER | PATCH /drivers/{driverId}/availability | Cập nhật trạng thái sẵn sàng | AVAILABLE/BUSY/OFFLINE; rỗng; sai enum; BRULE02 | BRULE02, EX08 |
| TS-VEHICLE-01 | DRIVER | POST /drivers/{driverId}/vehicles + PATCH /vehicles/{vehicleId} | Quản lý phương tiện | Đúng; trường bắt buộc rỗng; ID không tồn tại | EX08 |
| TS-RATE-01 | HISTORY-RATING | POST /trips/{tripId}/ratings | Đánh giá tài xế | Đúng; rỗng; biên 1 và 5; ngoài biên; BRULE09; phân quyền | BRULE09, BRULE10, EX07, EX08 |
| TS-NOTI-01 | NOTIFICATION | POST /notifications | Gửi thông báo theo sự kiện | Đúng từng event; rỗng; sai enum; mất kết nối | EX05, EX08 |
| TS-OPS-01 | OPERATION | GET /operations/* | Xem dữ liệu vận hành | Có dữ liệu; không có dữ liệu; chưa đăng nhập; sai quyền | BRULE01, BRULE10, EX07 |
| TS-OPS-02 | OPERATION | PATCH incidents + GET transactions | Xử lý sự cố và giao dịch | Đúng; rỗng; ID không tồn tại; Audit Log | BRULE11, EX08 |
| TS-PAY-01 | PAYMENT | POST /trips/{tripId}/fare/calculate | Tính và lưu cước | Trip hoàn thành/chưa hoàn thành; ID không tồn tại | BRULE06 |
| TS-PAY-02 | PAYMENT | PATCH method + POST cash/electronic | Chọn phương thức và thanh toán | CASH/ELECTRONIC; rỗng; sai enum; thanh toán đúng | BRULE07, EX08 |
| TS-PAY-03 | PAYMENT | failed + retry | Xử lý thanh toán thất bại | FAILED; thông báo; retry; mất kết nối; dữ liệu nhạy cảm | BRULE08, EX04, EX05 |
| TS-REPORT-01 | REPORT | GET /reports/* | Xem báo cáo hoạt động | Đúng từng báo cáo; dữ liệu rỗng; phân quyền | BRULE10, EX07 |
| TS-TRIP-01 | TRIP | POST /trips/{tripId}/matching | Tìm tài xế | AVAILABLE; BUSY; lỗi vị trí; không có Driver | BRULE02, BRULE05, EX01, EX06 |
| TS-TRIP-02 | TRIP | offer/accept/reject/retry/fail | Phân công tài xế | Offer; accept; 1 Trip-1 Driver; reject; timeout; không còn Driver | BRULE03, BRULE04, BRULE05, EX01, EX02, EX03 |
| TS-TRIP-03 | TRIP | GET trip + tracking | Xem và theo dõi chuyến | Đúng; sai quyền; có/không vị trí | BRULE10, EX06, EX07 |
| TS-TRIP-04 | TRIP | PATCH /trips/{tripId}/status | Cập nhật trạng thái chuyến | Các trạng thái hợp lệ; rỗng; sai enum; sai quyền | BRULE10, EX07, EX08 |
| TS-TRIP-05 | TRIP | POST /drivers/{driverId}/locations | Cập nhật vị trí tài xế | Đúng; rỗng; sai kiểu; mất kết nối | EX05, EX08 |

---

## 3. Liên kết Test Scenario → Test Case

| Test Scenario | File Test Case |
|---|---|
| TS-AUTH-* | Test Cases/auth-testcase.md |
| TS-AUTHZ-* / TS-AUDIT-* | Test Cases/authorization-testcase.md |
| TS-BOOK-* | Test Cases/booking-testcase.md |
| TS-DRIVER-* / TS-VEHICLE-* | Test Cases/driver-testcase.md |
| TS-RATE-* | Test Cases/history-rating-testcase.md |
| TS-NOTI-* | Test Cases/notification-testcase.md |
| TS-OPS-* | Test Cases/operation-testcase.md |
| TS-PAY-* | Test Cases/payment-testcase.md |
| TS-REPORT-* | Test Cases/report-testcase.md |
| TS-TRIP-* | Test Cases/trip-testcase.md |
