TEST SCENARIO – CAB SYSTEM

1. Mục đích

Tài liệu này sinh Test Scenario từ FR + API + Business Rule + Business Exception + Acceptance Criteria. Mỗi scenario phải được triển khai thành các Test Case đủ độ phủ theo dữ liệu và quy tắc nghiệp vụ.

2. Quy tắc độ phủ

Positive: dữ liệu hợp lệ.

Empty/Null: bỏ trống/thiếu trường bắt buộc.

Negative: sai kiểu, sai format, sai enum, ID không tồn tại.

Boundary: tại biên và ngay ngoài biên khi API/SRS xác định biên.

Business Rule: kiểm tra BRULE01–BRULE11.

Exception: kiểm tra EX01–EX08.

Security: 401 khi chưa xác thực và 403 khi không đủ quyền nếu endpoint được bảo vệ.

Data consistency: dữ liệu lưu, dữ liệu trả về và báo cáo phải nhất quán.

Các nội dung SRS đang TBD (công thức cước, timeout tài xế, số lần retry, chính sách hủy, chính sách retry thanh toán, tần suất vị trí, thời gian lưu dữ liệu, kênh thông báo, quyền chi tiết) không được tự đặt số. Dùng giá trị cấu hình sau khi được xác nhận.

3. Business Rule và Business Exception dùng để test

Mã

Nội dung

BRULE01

Người dùng phải đăng nhập trước khi dùng chức năng yêu cầu xác thực.

BRULE02

Chỉ tài xế ở trạng thái sẵn sàng/AVAILABLE mới được tìm để nhận chuyến.

BRULE03

Một chuyến không được phân công đồng thời cho nhiều tài xế.

BRULE04

Tài xế từ chối thì hệ thống tiếp tục tìm tài xế khác.

BRULE05

Không tìm được tài xế thì hệ thống phải thông báo khách hàng.

BRULE06

Chỉ chuyến hoàn thành mới xác định cước cuối cùng.

BRULE07

Hệ thống hỗ trợ tiền mặt và thanh toán điện tử.

BRULE08

CAB không lưu trực tiếp dữ liệu thẻ/tài khoản thanh toán nhạy cảm.

BRULE09

Customer chỉ được đánh giá chuyến đã hoàn thành.

BRULE10

Người dùng chỉ được thực hiện chức năng phù hợp với quyền.

BRULE11

Các thao tác quản trị quan trọng phải được ghi Audit Log.

EX01

Không tìm được tài xế → thông báo khách hàng.

EX02

Tài xế từ chối → tìm tài xế khác.

EX03

Tài xế không phản hồi → sau thời gian quy định tìm tài xế khác.

EX04

Thanh toán thất bại → thông báo và cho phép xử lý lại theo chính sách.

EX05

Mất kết nối → lưu trạng thái phù hợp và xử lý lại khi có kết nối.

EX06

Không lấy được vị trí → dùng vị trí gần nhất nếu có hoặc thông báo lỗi.

EX07

Người dùng không có quyền → từ chối thao tác.

EX08

Dữ liệu không hợp lệ → thông báo lỗi và yêu cầu nhập lại.

4. Danh sách Test Scenario

4.1. AUTH

Scenario ID

API

FR

Mục tiêu

Độ phủ bắt buộc

BRULE / EX

TS-AUTH-REG-01

POST /auth/register

FR02.01

Đăng ký Customer

Valid; Empty/Null; Invalid format/type; Boundary password; Duplicate

EX08

TS-AUTH-LOGIN-01

POST /auth/login

FR02.02

Đăng nhập

Valid; Empty; Wrong credential; Locked account

BRULE01, EX08

TS-AUTH-PROFILE-01

PATCH /customers/{customerId}

FR02.03

Cập nhật Customer

Valid; Empty body; Invalid format/ID; Auth; Permission

BRULE01, BRULE10, EX07, EX08

4.2. AUTHORIZATION

Scenario ID

API

FR

Mục tiêu

Độ phủ bắt buộc

BRULE / EX

TS-AUTHZ-VERIFY-01

POST /authorization/verify

FR18.01

Xác thực JWT

Valid; Missing; Invalid; Expired

BRULE01, EX07

TS-AUTHZ-ROLE-01

PUT /authorization/users/{userId}/role

FR18.02

Phân quyền

Valid; Empty; Invalid role/ID; Permission; Audit

BRULE10, BRULE11, EX07, EX08

TS-AUTHZ-CHECK-01

POST /authorization/check

FR18.03

Kiểm tra quyền

Allowed; Denied; Empty; Invalid

BRULE10, EX07, EX08

TS-AUDIT-CREATE-01

POST /audit-logs

FR20.01

Ghi Audit Log

Valid; Missing field; Invalid data; Required audit content

BRULE11, EX08

TS-AUDIT-SEARCH-01

GET /audit-logs

FR20.02

Tra cứu Audit Log

Valid; Empty result; Auth; Permission

BRULE10, BRULE11, EX07

4.3. BOOKING

Scenario ID

API

FR

Mục tiêu

Độ phủ bắt buộc

BRULE / EX

TS-BOOK-VALIDATE-01

POST /bookings/validate

FR01.05

Validate yêu cầu đặt xe

Valid; Empty each required field; Invalid type/vehicle

EX08

TS-BOOK-CREATE-01

POST /bookings

FR01.01-FR01.04, FR01.06

Tạo chuyến

Valid; Empty; Invalid; Auth; Initial status; Network exception

BRULE01, EX05, EX07, EX08

4.4. DRIVER

Scenario ID

API

FR

Mục tiêu

Độ phủ bắt buộc

BRULE / EX

TS-DRIVER-CREATE-01

POST /drivers

FR03.03

Tạo Driver

Valid; Empty; Invalid; Duplicate; Permission

BRULE10, EX07, EX08

TS-DRIVER-PROFILE-01

PATCH /drivers/{driverId}

FR03.01

Cập nhật hồ sơ Driver

Valid; Empty; Invalid; Not found; Permission

BRULE10, EX07, EX08

TS-DRIVER-STATUS-01

PATCH /drivers/{driverId}/availability

FR03.02

Cập nhật trạng thái Driver

AVAILABLE/BUSY/OFFLINE; Empty; Invalid enum; Matching rule

BRULE02, EX08

TS-VEHICLE-CREATE-01

POST /drivers/{driverId}/vehicles

FR04.01

Thêm phương tiện

Valid; Empty; Invalid type; Duplicate plate; Invalid driver

EX08

TS-VEHICLE-UPDATE-01

PATCH /vehicles/{vehicleId}

FR04.02

Cập nhật phương tiện

Valid; Empty; Invalid enum; Not found; Permission

BRULE10, EX07, EX08

4.5. TRIP

Scenario ID

API

FR

Mục tiêu

Độ phủ bắt buộc

BRULE / EX

TS-TRIP-MATCH-01

POST /trips/{tripId}/matching

FR05.01-FR05.04

Tìm/lọc/ưu tiên tài xế

AVAILABLE vs BUSY/OFFLINE; location; vehicle; no driver

BRULE02, BRULE05, EX01, EX06

TS-TRIP-OFFER-01

POST /trips/{tripId}/driver-offer

FR06.01

Gửi yêu cầu cho Driver

Valid; Empty/invalid driverId; unavailable driver

BRULE02, EX08

TS-TRIP-ACCEPT-01

POST /trips/{tripId}/accept

FR06.02

Driver chấp nhận

Valid; already assigned; wrong driver; invalid trip

BRULE03, BRULE10, EX07

TS-TRIP-REJECT-01

POST /trips/{tripId}/reject

FR06.03

Driver từ chối

Valid; wrong driver; invalid trip; find another

BRULE04, EX02

TS-TRIP-RETRY-01

POST /trips/{tripId}/matching/retry

FR06.04-FR06.05

Timeout/tìm Driver khác

No response; rejected driver; no next driver; invalid trip

BRULE04, BRULE05, EX01, EX02, EX03

TS-TRIP-MATCH-FAIL-01

POST /trips/{tripId}/matching/fail

FR06.06

Không tìm được Driver

No driver; notify customer; invalid state/ID

BRULE05, EX01

TS-TRIP-DETAIL-01

GET /trips/{tripId}

FR07.01-FR07.02

Xem trạng thái/tài xế

Owner; invalid ID; wrong customer; auth

BRULE01, BRULE10, EX07

TS-TRIP-TRACK-01

GET /trips/{tripId}/tracking

FR07.03

Theo dõi vị trí

Current; last known; no location; permission

BRULE10, EX06, EX07

TS-TRIP-STATUS-01

PATCH /trips/{tripId}/status

FR08.01-FR08.04

Cập nhật trạng thái chuyến

All valid states; Empty; Invalid enum; invalid order; wrong driver

BRULE03, BRULE10, EX07, EX08

TS-TRIP-LOCATION-01

POST /drivers/{driverId}/locations

FR09.01-FR09.02

Ghi/cập nhật vị trí

Valid; Empty; wrong type; geographic boundary; network exception

EX05, EX06, EX08

4.6. PAYMENT

Scenario ID

API

FR

Mục tiêu

Độ phủ bắt buộc

BRULE / EX

TS-PAY-FARE-01

POST /trips/{tripId}/fare/calculate

FR10.01-FR10.03

Tính/xác định/lưu cước

Completed vs non-completed; Invalid ID; Auth

BRULE06, EX07, EX08

TS-PAY-METHOD-01

PATCH /payments/{paymentId}/method

FR11.01

Chọn phương thức

CASH; ELECTRONIC; Empty; Invalid enum; Invalid ID

BRULE07, EX08

TS-PAY-CASH-01

POST /payments/cash

FR11.02

Thanh toán tiền mặt

Valid; Empty; amount 0/negative; invalid trip

BRULE07, EX08

TS-PAY-ELECTRONIC-01

POST /payments/electronic

FR11.03

Thanh toán điện tử

Valid; Empty; invalid amount; provider fail; no sensitive storage

BRULE07, BRULE08, EX04, EX05, EX08

TS-PAY-RESULT-01

GET /payments/{paymentId}

FR11.04

Xem kết quả thanh toán

SUCCESS; FAILED; PENDING; invalid ID; Auth

EX04, EX07

TS-PAY-FAIL-01

PATCH /payments/{paymentId}/failed

FR12.01-FR12.02

Ghi nhận/thông báo thất bại

Valid failure; Empty reason; Invalid ID; state integrity

EX04, EX08

TS-PAY-RETRY-01

POST /payments/{paymentId}/retry

FR12.03

Thanh toán lại

FAILED; non-FAILED; invalid ID; provider failure

EX04, EX05

4.7. NOTIFICATION

Scenario ID

API

FR

Mục tiêu

Độ phủ bắt buộc

BRULE / EX

TS-NOTI-SEND-01

POST /notifications

FR13.01-FR13.05

Gửi thông báo

All event types; Empty; Invalid enum; Correct recipient; Provider failure

EX05, EX08

4.8. HISTORY-RATING

Scenario ID

API

FR

Mục tiêu

Độ phủ bắt buộc

BRULE / EX

TS-RATE-CREATE-01

POST /trips/{tripId}/ratings

FR14.01-FR14.02

Đánh giá và lưu đánh giá

Valid; Empty; score boundary 1/5; 0/6 invalid; comment 500/501; trip state; ownership; duplicate

BRULE09, BRULE10, EX07, EX08

4.9. OPERATION

Scenario ID

API

FR

Mục tiêu

Độ phủ bắt buộc

BRULE / EX

TS-OPS-CUSTOMERS-01

GET /operations/customers

FR15.01

Quản lý khách hàng

Valid; Empty result/body; Invalid/Not found ID when applicable; Auth; Permission; Audit for update

BRULE10, BRULE11, EX07, EX08

TS-OPS-DRIVERS-01

GET /operations/drivers

FR15.02

Quản lý tài xế

Valid; Empty result/body; Invalid/Not found ID when applicable; Auth; Permission; Audit for update

BRULE10, BRULE11, EX07, EX08

TS-OPS-VEHICLES-01

GET /operations/vehicles

FR15.03

Quản lý phương tiện

Valid; Empty result/body; Invalid/Not found ID when applicable; Auth; Permission; Audit for update

BRULE10, BRULE11, EX07, EX08

TS-OPS-TRIPS-01

GET /operations/trips

FR15.04

Theo dõi chuyến

Valid; Empty result/body; Invalid/Not found ID when applicable; Auth; Permission; Audit for update

BRULE10, BRULE11, EX07, EX08

TS-OPS-INCIDENTS-01

GET /operations/incidents

FR16.01

Xem chuyến lỗi

Valid; Empty result/body; Invalid/Not found ID when applicable; Auth; Permission; Audit for update

BRULE10, BRULE11, EX07, EX08

TS-OPS-INCIDENT-HANDLE-01

PATCH /operations/incidents/{incidentId}

FR16.02

Xử lý chuyến lỗi

Valid; Empty result/body; Invalid/Not found ID when applicable; Auth; Permission; Audit for update

BRULE10, BRULE11, EX07, EX08

TS-OPS-TXN-LIST-01

GET /operations/transactions

FR17.01

Tra cứu giao dịch

Valid; Empty result/body; Invalid/Not found ID when applicable; Auth; Permission; Audit for update

BRULE10, BRULE11, EX07, EX08

TS-OPS-TXN-DETAIL-01

GET /operations/transactions/{transactionId}

FR17.02

Xem trạng thái giao dịch

Valid; Empty result/body; Invalid/Not found ID when applicable; Auth; Permission; Audit for update

BRULE10, BRULE11, EX07, EX08

4.10. REPORT

Scenario ID

API

FR

Mục tiêu

Độ phủ bắt buộc

BRULE / EX

TS-REPORT-TRIPS-01

GET /reports/trips

FR19.01

Báo cáo chuyến

Valid; Empty dataset; Data consistency; Auth; Permission

BRULE10, EX07

TS-REPORT-REVENUE-01

GET /reports/revenue

FR19.02

Báo cáo doanh thu

Valid; Empty dataset; Data consistency; Auth; Permission

BRULE10, EX07

TS-REPORT-COMPLETE-01

GET /reports/completion-rate

FR19.03

Tỷ lệ hoàn thành

Valid; Empty dataset; Data consistency; Auth; Permission

BRULE10, EX07

TS-REPORT-CANCEL-01

GET /reports/cancellation-rate

FR19.04

Tỷ lệ hủy

Valid; Empty dataset; Data consistency; Auth; Permission

BRULE10, EX07

TS-REPORT-DRIVER-01

GET /reports/drivers

FR19.05

Hiệu quả tài xế

Valid; Empty dataset; Data consistency; Auth; Permission

BRULE10, EX07

5. Mapping sang Test Case

Scenario

File

TS-AUTH-*

Test Cases/auth-testcase.md

TS-AUTHZ-* / TS-AUDIT-*

Test Cases/authorization-testcase.md

TS-BOOK-*

Test Cases/booking-testcase.md

TS-DRIVER-* / TS-VEHICLE-*

Test Cases/driver-testcase.md

TS-TRIP-*

Test Cases/trip-testcase.md

TS-PAY-*

Test Cases/payment-testcase.md

TS-NOTI-*

Test Cases/notification-testcase.md

TS-RATE-*

Test Cases/history-rating-testcase.md

TS-OPS-*

Test Cases/operation-testcase.md

TS-REPORT-*

Test Cases/report-testcase.md
