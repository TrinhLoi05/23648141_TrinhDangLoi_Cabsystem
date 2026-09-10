# TEST CASE – OPERATION

## 1. Thông tin chung

**Module:** Operation  
**Business Requirement:** BR15, BR16, BR17

---

## 2. Test Cases

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-OPS-01 | TS-OPS-01 – Xem khách hàng | FR15.01 | Operator đăng nhập | Không | Mở quản lý khách hàng | Danh sách hiển thị | Medium | Not Run |
| TC-OPS-02 | TS-OPS-02 – Xem tài xế | FR15.02 | Operator đăng nhập | Không | Mở quản lý tài xế | Danh sách hiển thị | Medium | Not Run |
| TC-OPS-03 | TS-OPS-03 – Xem phương tiện | FR15.03 | Operator đăng nhập | Không | Mở phương tiện | Danh sách hiển thị | Medium | Not Run |
| TC-OPS-04 | TS-OPS-04 – Theo dõi chuyến | FR15.04 | Operator đăng nhập | Trip đang hoạt động | Mở danh sách chuyến | Hiển thị trạng thái chuyến | High | Not Run |
| TC-OPS-05 | TS-OPS-05 – Không có quyền Operation | FR15.01-FR15.04 | Customer đăng nhập | Không | Truy cập Operation | Hệ thống từ chối | High | Not Run |
| TC-OPS-06 | TS-OPS-06 – Xem chuyến lỗi | FR16.01 | Có incident | Không | Mở danh sách sự cố | Hiển thị chuyến lỗi | High | Not Run |
| TC-OPS-07 | TS-OPS-07 – Xử lý sự cố | FR16.02 | Incident tồn tại | REASSIGN_DRIVER | Chọn sự cố → xử lý | Kết quả được lưu | High | Not Run |
| TC-OPS-08 | TS-OPS-08 – Xử lý khi không có quyền | FR16.02 | User không có quyền | Không | Xử lý incident | Hệ thống từ chối | High | Not Run |
| TC-OPS-09 | TS-OPS-09 – Tra cứu giao dịch | FR17.01 | Operator đăng nhập | Không | Mở danh sách giao dịch | Danh sách hiển thị | Medium | Not Run |
| TC-OPS-10 | TS-OPS-10 – Xem trạng thái giao dịch | FR17.02 | Transaction tồn tại | PAY001 | Chọn giao dịch | Hiển thị đúng trạng thái | Medium | Not Run |
| TC-OPS-11 | TS-OPS-11 – Giao dịch không tồn tại | FR17.02 | PAY999 không tồn tại | PAY999 | Tra cứu | Hệ thống báo không tìm thấy | Medium | Not Run |

---

## 3. Traceability

| FR | API |
|---|---|
| FR15.01 | GET /operations/customers |
| FR15.02 | GET /operations/drivers |
| FR15.03 | GET /operations/vehicles |
| FR15.04 | GET /operations/trips |
| FR16.01 | GET /operations/incidents |
| FR16.02 | PATCH /operations/incidents/{incidentId} |
| FR17.01 | GET /operations/transactions |
| FR17.02 | GET /operations/transactions/{transactionId} |
