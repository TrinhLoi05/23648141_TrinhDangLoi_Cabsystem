# TEST CASE – AUTHORIZATION

> Bộ Test Case cơ bản cho người mới học. Chỉ giữ các case quan trọng để đủ độ phủ theo yêu cầu.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-AUTHZ-001 | TS-AUTHZ-01 – Xác thực và kiểm tra quyền | Xác thực với token hợp lệ | Người dùng đã đăng nhập. | 1. Gửi POST /authorization/verify với token hợp lệ.<br>2. Kiểm tra kết quả. | Bearer Token: valid | Xác thực thành công. | High |
| TC-AUTHZ-002 | TS-AUTHZ-01 – Xác thực và kiểm tra quyền | Không có token | Người dùng chưa đăng nhập. | 1. Gửi request không có token.<br>2. Kiểm tra kết quả. | Authorization: missing | Hệ thống từ chối theo BRULE01/EX07. | High |
| TC-AUTHZ-003 | TS-AUTHZ-01 – Xác thực và kiểm tra quyền | Token không hợp lệ | Có token nhưng token sai hoặc hết hạn. | 1. Gửi token không hợp lệ.<br>2. Kiểm tra kết quả. | Bearer Token: invalid | Hệ thống từ chối xác thực. | High |
| TC-AUTHZ-004 | TS-AUTHZ-01 – Xác thực và kiểm tra quyền | Người dùng có quyền | User đã được cấp quyền phù hợp. | 1. Gửi POST /authorization/check.<br>2. Gửi resource và action.<br>3. Kiểm tra kết quả. | resource: DRIVER<br>action: UPDATE | Hệ thống cho phép thao tác. | High |
| TC-AUTHZ-005 | TS-AUTHZ-01 – Xác thực và kiểm tra quyền | Người dùng không có quyền | User đã đăng nhập nhưng không có quyền. | 1. Kiểm tra quyền với action không được cấp.<br>2. Kiểm tra kết quả. | resource: AUDIT_LOG<br>action: READ | Hệ thống từ chối theo BRULE10/EX07. | High |
| TC-AUTHZ-006 | TS-AUTHZ-02 – Phân quyền người dùng | Gán vai trò hợp lệ | Admin đã đăng nhập; userId tồn tại. | 1. PUT /authorization/users/{userId}/role.<br>2. Chọn role hợp lệ.<br>3. Kiểm tra kết quả. | userId: USR001<br>role: DRIVER | Vai trò được cập nhật. | High |
| TC-AUTHZ-007 | TS-AUTHZ-02 – Phân quyền người dùng | Role rỗng | Admin đã đăng nhập. | 1. Để role rỗng.<br>2. Gửi request. | role: empty | Hệ thống báo dữ liệu không hợp lệ. | High |
| TC-AUTHZ-008 | TS-AUTHZ-02 – Phân quyền người dùng | Role ngoài danh sách | Admin đã đăng nhập. | 1. Gửi role không thuộc CUSTOMER/DRIVER/OPERATOR/ADMIN.<br>2. Kiểm tra kết quả. | role: SUPERUSER | Hệ thống từ chối dữ liệu. | High |
| TC-AUTHZ-009 | TS-AUTHZ-02 – Phân quyền người dùng | Người không có quyền phân quyền | Customer đã đăng nhập. | 1. Customer gửi yêu cầu đổi role.<br>2. Kiểm tra kết quả. | role: ADMIN | Hệ thống từ chối theo BRULE10. | High |
| TC-AUTHZ-010 | TS-AUTHZ-02 – Phân quyền người dùng | Kiểm tra ghi log sau phân quyền | Admin vừa thay đổi role thành công. | 1. Thay đổi role.<br>2. Kiểm tra Audit Log. | action: UPDATE_ROLE | Có Audit Log theo BRULE11. | Medium |
| TC-AUTHZ-011 | TS-AUDIT-01 – Ghi và tra cứu Audit Log | Ghi Audit Log hợp lệ | Người dùng có quyền; có thao tác quan trọng. | 1. POST /audit-logs.<br>2. Gửi action hợp lệ.<br>3. Kiểm tra dữ liệu log. | action: UPDATE_ROLE<br>target: USR001<br>result: SUCCESS | Audit Log được lưu. | High |
| TC-AUTHZ-012 | TS-AUDIT-01 – Ghi và tra cứu Audit Log | Action rỗng | Người dùng có quyền. | 1. Gửi action rỗng.<br>2. Kiểm tra kết quả. | action: empty | Hệ thống từ chối dữ liệu theo EX08. | High |
| TC-AUTHZ-013 | TS-AUDIT-01 – Ghi và tra cứu Audit Log | Tra cứu Audit Log | Admin/người có quyền đã đăng nhập. | 1. GET /audit-logs.<br>2. Kiểm tra danh sách. | Có dữ liệu log | Hiển thị danh sách log. | High |
| TC-AUTHZ-014 | TS-AUDIT-01 – Ghi và tra cứu Audit Log | Không có quyền tra cứu log | Customer đã đăng nhập. | 1. GET /audit-logs.<br>2. Kiểm tra kết quả. | Token Customer | Hệ thống từ chối theo BRULE10/EX07. | High |
