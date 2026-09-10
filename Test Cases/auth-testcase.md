# TEST CASE – AUTH

## 1. Thông tin chung

**Module:** Authentication / Customer Account  
**Liên quan:** BR02 – Quản lý khách hàng

Functional Requirements:

- FR02.01 – Đăng ký.
- FR02.02 – Đăng nhập.
- FR02.03 – Cập nhật thông tin cá nhân.

---

# 2. Test Case cho FR02.01 – Đăng ký tài khoản

## TC-AUTH-01 – Đăng ký tài khoản thành công

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-01 |
| Test Scenario | TS-AUTH-01 – Đăng ký với thông tin hợp lệ |
| FR | FR02.01 |
| Chức năng | Đăng ký tài khoản |
| Priority | High |
| Pre-condition | Khách hàng chưa có tài khoản |
| Test Data | Họ tên: Nguyễn Văn A<br>Phone: 0901234567<br>Email: nguyenvana@gmail.com<br>Password: 123456 |
| Expected Result | Tài khoản được tạo thành công |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Mở chức năng đăng ký | Hệ thống hiển thị form đăng ký |
| 2 | Nhập họ tên | Hệ thống ghi nhận họ tên |
| 3 | Nhập số điện thoại | Hệ thống ghi nhận số điện thoại |
| 4 | Nhập email | Hệ thống ghi nhận email |
| 5 | Nhập mật khẩu | Hệ thống ghi nhận mật khẩu |
| 6 | Nhấn nút Đăng ký | Hệ thống kiểm tra dữ liệu |
| 7 | Hệ thống tạo tài khoản | Tài khoản được lưu thành công |
| 8 | Kiểm tra thông báo | Hiển thị “Đăng ký tài khoản thành công” |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

## TC-AUTH-02 – Đăng ký thiếu thông tin bắt buộc

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-02 |
| Test Scenario | TS-AUTH-02 – Đăng ký thiếu thông tin |
| FR | FR02.01 |
| Chức năng | Đăng ký tài khoản |
| Priority | High |
| Pre-condition | Khách hàng chưa có tài khoản |
| Test Data | Họ tên: Nguyễn Văn A<br>Phone: để trống<br>Password: 123456 |
| Expected Result | Hệ thống thông báo thiếu thông tin và không tạo tài khoản |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Mở form đăng ký | Form đăng ký được hiển thị |
| 2 | Nhập họ tên | Dữ liệu được ghi nhận |
| 3 | Để trống số điện thoại | Không có dữ liệu số điện thoại |
| 4 | Nhập mật khẩu | Dữ liệu được ghi nhận |
| 5 | Nhấn Đăng ký | Hệ thống kiểm tra dữ liệu |
| 6 | Kiểm tra kết quả | Hệ thống thông báo thiếu thông tin bắt buộc |
| 7 | Kiểm tra dữ liệu | Không tạo tài khoản |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

## TC-AUTH-03 – Đăng ký với email đã tồn tại

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-03 |
| Test Scenario | TS-AUTH-03 – Email đã tồn tại |
| FR | FR02.01 |
| Chức năng | Đăng ký tài khoản |
| Priority | High |
| Pre-condition | Email nguyenvana@gmail.com đã tồn tại |
| Test Data | Phone: 0909999999<br>Email: nguyenvana@gmail.com<br>Password: 123456 |
| Expected Result | Hệ thống từ chối đăng ký |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Mở form đăng ký | Form được hiển thị |
| 2 | Nhập thông tin hợp lệ | Dữ liệu được ghi nhận |
| 3 | Nhập email đã tồn tại | Email được nhận |
| 4 | Nhấn Đăng ký | Hệ thống kiểm tra email |
| 5 | Kiểm tra kết quả | Hiển thị “Email hoặc số điện thoại đã được sử dụng” |
| 6 | Kiểm tra dữ liệu | Không tạo tài khoản mới |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

## TC-AUTH-04 – Đăng ký với số điện thoại đã tồn tại

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-04 |
| Test Scenario | TS-AUTH-04 – Số điện thoại đã tồn tại |
| FR | FR02.01 |
| Chức năng | Đăng ký tài khoản |
| Priority | High |
| Pre-condition | Số điện thoại 0901234567 đã tồn tại |
| Test Data | Phone: 0901234567<br>Email: newcustomer@gmail.com<br>Password: 123456 |
| Expected Result | Hệ thống từ chối đăng ký |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Mở form đăng ký | Form được hiển thị |
| 2 | Nhập thông tin | Dữ liệu được ghi nhận |
| 3 | Nhập số điện thoại đã tồn tại | Số điện thoại được nhận |
| 4 | Nhấn Đăng ký | Hệ thống kiểm tra |
| 5 | Kiểm tra kết quả | Hệ thống thông báo số điện thoại đã được sử dụng |
| 6 | Kiểm tra dữ liệu | Không tạo tài khoản mới |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

## TC-AUTH-05 – Đăng ký với email sai định dạng

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-05 |
| Test Scenario | TS-AUTH-05 – Email không đúng định dạng |
| FR | FR02.01 |
| Chức năng | Đăng ký tài khoản |
| Priority | Medium |
| Pre-condition | Khách hàng chưa có tài khoản |
| Test Data | Email: nguyenvanagmail.com |
| Expected Result | Hệ thống thông báo email không hợp lệ |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Mở form đăng ký | Form được hiển thị |
| 2 | Nhập các thông tin cần thiết | Dữ liệu được ghi nhận |
| 3 | Nhập email sai định dạng | Email được nhập |
| 4 | Nhấn Đăng ký | Hệ thống kiểm tra định dạng email |
| 5 | Kiểm tra kết quả | Hiển thị thông báo email không hợp lệ |
| 6 | Kiểm tra dữ liệu | Không tạo tài khoản |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

# 3. Test Case cho FR02.02 – Đăng nhập

## TC-AUTH-06 – Đăng nhập thành công

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-06 |
| Test Scenario | TS-AUTH-06 – Đăng nhập với tài khoản hợp lệ |
| FR | FR02.02 |
| Chức năng | Đăng nhập |
| Priority | High |
| Pre-condition | Tài khoản đã tồn tại và đang hoạt động |
| Test Data | Phone: 0901234567<br>Password: 123456 |
| Expected Result | Người dùng đăng nhập thành công và nhận Access Token |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Mở màn hình đăng nhập | Form đăng nhập được hiển thị |
| 2 | Nhập số điện thoại | Hệ thống ghi nhận |
| 3 | Nhập mật khẩu đúng | Hệ thống ghi nhận |
| 4 | Nhấn Đăng nhập | Hệ thống xác thực |
| 5 | Kiểm tra kết quả | Đăng nhập thành công |
| 6 | Kiểm tra phiên đăng nhập | Hệ thống trả Access Token |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

## TC-AUTH-07 – Đăng nhập sai mật khẩu

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-07 |
| Test Scenario | TS-AUTH-07 – Sai mật khẩu |
| FR | FR02.02 |
| Chức năng | Đăng nhập |
| Priority | High |
| Pre-condition | Tài khoản tồn tại |
| Test Data | Phone: 0901234567<br>Password: 999999 |
| Expected Result | Đăng nhập thất bại |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Mở trang đăng nhập | Form được hiển thị |
| 2 | Nhập tài khoản đúng | Hệ thống ghi nhận |
| 3 | Nhập mật khẩu sai | Hệ thống ghi nhận |
| 4 | Nhấn Đăng nhập | Hệ thống kiểm tra |
| 5 | Kiểm tra kết quả | Hiển thị thông báo tài khoản hoặc mật khẩu không chính xác |
| 6 | Kiểm tra phiên | Không tạo phiên đăng nhập |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

## TC-AUTH-08 – Đăng nhập với tài khoản không tồn tại

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-08 |
| Test Scenario | TS-AUTH-08 – Tài khoản không tồn tại |
| FR | FR02.02 |
| Chức năng | Đăng nhập |
| Priority | High |
| Pre-condition | Tài khoản chưa tồn tại |
| Test Data | Phone: 0999999999<br>Password: 123456 |
| Expected Result | Hệ thống từ chối đăng nhập |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Mở trang đăng nhập | Form được hiển thị |
| 2 | Nhập tài khoản không tồn tại | Hệ thống ghi nhận |
| 3 | Nhập mật khẩu | Hệ thống ghi nhận |
| 4 | Nhấn Đăng nhập | Hệ thống kiểm tra tài khoản |
| 5 | Kiểm tra kết quả | Hệ thống thông báo đăng nhập thất bại |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

## TC-AUTH-09 – Đăng nhập với tài khoản bị khóa

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-09 |
| Test Scenario | TS-AUTH-09 – Tài khoản bị khóa |
| FR | FR02.02 |
| Chức năng | Đăng nhập |
| Priority | High |
| Pre-condition | Tài khoản tồn tại nhưng status = LOCKED |
| Test Data | Phone: 0901234567<br>Password: 123456 |
| Expected Result | Không cho phép đăng nhập |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Mở màn hình đăng nhập | Form được hiển thị |
| 2 | Nhập thông tin đăng nhập đúng | Hệ thống nhận dữ liệu |
| 3 | Nhấn Đăng nhập | Hệ thống kiểm tra trạng thái tài khoản |
| 4 | Kiểm tra kết quả | Hiển thị “Tài khoản đã bị khóa” |
| 5 | Kiểm tra phiên | Không tạo Access Token |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

# 4. Test Case cho FR02.03 – Cập nhật thông tin khách hàng

## TC-AUTH-10 – Cập nhật thông tin cá nhân thành công

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-10 |
| Test Scenario | TS-AUTH-10 – Cập nhật thông tin hợp lệ |
| FR | FR02.03 |
| Chức năng | Cập nhật thông tin |
| Priority | Medium |
| Pre-condition | Khách hàng đã đăng nhập |
| Test Data | Full Name: Nguyễn Văn An<br>Email: nguyenvanan@gmail.com |
| Expected Result | Thông tin khách hàng được cập nhật |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Đăng nhập | Đăng nhập thành công |
| 2 | Mở thông tin cá nhân | Hiển thị thông tin hiện tại |
| 3 | Chọn chỉnh sửa | Cho phép nhập dữ liệu mới |
| 4 | Nhập thông tin hợp lệ | Dữ liệu được ghi nhận |
| 5 | Nhấn Lưu | Hệ thống kiểm tra dữ liệu |
| 6 | Kiểm tra kết quả | Hệ thống thông báo cập nhật thành công |
| 7 | Mở lại hồ sơ | Hiển thị thông tin mới |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

## TC-AUTH-11 – Cập nhật thông tin không hợp lệ

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-11 |
| Test Scenario | TS-AUTH-11 – Cập nhật dữ liệu không hợp lệ |
| FR | FR02.03 |
| Chức năng | Cập nhật thông tin |
| Priority | Medium |
| Pre-condition | Khách hàng đã đăng nhập |
| Test Data | Email: nguyenvanangmail.com |
| Expected Result | Hệ thống thông báo lỗi và không cập nhật dữ liệu |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Đăng nhập | Đăng nhập thành công |
| 2 | Mở hồ sơ | Hồ sơ được hiển thị |
| 3 | Chọn chỉnh sửa | Cho phép chỉnh sửa |
| 4 | Nhập email sai định dạng | Dữ liệu được nhập |
| 5 | Nhấn Lưu | Hệ thống kiểm tra |
| 6 | Kiểm tra kết quả | Thông báo dữ liệu không hợp lệ |
| 7 | Kiểm tra hồ sơ | Dữ liệu cũ vẫn được giữ nguyên |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

## TC-AUTH-12 – Cập nhật thông tin khi chưa đăng nhập

| Thuộc tính | Nội dung |
|---|---|
| Test Case ID | TC-AUTH-12 |
| Test Scenario | TS-AUTH-12 – Cập nhật khi chưa đăng nhập |
| FR | FR02.03 |
| Chức năng | Cập nhật thông tin |
| Priority | High |
| Pre-condition | Người dùng chưa đăng nhập hoặc không có Access Token |
| Test Data | customerId = CUS001 |
| Expected Result | Hệ thống từ chối yêu cầu |

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Không đăng nhập vào hệ thống | Không có Access Token |
| 2 | Gửi yêu cầu cập nhật khách hàng | Hệ thống kiểm tra xác thực |
| 3 | Kiểm tra kết quả | Hệ thống từ chối yêu cầu |
| 4 | Kiểm tra thông báo | Hiển thị “Bạn chưa đăng nhập” |
| 5 | Kiểm tra dữ liệu | Thông tin khách hàng không thay đổi |

**Actual Result:** Chưa kiểm thử  
**Status:** Not Run

---

# 5. Traceability – AUTH

| Test Scenario | Test Case | FR | API |
|---|---|---|---|
| TS-AUTH-01 | TC-AUTH-01 | FR02.01 | POST /auth/register |
| TS-AUTH-02 | TC-AUTH-02 | FR02.01 | POST /auth/register |
| TS-AUTH-03 | TC-AUTH-03 | FR02.01 | POST /auth/register |
| TS-AUTH-04 | TC-AUTH-04 | FR02.01 | POST /auth/register |
| TS-AUTH-05 | TC-AUTH-05 | FR02.01 | POST /auth/register |
| TS-AUTH-06 | TC-AUTH-06 | FR02.02 | POST /auth/login |
| TS-AUTH-07 | TC-AUTH-07 | FR02.02 | POST /auth/login |
| TS-AUTH-08 | TC-AUTH-08 | FR02.02 | POST /auth/login |
| TS-AUTH-09 | TC-AUTH-09 | FR02.02 | POST /auth/login |
| TS-AUTH-10 | TC-AUTH-10 | FR02.03 | PATCH /customers/{customerId} |
| TS-AUTH-11 | TC-AUTH-11 | FR02.03 | PATCH /customers/{customerId} |
| TS-AUTH-12 | TC-AUTH-12 | FR02.03 | PATCH /customers/{customerId} |

---

# 6. Tổng kết

Nhóm AUTH hiện có:

- 3 Functional Requirements.
- 12 Test Scenarios.
- 12 Test Cases.

```text
BR02
 │
 ├── FR02.01 Đăng ký
 │       ├── TC-AUTH-01
 │       ├── TC-AUTH-02
 │       ├── TC-AUTH-03
 │       ├── TC-AUTH-04
 │       └── TC-AUTH-05
 │
 ├── FR02.02 Đăng nhập
 │       ├── TC-AUTH-06
 │       ├── TC-AUTH-07
 │       ├── TC-AUTH-08
 │       └── TC-AUTH-09
 │
 └── FR02.03 Cập nhật thông tin
         ├── TC-AUTH-10
         ├── TC-AUTH-11
         └── TC-AUTH-12
```
