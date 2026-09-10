# TEST CASE – PAYMENT

## 1. Thông tin chung

**Module:** Fare & Payment  
**Business Requirement:** BR10, BR11, BR12

---

## 2. Test Cases

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-PAY-01 | TS-PAY-01 – Xác định dịch vụ | FR10.02 | Trip tồn tại | CAR_4_SEAT | Tính cước | Hệ thống xác định đúng dịch vụ | High | Not Run |
| TC-PAY-02 | TS-PAY-02 – Tính cước | FR10.01 | Trip=COMPLETED | TRIP001 | Yêu cầu tính cước | Hệ thống trả số tiền | High | Not Run |
| TC-PAY-03 | TS-PAY-03 – Lưu cước | FR10.03 | Đã tính cước | fare hợp lệ | Tính → lưu | Fare được lưu với Trip | High | Not Run |
| TC-PAY-04 | TS-PAY-04 – Trip không hợp lệ | FR10.01 | Trip không hợp lệ | TRIP999 | Tính cước | Hệ thống từ chối | Medium | Not Run |
| TC-PAY-05 | TS-PAY-05 – Chọn tiền mặt | FR11.01 | Có payment | CASH | Chọn phương thức | method=CASH | High | Not Run |
| TC-PAY-06 | TS-PAY-06 – Thanh toán tiền mặt | FR11.02 | Trip hoàn thành | amount hợp lệ | Xác nhận CASH | Giao dịch được ghi nhận | High | Not Run |
| TC-PAY-07 | TS-PAY-07 – Chọn điện tử | FR11.01 | Có payment | ELECTRONIC | Chọn phương thức | method=ELECTRONIC | High | Not Run |
| TC-PAY-08 | TS-PAY-08 – Điện tử thành công | FR11.03 | Provider hoạt động | amount hợp lệ | Thanh toán | Provider xử lý thành công | High | Not Run |
| TC-PAY-09 | TS-PAY-09 – Nhận kết quả | FR11.04 | Payment SUCCESS | PAY001 | Xem payment | status=PAID/SUCCESS | High | Not Run |
| TC-PAY-10 | TS-PAY-10 – Giao dịch thất bại | FR12.01 | Provider trả FAILED | PAY001 | Nhận callback/kết quả | status=FAILED | High | Not Run |
| TC-PAY-11 | TS-PAY-11 – Thông báo lỗi | FR12.02 | Payment FAILED | FAILED | Kiểm tra kết quả | Customer nhận thông báo | High | Not Run |
| TC-PAY-12 | TS-PAY-12 – Thanh toán lại | FR12.03 | Payment FAILED | PAY001 | Chọn Retry | Hệ thống xử lý lần thanh toán lại | High | Not Run |
| TC-PAY-13 | TS-PAY-13 – Provider mất kết nối | FR11.03 | Provider unavailable | Không | Thanh toán điện tử | Booking và Trip không bị dừng toàn hệ thống | High | Not Run |
| TC-PAY-14 | TS-PAY-14 – Không lưu dữ liệu thẻ | FR11.03 | Thanh toán điện tử | Card data | Kiểm tra dữ liệu lưu | Không lưu thông tin thẻ nhạy cảm | High | Not Run |

---

## 3. Traceability

| FR | API |
|---|---|
| FR10.01 | POST /trips/{tripId}/fare/calculate |
| FR10.02 | POST /trips/{tripId}/fare/calculate |
| FR10.03 | POST /trips/{tripId}/fare/calculate |
| FR11.01 | PATCH /payments/{paymentId}/method |
| FR11.02 | POST /payments/cash |
| FR11.03 | POST /payments/electronic |
| FR11.04 | GET /payments/{paymentId} |
| FR12.01 | PATCH /payments/{paymentId}/failed |
| FR12.02 | PATCH /payments/{paymentId}/failed |
| FR12.03 | POST /payments/{paymentId}/retry |
