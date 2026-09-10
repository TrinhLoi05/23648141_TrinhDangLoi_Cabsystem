# TEST CASE – AUTHORIZATION

## 1. Thông tin chung

**Module:** Authorization / Permission / Audit Log  
**Business Requirement:** BR18, BR20

Functional Requirements:

- FR18.01 – Xác thực.
- FR18.02 – Phân quyền.
- FR18.03 – Kiểm soát quản trị.
- FR20.01 – Ghi log.
- FR20.02 – Tra cứu log.

---

## 2. Test Cases

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-AUTHZ-01 | TS-AUTHZ-01 – Xác thực token hợp lệ | FR18.01 | Người dùng đã đăng nhập | Token hợp lệ | Gửi token đến chức năng xác thực | Người dùng được xác thực thành công | High | Not Run |
| TC-AUTHZ-02 | TS-AUTHZ-02 – Token không hợp lệ | FR18.01 | Có token | Token sai | Gửi token không hợp lệ | Hệ thống từ chối truy cập | High | Not Run |
| TC-AUTHZ-03 | TS-AUTHZ-03 – Token hết hạn | FR18.01 | Token đã hết hạn | Expired Token | Gửi token hết hạn | Hệ thống yêu cầu đăng nhập lại | High | Not Run |
| TC-AUTHZ-04 | TS-AUTHZ-04 – Admin phân quyền | FR18.02 | Admin đã đăng nhập | userId=USR001, role=DRIVER | Chọn người dùng → chọn DRIVER → lưu | Vai trò DRIVER được cập nhật | High | Not Run |
| TC-AUTHZ-05 | TS-AUTHZ-05 – Người không phải Admin phân quyền | FR18.02 | Customer đã đăng nhập | role=DRIVER | Gửi yêu cầu phân quyền | Hệ thống từ chối thao tác | High | Not Run |
| TC-AUTHZ-06 | TS-AUTHZ-06 – Vai trò không hợp lệ | FR18.02 | Admin đã đăng nhập | role=ABC | Gửi yêu cầu cập nhật role | Hệ thống báo vai trò không hợp lệ | Medium | Not Run |
| TC-AUTHZ-07 | TS-AUTHZ-07 – Có quyền thao tác quản trị | FR18.03 | User có quyền | resource=DRIVER, action=UPDATE | Kiểm tra quyền | allowed = true | High | Not Run |
| TC-AUTHZ-08 | TS-AUTHZ-08 – Không có quyền | FR18.03 | User không có quyền | resource=DRIVER, action=DELETE | Kiểm tra quyền | Hệ thống từ chối thao tác | High | Not Run |
| TC-AUTHZ-09 | TS-AUDIT-01 – Ghi thao tác quan trọng | FR20.01 | User đã xác thực | action=UPDATE_DRIVER | Thực hiện thao tác → kiểm tra log | Audit Log được tạo | Medium | Not Run |
| TC-AUTHZ-10 | TS-AUDIT-02 – Ghi log thay đổi quyền | FR20.01 | Admin đã đăng nhập | UPDATE_ROLE | Thay đổi role → kiểm tra log | Có log thay đổi quyền | High | Not Run |
| TC-AUTHZ-11 | TS-AUDIT-05 – Tra cứu Audit Log | FR20.02 | Admin đã đăng nhập | Không | Mở danh sách Audit Log | Danh sách log được hiển thị | Medium | Not Run |
| TC-AUTHZ-12 | TS-AUDIT-06 – Tra cứu log theo user | FR20.02 | Admin đã đăng nhập | userId=USR001 | Nhập userId → tìm kiếm | Chỉ hiển thị log của USR001 | Medium | Not Run |
| TC-AUTHZ-13 | TS-AUDIT-07 – Tra cứu theo thời gian | FR20.02 | Admin đã đăng nhập | fromDate, toDate | Chọn khoảng thời gian → tìm | Hiển thị đúng log trong khoảng thời gian | Medium | Not Run |
| TC-AUTHZ-14 | TS-AUDIT-08 – Không có quyền xem log | FR20.02 | Customer đã đăng nhập | Không | Truy cập Audit Log | Hệ thống từ chối truy cập | High | Not Run |

---

## 3. Traceability

| FR | API |
|---|---|
| FR18.01 | POST /authorization/verify |
| FR18.02 | PUT /authorization/users/{userId}/role |
| FR18.03 | POST /authorization/check |
| FR20.01 | POST /audit-logs |
| FR20.02 | GET /audit-logs |
