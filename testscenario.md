# TEST SCENARIO – CAB SYSTEM

## 1. Mục đích

Tài liệu Test Scenario mô tả các tình huống cần kiểm thử
cho hệ thống CAB System.

Test Scenario được xây dựng dựa trên:

- Business Requirement (BR)
- Functional Requirement (FR)
- Use Case (UC)
- Acceptance Criteria (AC)

Luồng truy xuất:

BR
↓
FR
↓
UC
↓
AC
↓
Test Scenario
↓
Test Case

---

# 2. Quy ước mã Test Scenario

| Mã | Nhóm chức năng |
|---|---|
| TS-AUTH | Đăng ký, đăng nhập, khách hàng |
| TS-AUTHZ | Xác thực và phân quyền |
| TS-BOOK | Đặt chuyến |
| TS-DRIVER | Tài xế và phương tiện |
| TS-TRIP | Chuyến xe |
| TS-PAY | Tính cước và thanh toán |
| TS-NOTI | Thông báo |
| TS-RATE | Đánh giá |
| TS-OPS | Quản lý vận hành |
| TS-REPORT | Báo cáo |
| TS-AUDIT | Audit Log |
| TS-E2E | Kiểm thử toàn bộ quy trình |

---

# 3. AUTH – Authentication

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-AUTH-01 | FR02.01 | Đăng ký với thông tin hợp lệ | Tài khoản được tạo thành công |
| TS-AUTH-02 | FR02.01 | Đăng ký thiếu thông tin bắt buộc | Hệ thống báo lỗi |
| TS-AUTH-03 | FR02.01 | Đăng ký email đã tồn tại | Hệ thống từ chối |
| TS-AUTH-04 | FR02.01 | Đăng ký số điện thoại đã tồn tại | Hệ thống từ chối |
| TS-AUTH-05 | FR02.01 | Đăng ký email sai định dạng | Hệ thống báo lỗi |
| TS-AUTH-06 | FR02.02 | Đăng nhập đúng tài khoản và mật khẩu | Đăng nhập thành công |
| TS-AUTH-07 | FR02.02 | Đăng nhập sai mật khẩu | Đăng nhập thất bại |
| TS-AUTH-08 | FR02.02 | Đăng nhập tài khoản không tồn tại | Hệ thống từ chối |
| TS-AUTH-09 | FR02.02 | Đăng nhập tài khoản bị khóa | Không cho phép đăng nhập |
| TS-AUTH-10 | FR02.03 | Cập nhật thông tin hợp lệ | Thông tin được cập nhật |
| TS-AUTH-11 | FR02.03 | Cập nhật dữ liệu không hợp lệ | Hệ thống báo lỗi |
| TS-AUTH-12 | FR02.03 | Cập nhật khi chưa đăng nhập | Hệ thống từ chối |

---

# 4. AUTHORIZATION – Phân quyền

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-AUTHZ-01 | FR18.01 | Xác thực token hợp lệ | Xác thực thành công |
| TS-AUTHZ-02 | FR18.01 | Token không hợp lệ | Từ chối truy cập |
| TS-AUTHZ-03 | FR18.01 | Token hết hạn | Yêu cầu đăng nhập lại |
| TS-AUTHZ-04 | FR18.02 | Admin phân quyền người dùng | Role được cập nhật |
| TS-AUTHZ-05 | FR18.02 | Người không có quyền phân quyền | Hệ thống từ chối |
| TS-AUTHZ-06 | FR18.02 | Role không hợp lệ | Hệ thống báo lỗi |
| TS-AUTHZ-07 | FR18.03 | Người dùng có quyền thao tác | Cho phép thực hiện |
| TS-AUTHZ-08 | FR18.03 | Người dùng không có quyền | Từ chối thao tác |

---

# 5. BOOKING – Đặt chuyến

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-BOOK-01 | FR01.01 | Nhập điểm đón hợp lệ | Ghi nhận điểm đón |
| TS-BOOK-02 | FR01.01 | Không nhập điểm đón | Báo lỗi |
| TS-BOOK-03 | FR01.02 | Nhập điểm đến hợp lệ | Ghi nhận điểm đến |
| TS-BOOK-04 | FR01.02 | Không nhập điểm đến | Báo lỗi |
| TS-BOOK-05 | FR01.03 | Chọn loại xe hợp lệ | Ghi nhận loại xe |
| TS-BOOK-06 | FR01.03 | Không chọn loại xe | Không cho tạo chuyến |
| TS-BOOK-07 | FR01.05 | Kiểm tra yêu cầu hợp lệ | Dữ liệu hợp lệ |
| TS-BOOK-08 | FR01.05 | Kiểm tra yêu cầu lỗi | Hệ thống báo lỗi |
| TS-BOOK-09 | FR01.04, FR01.06 | Gửi yêu cầu đặt xe hợp lệ | Tạo chuyến thành công |
| TS-BOOK-10 | FR01.06 | Kiểm tra trạng thái chuyến mới | SEARCHING_DRIVER |
| TS-BOOK-11 | FR01.04 | Đặt xe khi chưa đăng nhập | Hệ thống từ chối |

---

# 6. DRIVER – Tài xế và phương tiện

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-DRIVER-01 | FR03.03 | Tạo tài khoản tài xế hợp lệ | Tài khoản được tạo |
| TS-DRIVER-02 | FR03.03 | Tạo tài xế thiếu dữ liệu | Báo lỗi |
| TS-DRIVER-03 | FR03.03 | Số điện thoại tài xế đã tồn tại | Từ chối tạo |
| TS-DRIVER-04 | FR03.01 | Cập nhật hồ sơ tài xế | Hồ sơ được cập nhật |
| TS-DRIVER-05 | FR03.01 | Cập nhật tài xế không tồn tại | Báo không tìm thấy |
| TS-DRIVER-06 | FR03.02 | Chuyển AVAILABLE | Trạng thái được cập nhật |
| TS-DRIVER-07 | FR03.02 | Chuyển BUSY | Trạng thái được cập nhật |
| TS-DRIVER-08 | FR03.02 | Chuyển OFFLINE | Trạng thái được cập nhật |
| TS-DRIVER-09 | FR03.02 | Trạng thái không hợp lệ | Hệ thống từ chối |
| TS-DRIVER-10 | FR04.01 | Thêm phương tiện | Phương tiện được tạo |
| TS-DRIVER-11 | FR04.01 | Biển số đã tồn tại | Hệ thống từ chối |
| TS-DRIVER-12 | FR04.02 | Cập nhật phương tiện | Cập nhật thành công |
| TS-DRIVER-13 | FR04.02 | Phương tiện không tồn tại | Báo lỗi |

---

# 7. TRIP – Chuyến xe

## 7.1. Tìm tài xế

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-TRIP-01 | FR05.01 | Có tài xế AVAILABLE | Tìm được tài xế |
| TS-TRIP-02 | FR05.01 | Không có tài xế AVAILABLE | Không tìm được tài xế |
| TS-TRIP-03 | FR05.02 | Kiểm tra vị trí tài xế | Vị trí được sử dụng |
| TS-TRIP-04 | FR05.03 | Lọc theo loại xe | Chọn đúng tài xế phù hợp |
| TS-TRIP-05 | FR05.04 | Có nhiều tài xế phù hợp | Áp dụng tiêu chí ưu tiên |

## 7.2. Phân công tài xế

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-TRIP-06 | FR06.01 | Gửi yêu cầu cho tài xế | Driver nhận yêu cầu |
| TS-TRIP-07 | FR06.02 | Driver chấp nhận | Driver được phân công |
| TS-TRIP-08 | FR06.03 | Driver từ chối | Ghi nhận từ chối |
| TS-TRIP-09 | FR06.05 | Driver từ chối và còn tài xế khác | Tìm tài xế khác |
| TS-TRIP-10 | FR06.04 | Driver không phản hồi | Xử lý timeout |
| TS-TRIP-11 | FR06.05 | Retry tìm tài xế | Tìm tài xế tiếp theo |
| TS-TRIP-12 | FR06.06 | Không còn tài xế | NO_DRIVER_FOUND |
| TS-TRIP-13 | FR06.06 | Không tìm được tài xế | Customer nhận thông báo |

## 7.3. Theo dõi chuyến

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-TRIP-14 | FR07.01 | Xem trạng thái chuyến | Hiển thị đúng trạng thái |
| TS-TRIP-15 | FR07.02 | Xem tài xế | Hiển thị đúng Driver |
| TS-TRIP-16 | FR07.03 | Theo dõi vị trí | Hiển thị vị trí |
| TS-TRIP-17 | FR07.03 | Không có vị trí mới | Hiển thị vị trí gần nhất |
| TS-TRIP-18 | FR07.01 | Xem chuyến người khác | Hệ thống từ chối |

## 7.4. Thực hiện chuyến

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-TRIP-19 | FR08.01 | Driver đến điểm đón | Cập nhật trạng thái |
| TS-TRIP-20 | FR08.02 | Driver đã đón khách | Cập nhật trạng thái |
| TS-TRIP-21 | FR08.03 | Bắt đầu chuyến | IN_PROGRESS |
| TS-TRIP-22 | FR08.04 | Hoàn thành chuyến | COMPLETED |
| TS-TRIP-23 | FR08.* | Cập nhật sai trình tự | Hệ thống từ chối |
| TS-TRIP-24 | FR08.* | Driver khác cập nhật chuyến | Hệ thống từ chối |

## 7.5. Vị trí tài xế

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-TRIP-25 | FR09.01 | Ghi vị trí hợp lệ | Vị trí được lưu |
| TS-TRIP-26 | FR09.02 | Cập nhật vị trí mới | Lưu vị trí mới |
| TS-TRIP-27 | FR09.01 | Tọa độ không hợp lệ | Hệ thống từ chối |
| TS-TRIP-28 | FR09.02 | Mất kết nối GPS | Xử lý theo chính sách |

---

# 8. PAYMENT – Thanh toán

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-PAY-01 | FR10.02 | Xác định dịch vụ | Xác định đúng loại dịch vụ |
| TS-PAY-02 | FR10.01 | Tính cước | Tính được số tiền |
| TS-PAY-03 | FR10.03 | Lưu cước | Fare được lưu |
| TS-PAY-04 | FR10.01 | Trip không hợp lệ | Hệ thống từ chối |
| TS-PAY-05 | FR11.01 | Chọn tiền mặt | method=CASH |
| TS-PAY-06 | FR11.02 | Thanh toán tiền mặt | Giao dịch được ghi nhận |
| TS-PAY-07 | FR11.01 | Chọn điện tử | method=ELECTRONIC |
| TS-PAY-08 | FR11.03 | Thanh toán điện tử thành công | Giao dịch thành công |
| TS-PAY-09 | FR11.04 | Nhận kết quả thanh toán | Trạng thái được cập nhật |
| TS-PAY-10 | FR12.01 | Thanh toán thất bại | status=FAILED |
| TS-PAY-11 | FR12.02 | Thông báo thanh toán lỗi | Customer nhận thông báo |
| TS-PAY-12 | FR12.03 | Thanh toán lại | Hệ thống xử lý retry |
| TS-PAY-13 | FR11.03 | Payment Provider mất kết nối | Chức năng chính vẫn hoạt động |
| TS-PAY-14 | FR11.03 | Kiểm tra dữ liệu thẻ | Không lưu dữ liệu thẻ nhạy cảm |

---

# 9. NOTIFICATION – Thông báo

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-NOTI-01 | FR13.01 | Booking được tiếp nhận | Customer nhận thông báo |
| TS-NOTI-02 | FR13.02 | Driver nhận chuyến | Customer nhận thông báo |
| TS-NOTI-03 | FR13.03 | Driver đến | Customer nhận thông báo |
| TS-NOTI-04 | FR13.04 | Trip hoàn thành | Customer nhận thông báo |
| TS-NOTI-05 | FR13.05 | Thanh toán thành công | Customer nhận thông báo |
| TS-NOTI-06 | FR13.05 | Thanh toán thất bại | Customer nhận thông báo |
| TS-NOTI-07 | FR13.* | Notification Provider lỗi | Chức năng chính vẫn hoạt động |
| TS-NOTI-08 | FR13.* | Kiểm tra người nhận | Thông báo đúng người |

---

# 10. HISTORY & RATING – Đánh giá

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-RATE-01 | FR14.01 | Đánh giá chuyến hoàn thành | Cho phép đánh giá |
| TS-RATE-02 | FR14.02 | Lưu đánh giá hợp lệ | Rating được lưu |
| TS-RATE-03 | FR14.01 | Điểm nhỏ hơn 1 | Từ chối |
| TS-RATE-04 | FR14.01 | Điểm lớn hơn 5 | Từ chối |
| TS-RATE-05 | FR14.01 | Trip chưa hoàn thành | Không cho đánh giá |
| TS-RATE-06 | FR14.01 | Đánh giá chuyến người khác | Từ chối |
| TS-RATE-07 | FR14.02 | Đánh giá lần hai | Xử lý theo chính sách |

---

# 11. OPERATION – Quản lý vận hành

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-OPS-01 | FR15.01 | Xem khách hàng | Danh sách được hiển thị |
| TS-OPS-02 | FR15.02 | Xem tài xế | Danh sách được hiển thị |
| TS-OPS-03 | FR15.03 | Xem phương tiện | Danh sách được hiển thị |
| TS-OPS-04 | FR15.04 | Theo dõi chuyến | Hiển thị chuyến đang hoạt động |
| TS-OPS-05 | FR15.* | User không có quyền Operation | Từ chối truy cập |
| TS-OPS-06 | FR16.01 | Xem chuyến lỗi | Hiển thị sự cố |
| TS-OPS-07 | FR16.02 | Xử lý sự cố | Lưu kết quả |
| TS-OPS-08 | FR16.02 | Không có quyền xử lý | Từ chối |
| TS-OPS-09 | FR17.01 | Tra cứu giao dịch | Hiển thị giao dịch |
| TS-OPS-10 | FR17.02 | Xem trạng thái giao dịch | Hiển thị đúng trạng thái |
| TS-OPS-11 | FR17.02 | Giao dịch không tồn tại | Báo không tìm thấy |

---

# 12. REPORT – Báo cáo

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-REPORT-01 | FR19.01 | Báo cáo số chuyến | Hiển thị đúng số chuyến |
| TS-REPORT-02 | FR19.02 | Báo cáo doanh thu | Hiển thị đúng doanh thu |
| TS-REPORT-03 | FR19.03 | Tỷ lệ hoàn thành | Hiển thị đúng tỷ lệ |
| TS-REPORT-04 | FR19.04 | Tỷ lệ hủy | Hiển thị đúng tỷ lệ |
| TS-REPORT-05 | FR19.05 | Hiệu quả tài xế | Hiển thị thống kê |
| TS-REPORT-06 | FR19.* | Không có dữ liệu | Hiển thị 0 hoặc rỗng |
| TS-REPORT-07 | FR19.* | Không có quyền | Từ chối truy cập |

---

# 13. AUDIT LOG

| Test Scenario ID | FR | Test Scenario | Expected Result |
|---|---|---|---|
| TS-AUDIT-01 | FR20.01 | Thực hiện thao tác quan trọng | Audit Log được tạo |
| TS-AUDIT-02 | FR20.01 | Admin thay đổi quyền | Ghi Audit Log |
| TS-AUDIT-03 | FR20.01 | Operator xử lý sự cố | Ghi Audit Log |
| TS-AUDIT-04 | FR20.01 | Kiểm tra nội dung log | Có user, thời gian, action, result |
| TS-AUDIT-05 | FR20.02 | Admin tra cứu log | Danh sách được hiển thị |
| TS-AUDIT-06 | FR20.02 | Tra cứu theo user | Hiển thị đúng log |
| TS-AUDIT-07 | FR20.02 | Tra cứu theo thời gian | Hiển thị đúng khoảng thời gian |
| TS-AUDIT-08 | FR20.02 | User không có quyền xem | Hệ thống từ chối |

---

# 14. END-TO-END TEST SCENARIO

| Test Scenario ID | Test Scenario | Expected Result |
|---|---|---|
| TS-E2E-01 | Customer đặt xe → Driver nhận → thực hiện chuyến → thanh toán → đánh giá | Toàn bộ quy trình hoàn thành thành công |
| TS-E2E-02 | Driver đầu tiên từ chối, Driver thứ hai chấp nhận | Hệ thống tự động tìm tài xế khác |
| TS-E2E-03 | Không tìm được tài xế | Customer được thông báo |
| TS-E2E-04 | Thanh toán điện tử thất bại | Ghi nhận FAILED và cho phép xử lý lại theo chính sách |

---

# 15. Liên kết với Test Case

Mỗi Test Scenario sẽ được triển khai chi tiết trong thư mục:

Test Cases/

Ví dụ:

TS-AUTH-01
↓
Test Cases/auth-testcase.md
↓
TC-AUTH-01

TS-BOOK-01
↓
Test Cases/booking-testcase.md
↓
TC-BOOK-01

TS-TRIP-01
↓
Test Cases/trip-testcase.md
↓
TC-TRIP-01

TS-PAY-01
↓
Test Cases/payment-testcase.md
↓
TC-PAY-01
