# TEST CASE – REPORT

## 1. Thông tin chung

**Module:** Report  
**Business Requirement:** BR19 – Báo cáo

---

## 2. Test Cases

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-REPORT-01 | TS-REPORT-01 – Báo cáo chuyến | FR19.01 | Operator có quyền | Khoảng thời gian | Mở báo cáo chuyến | Hiển thị đúng số chuyến | Medium | Not Run |
| TC-REPORT-02 | TS-REPORT-02 – Báo cáo doanh thu | FR19.02 | Có dữ liệu payment | Khoảng thời gian | Mở báo cáo doanh thu | Tổng doanh thu chính xác | High | Not Run |
| TC-REPORT-03 | TS-REPORT-03 – Tỷ lệ hoàn thành | FR19.03 | Có dữ liệu Trip | Khoảng thời gian | Xem báo cáo | Hiển thị đúng tỷ lệ hoàn thành | Medium | Not Run |
| TC-REPORT-04 | TS-REPORT-04 – Tỷ lệ hủy | FR19.04 | Có chuyến CANCELLED | Khoảng thời gian | Xem báo cáo | Hiển thị đúng tỷ lệ hủy | Medium | Not Run |
| TC-REPORT-05 | TS-REPORT-05 – Hiệu quả tài xế | FR19.05 | Có dữ liệu Driver | DRV001 | Xem báo cáo tài xế | Hiển thị thống kê tài xế | Medium | Not Run |
| TC-REPORT-06 | TS-REPORT-06 – Không có dữ liệu | FR19.01-FR19.05 | Khoảng thời gian rỗng | Khoảng thời gian | Xem báo cáo | Hiển thị 0 hoặc danh sách rỗng | Low | Not Run |
| TC-REPORT-07 | TS-REPORT-07 – Không có quyền | FR19.01-FR19.05 | Customer đăng nhập | Không | Truy cập Report | Hệ thống từ chối | High | Not Run |

---

## 3. Traceability

| FR | API |
|---|---|
| FR19.01 | GET /reports/trips |
| FR19.02 | GET /reports/revenue |
| FR19.03 | GET /reports/completion-rate |
| FR19.04 | GET /reports/cancellation-rate |
| FR19.05 | GET /reports/drivers |
