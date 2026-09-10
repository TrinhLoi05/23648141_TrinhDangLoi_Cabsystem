# TEST CASE – NOTIFICATION

## 1. Thông tin chung

**Module:** Notification  
**Business Requirement:** BR13 – Thông báo

---

## 2. Test Cases

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-NOTI-01 | TS-NOTI-01 – Thông báo đặt xe | FR13.01 | Booking được tiếp nhận | BOOKING_RECEIVED | Tạo chuyến | Customer nhận thông báo | High | Not Run |
| TC-NOTI-02 | TS-NOTI-02 – Tài xế nhận chuyến | FR13.02 | Driver chấp nhận | DRIVER_ASSIGNED | Driver accept | Customer nhận thông báo | High | Not Run |
| TC-NOTI-03 | TS-NOTI-03 – Tài xế đến | FR13.03 | Driver đã đến | DRIVER_ARRIVED | Cập nhật trạng thái | Customer nhận thông báo | High | Not Run |
| TC-NOTI-04 | TS-NOTI-04 – Hoàn thành chuyến | FR13.04 | Trip đang chạy | COMPLETED | Hoàn thành chuyến | Customer nhận thông báo | High | Not Run |
| TC-NOTI-05 | TS-NOTI-05 – Thanh toán thành công | FR13.05 | Payment SUCCESS | SUCCESS | Thanh toán | Nhận thông báo thành công | High | Not Run |
| TC-NOTI-06 | TS-NOTI-06 – Thanh toán thất bại | FR13.05 | Payment FAILED | FAILED | Thanh toán | Nhận thông báo thất bại | High | Not Run |
| TC-NOTI-07 | TS-NOTI-07 – Provider thông báo lỗi | FR13.01-FR13.05 | Notification Provider lỗi | Provider unavailable | Phát sinh sự kiện | Chức năng chính vẫn tiếp tục | High | Not Run |
| TC-NOTI-08 | TS-NOTI-08 – Đúng người nhận | FR13.01-FR13.05 | Có nhiều người dùng | userId=CUS001 | Gửi thông báo | Chỉ đúng người dùng nhận | High | Not Run |

---

## 3. Traceability

| FR | API |
|---|---|
| FR13.01 | POST /notifications |
| FR13.02 | POST /notifications |
| FR13.03 | POST /notifications |
| FR13.04 | POST /notifications |
| FR13.05 | POST /notifications |
