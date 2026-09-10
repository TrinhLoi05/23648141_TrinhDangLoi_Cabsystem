# TEST CASE – AUTH

> Bộ Test Case cơ bản cho người mới học. Chỉ giữ các case quan trọng để đủ độ phủ theo yêu cầu.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-AUTH-001 | TS-AUTH-01 – Đăng ký tài khoản khách hàng | Đăng ký với dữ liệu hợp lệ | Khách hàng chưa có tài khoản. | 1. Gửi POST /auth/register.<br>2. Nhập đầy đủ dữ liệu hợp lệ.<br>3. Kiểm tra kết quả. | fullName: Nguyễn Văn A<br>phone: 0901234567<br>email: a@gmail.com<br>password: 123456 | Tạo tài khoản thành công. | High |
| TC-AUTH-002 | TS-AUTH-01 – Đăng ký tài khoản khách hàng | Bỏ trống trường bắt buộc | Khách hàng chưa có tài khoản. | 1. Gửi POST /auth/register.<br>2. Để fullName hoặc phone hoặc password rỗng.<br>3. Kiểm tra kết quả. | fullName: empty | Hệ thống báo dữ liệu không hợp lệ và không tạo tài khoản. | High |
| TC-AUTH-003 | TS-AUTH-01 – Đăng ký tài khoản khách hàng | Email sai định dạng | Khách hàng chưa có tài khoản. | 1. Nhập email sai định dạng.<br>2. Gửi đăng ký.<br>3. Kiểm tra kết quả. | email: agmail.com | Hệ thống báo lỗi dữ liệu. | Medium |
| TC-AUTH-004 | TS-AUTH-01 – Đăng ký tài khoản khách hàng | Dữ liệu sai kiểu | Khách hàng chưa có tài khoản. | 1. Gửi phone dạng số thay vì chuỗi.<br>2. Kiểm tra kết quả. | phone: 901234567 | Hệ thống từ chối dữ liệu không đúng kiểu. | Medium |
| TC-AUTH-005 | TS-AUTH-01 – Đăng ký tài khoản khách hàng | Đăng ký thông tin đã tồn tại | Số điện thoại hoặc email đã tồn tại. | 1. Gửi thông tin đăng ký bị trùng.<br>2. Kiểm tra kết quả. | phone: 0901234567 đã tồn tại | Hệ thống không tạo tài khoản trùng. | High |
| TC-AUTH-006 | TS-AUTH-02 – Đăng nhập khách hàng | Đăng nhập với thông tin đúng | Tài khoản đã tồn tại. | 1. Gửi POST /auth/login.<br>2. Nhập identifier và password đúng.<br>3. Kiểm tra kết quả. | identifier: 0901234567<br>password: 123456 | Đăng nhập thành công. | High |
| TC-AUTH-007 | TS-AUTH-02 – Đăng nhập khách hàng | Identifier rỗng | Tài khoản đã tồn tại. | 1. Để identifier rỗng.<br>2. Gửi đăng nhập.<br>3. Kiểm tra kết quả. | identifier: empty<br>password: 123456 | Không đăng nhập; hệ thống báo lỗi. | High |
| TC-AUTH-008 | TS-AUTH-02 – Đăng nhập khách hàng | Password rỗng | Tài khoản đã tồn tại. | 1. Nhập identifier.<br>2. Để password rỗng.<br>3. Gửi đăng nhập. | identifier: 0901234567<br>password: empty | Không đăng nhập; hệ thống báo lỗi. | High |
| TC-AUTH-009 | TS-AUTH-02 – Đăng nhập khách hàng | Sai thông tin đăng nhập | Tài khoản đã tồn tại. | 1. Nhập identifier đúng.<br>2. Nhập password sai.<br>3. Gửi đăng nhập. | identifier: 0901234567<br>password: wrong | Đăng nhập thất bại; không xác thực người dùng. | High |
| TC-AUTH-010 | TS-AUTH-03 – Cập nhật thông tin khách hàng | Cập nhật dữ liệu hợp lệ | Customer đã đăng nhập và cập nhật tài khoản của mình. | 1. Gửi PATCH /customers/{customerId}.<br>2. Nhập dữ liệu hợp lệ.<br>3. Kiểm tra dữ liệu. | customerId: CUS001<br>fullName: Nguyễn Văn An | Thông tin được cập nhật. | High |
| TC-AUTH-011 | TS-AUTH-03 – Cập nhật thông tin khách hàng | Email cập nhật không hợp lệ | Customer đã đăng nhập. | 1. Gửi email sai định dạng.<br>2. Kiểm tra kết quả. | email: angmail.com | Hệ thống báo lỗi; không lưu dữ liệu sai. | Medium |
| TC-AUTH-012 | TS-AUTH-03 – Cập nhật thông tin khách hàng | Không đăng nhập | Không có Bearer Token. | 1. Gửi PATCH không có token.<br>2. Kiểm tra kết quả. | Authorization: missing | Hệ thống từ chối theo BRULE01. | High |
| TC-AUTH-013 | TS-AUTH-03 – Cập nhật thông tin khách hàng | Cập nhật tài khoản người khác | Customer A đã đăng nhập; customerId thuộc Customer B. | 1. Customer A gửi PATCH vào customerId của B.<br>2. Kiểm tra kết quả. | customerId: CUS-B | Hệ thống từ chối theo BRULE10/EX07. | High |
