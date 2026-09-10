# TEST CASE – REPORT

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-REPORT-001 | TS-REPORT-01 – Xem báo cáo hoạt động | Báo cáo số lượng chuyến | Người dùng có quyền; có dữ liệu thực tế. | 1. Gọi GET /reports/trips.<br>2. Đối chiếu dữ liệu. | Dữ liệu hệ thống đã biết | Hiển thị đúng số lượng chuyến. | High |
| TC-REPORT-002 | TS-REPORT-01 – Xem báo cáo hoạt động | Báo cáo doanh thu | Người dùng có quyền; có dữ liệu thực tế. | 1. Gọi GET /reports/revenue.<br>2. Đối chiếu dữ liệu. | Dữ liệu hệ thống đã biết | Hiển thị đúng doanh thu. | High |
| TC-REPORT-003 | TS-REPORT-01 – Xem báo cáo hoạt động | Báo cáo tỷ lệ hoàn thành | Người dùng có quyền; có dữ liệu thực tế. | 1. Gọi GET /reports/completion-rate.<br>2. Đối chiếu dữ liệu. | Dữ liệu hệ thống đã biết | Hiển thị đúng tỷ lệ hoàn thành. | High |
| TC-REPORT-004 | TS-REPORT-01 – Xem báo cáo hoạt động | Báo cáo tỷ lệ hủy | Người dùng có quyền; có dữ liệu thực tế. | 1. Gọi GET /reports/cancellation-rate.<br>2. Đối chiếu dữ liệu. | Dữ liệu hệ thống đã biết | Hiển thị đúng tỷ lệ hủy. | High |
| TC-REPORT-005 | TS-REPORT-01 – Xem báo cáo hoạt động | Báo cáo hiệu quả tài xế | Người dùng có quyền; có dữ liệu thực tế. | 1. Gọi GET /reports/drivers.<br>2. Đối chiếu dữ liệu. | Dữ liệu hệ thống đã biết | Hiển thị đúng số liệu tài xế. | High |
| TC-REPORT-006 | TS-REPORT-01 – Xem báo cáo hoạt động | Không có dữ liệu báo cáo | Người dùng có quyền; không có dữ liệu. | 1. Gọi API báo cáo.<br>2. Kiểm tra kết quả. | Dataset: empty | Hiển thị 0 hoặc danh sách rỗng; không lỗi. | Medium |
| TC-REPORT-007 | TS-REPORT-01 – Xem báo cáo hoạt động | Người không có quyền xem báo cáo | Customer không có quyền báo cáo. | 1. Gọi API báo cáo bằng token Customer.<br>2. Kiểm tra kết quả. | Token Customer | Hệ thống từ chối theo BRULE10/EX07. | High |
