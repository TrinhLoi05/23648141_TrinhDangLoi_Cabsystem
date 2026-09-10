# TEST CASE – BOOKING

## 1. Thông tin chung

**Module:** Booking  
**Business Requirement:** BR01 – Đặt chuyến xe

Functional Requirements:

- FR01.01 – Nhập điểm đón.
- FR01.02 – Nhập điểm đến.
- FR01.03 – Chọn loại xe.
- FR01.04 – Gửi yêu cầu.
- FR01.05 – Kiểm tra yêu cầu.
- FR01.06 – Tạo chuyến.

---

## 2. Test Cases

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-BOOK-01 | TS-BOOK-01 – Nhập điểm đón hợp lệ | FR01.01 | Customer đã đăng nhập | IUH, Gò Vấp | Nhập điểm đón | Hệ thống ghi nhận điểm đón | High | Not Run |
| TC-BOOK-02 | TS-BOOK-02 – Không nhập điểm đón | FR01.01 | Customer đã đăng nhập | pickup=null | Để trống điểm đón → gửi | Hệ thống báo thiếu điểm đón | High | Not Run |
| TC-BOOK-03 | TS-BOOK-03 – Nhập điểm đến hợp lệ | FR01.02 | Customer đã đăng nhập | Sân bay Tân Sơn Nhất | Nhập điểm đến | Hệ thống ghi nhận điểm đến | High | Not Run |
| TC-BOOK-04 | TS-BOOK-04 – Không nhập điểm đến | FR01.02 | Customer đã đăng nhập | destination=null | Để trống → gửi | Hệ thống báo thiếu điểm đến | High | Not Run |
| TC-BOOK-05 | TS-BOOK-05 – Chọn loại xe hợp lệ | FR01.03 | Customer đã đăng nhập | CAR_4_SEAT | Chọn loại xe | Hệ thống ghi nhận loại xe | High | Not Run |
| TC-BOOK-06 | TS-BOOK-06 – Không chọn loại xe | FR01.03 | Customer đã đăng nhập | vehicleType=null | Gửi yêu cầu | Hệ thống báo lỗi | High | Not Run |
| TC-BOOK-07 | TS-BOOK-07 – Validate dữ liệu hợp lệ | FR01.05 | Đã nhập đủ dữ liệu | Pickup + destination + vehicle | Nhấn xác nhận | valid=true | High | Not Run |
| TC-BOOK-08 | TS-BOOK-08 – Validate dữ liệu lỗi | FR01.05 | Customer đã đăng nhập | Thiếu destination | Nhấn xác nhận | Hệ thống thông báo dữ liệu không hợp lệ | High | Not Run |
| TC-BOOK-09 | TS-BOOK-09 – Gửi yêu cầu hợp lệ | FR01.04, FR01.06 | Dữ liệu hợp lệ | Đầy đủ dữ liệu | Nhấn Đặt xe | Chuyến được tạo thành công | High | Not Run |
| TC-BOOK-10 | TS-BOOK-10 – Kiểm tra trạng thái chuyến mới | FR01.06 | Chuyến vừa tạo | TRIP001 | Xem chuyến | status=SEARCHING_DRIVER | High | Not Run |
| TC-BOOK-11 | TS-BOOK-11 – Đặt xe khi chưa đăng nhập | FR01.04 | Chưa đăng nhập | Không token | Gửi yêu cầu đặt xe | Hệ thống từ chối | High | Not Run |

---

## 3. Traceability

| FR | API |
|---|---|
| FR01.01 | POST /bookings |
| FR01.02 | POST /bookings |
| FR01.03 | POST /bookings |
| FR01.04 | POST /bookings |
| FR01.05 | POST /bookings/validate |
| FR01.06 | POST /bookings |
