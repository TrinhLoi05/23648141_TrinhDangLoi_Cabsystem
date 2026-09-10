# TEST CASE – DRIVER

## 1. Thông tin chung

**Module:** Driver / Vehicle  
**Business Requirement:** BR03, BR04

---

## 2. Test Cases

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-DRIVER-01 | TS-DRIVER-01 – Tạo tài xế hợp lệ | FR03.03 | Operator/Admin đã đăng nhập | Driver hợp lệ | Nhập thông tin → tạo | Tài khoản tài xế được tạo | High | Not Run |
| TC-DRIVER-02 | TS-DRIVER-02 – Thiếu dữ liệu | FR03.03 | Có quyền | phone=null | Gửi yêu cầu tạo | Hệ thống báo lỗi | High | Not Run |
| TC-DRIVER-03 | TS-DRIVER-03 – Phone đã tồn tại | FR03.03 | Phone tồn tại | 0912345678 | Tạo tài xế | Hệ thống từ chối | High | Not Run |
| TC-DRIVER-04 | TS-DRIVER-04 – Cập nhật hồ sơ | FR03.01 | Driver tồn tại | Tên mới | Sửa → lưu | Hồ sơ được cập nhật | Medium | Not Run |
| TC-DRIVER-05 | TS-DRIVER-05 – Driver không tồn tại | FR03.01 | Không có DRV999 | DRV999 | Cập nhật | Hệ thống báo không tìm thấy | Medium | Not Run |
| TC-DRIVER-06 | TS-DRIVER-06 – AVAILABLE | FR03.02 | Driver đã đăng nhập | AVAILABLE | Đổi trạng thái | status=AVAILABLE | High | Not Run |
| TC-DRIVER-07 | TS-DRIVER-07 – BUSY | FR03.02 | Driver đã đăng nhập | BUSY | Đổi trạng thái | status=BUSY | Medium | Not Run |
| TC-DRIVER-08 | TS-DRIVER-08 – OFFLINE | FR03.02 | Driver đã đăng nhập | OFFLINE | Đổi trạng thái | status=OFFLINE | Medium | Not Run |
| TC-DRIVER-09 | TS-DRIVER-09 – Status không hợp lệ | FR03.02 | Driver tồn tại | ABC | Cập nhật | Hệ thống báo lỗi | Medium | Not Run |
| TC-DRIVER-10 | TS-DRIVER-10 – Thêm phương tiện | FR04.01 | Driver tồn tại | 51A-123.45 | Thêm xe | Xe được lưu | High | Not Run |
| TC-DRIVER-11 | TS-DRIVER-11 – Biển số trùng | FR04.01 | Biển số tồn tại | 51A-123.45 | Thêm xe | Hệ thống từ chối | High | Not Run |
| TC-DRIVER-12 | TS-DRIVER-12 – Cập nhật phương tiện | FR04.02 | Vehicle tồn tại | Màu=Đen | Sửa → lưu | Xe được cập nhật | Medium | Not Run |
| TC-DRIVER-13 | TS-DRIVER-13 – Vehicle không tồn tại | FR04.02 | VEH999 không tồn tại | VEH999 | Cập nhật | Báo không tìm thấy | Medium | Not Run |

---

## 3. Traceability

| FR | API |
|---|---|
| FR03.01 | PATCH /drivers/{driverId} |
| FR03.02 | PATCH /drivers/{driverId}/availability |
| FR03.03 | POST /drivers |
| FR04.01 | POST /drivers/{driverId}/vehicles |
| FR04.02 | PATCH /vehicles/{vehicleId} |
