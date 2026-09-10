# TEST CASE – TRIP

## 1. Thông tin chung

**Module:** Trip  
**Business Requirement:** BR05, BR06, BR07, BR08, BR09

Functional Requirements:

- FR05.01 – FR05.04: Tìm tài xế.
- FR06.01 – FR06.06: Phân công tài xế.
- FR07.01 – FR07.03: Theo dõi chuyến.
- FR08.01 – FR08.04: Thực hiện chuyến.
- FR09.01 – FR09.02: Quản lý vị trí.

---

# 2. Test Case – Tìm tài xế

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-TRIP-01 | TS-TRIP-01 – Có Driver AVAILABLE | FR05.01 | Trip=SEARCHING_DRIVER | Driver AVAILABLE | Bắt đầu matching | Tìm được tài xế | High | Not Run |
| TC-TRIP-02 | TS-TRIP-02 – Không có Driver AVAILABLE | FR05.01 | Không có tài xế sẵn sàng | Không | Matching | Không tìm được tài xế | High | Not Run |
| TC-TRIP-03 | TS-TRIP-03 – Kiểm tra vị trí | FR05.02 | Driver có location | Lat/Long | Matching | Hệ thống sử dụng vị trí hiện tại | High | Not Run |
| TC-TRIP-04 | TS-TRIP-04 – Lọc theo loại xe | FR05.03 | Có nhiều driver | CAR_4_SEAT | Matching | Chỉ tài xế phù hợp được chọn | High | Not Run |
| TC-TRIP-05 | TS-TRIP-05 – Ưu tiên tài xế | FR05.04 | Nhiều driver phù hợp | Driver A/B | Matching | Áp dụng tiêu chí ưu tiên | Medium | Not Run |

> Tiêu chí ưu tiên cụ thể hiện là TBD.

---

# 3. Test Case – Phân công tài xế

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-TRIP-06 | TS-TRIP-06 – Gửi yêu cầu | FR06.01 | Driver phù hợp | DRV001 | Gửi offer | Driver nhận yêu cầu chuyến | High | Not Run |
| TC-TRIP-07 | TS-TRIP-07 – Driver chấp nhận | FR06.02 | Có offer | DRV001 | Chọn Accept | Driver được phân công | High | Not Run |
| TC-TRIP-08 | TS-TRIP-08 – Driver từ chối | FR06.03 | Có offer | DRV001 | Chọn Reject | Hệ thống ghi nhận từ chối | High | Not Run |
| TC-TRIP-09 | TS-TRIP-09 – Tìm driver khác | FR06.05 | Driver A reject | Driver B | Reject A | Hệ thống tìm Driver B | High | Not Run |
| TC-TRIP-10 | TS-TRIP-10 – Không phản hồi | FR06.04 | Driver không trả lời | Timeout | Chờ hết thời gian | Xử lý timeout | High | Not Run |
| TC-TRIP-11 | TS-TRIP-11 – Retry matching | FR06.05 | Driver A timeout | Driver B | Retry | Gửi yêu cầu tài xế tiếp theo | High | Not Run |
| TC-TRIP-12 | TS-TRIP-12 – Không còn tài xế | FR06.06 | Không còn driver | Không | Matching thất bại | status=NO_DRIVER_FOUND | High | Not Run |
| TC-TRIP-13 | TS-TRIP-13 – Thông báo không có tài xế | FR06.06 | NO_DRIVER_FOUND | CUS001 | Kết thúc matching | Customer nhận thông báo | High | Not Run |

---

# 4. Test Case – Theo dõi chuyến

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-TRIP-14 | TS-TRIP-14 – Xem trạng thái | FR07.01 | Trip tồn tại | TRIP001 | Mở Trip | Hiển thị đúng status | High | Not Run |
| TC-TRIP-15 | TS-TRIP-15 – Xem tài xế | FR07.02 | Trip đã có driver | DRV001 | Xem chi tiết Trip | Hiển thị đúng Driver | High | Not Run |
| TC-TRIP-16 | TS-TRIP-16 – Theo dõi vị trí | FR07.03 | Driver có vị trí | Lat/Long | Mở tracking | Hiển thị vị trí tài xế | High | Not Run |
| TC-TRIP-17 | TS-TRIP-17 – Không có vị trí mới | FR07.03 | Mất cập nhật GPS | Last Location | Mở tracking | Hiển thị vị trí gần nhất nếu có | Medium | Not Run |
| TC-TRIP-18 | TS-TRIP-18 – Xem chuyến người khác | FR07.01 | Trip thuộc Customer khác | TRIP002 | Truy cập Trip | Hệ thống từ chối | High | Not Run |

---

# 5. Test Case – Thực hiện chuyến

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-TRIP-19 | TS-TRIP-19 – Driver đến điểm đón | FR08.01 | Driver được phân công | DRIVER_ARRIVED | Chọn Đã đến | Status được cập nhật | High | Not Run |
| TC-TRIP-20 | TS-TRIP-20 – Đã đón khách | FR08.02 | DRIVER_ARRIVED | PASSENGER_PICKED_UP | Chọn Đã đón | Status được cập nhật | High | Not Run |
| TC-TRIP-21 | TS-TRIP-21 – Bắt đầu chuyến | FR08.03 | Đã đón khách | IN_PROGRESS | Chọn Bắt đầu | status=IN_PROGRESS | High | Not Run |
| TC-TRIP-22 | TS-TRIP-22 – Hoàn thành | FR08.04 | Trip đang chạy | COMPLETED | Chọn Hoàn thành | status=COMPLETED | High | Not Run |
| TC-TRIP-23 | TS-TRIP-23 – Sai trình tự | FR08.01-FR08.04 | Trip mới assigned | COMPLETED | Chuyển thẳng COMPLETED | Hệ thống từ chối | High | Not Run |
| TC-TRIP-24 | TS-TRIP-24 – Driver khác cập nhật | FR08.01-FR08.04 | DRV002 không được phân công | TRIP001 | Gửi update | Hệ thống từ chối | High | Not Run |

Trình tự hợp lệ:

```text
DRIVER_ASSIGNED
      ↓
DRIVER_ARRIVED
      ↓
PASSENGER_PICKED_UP
      ↓
IN_PROGRESS
      ↓
COMPLETED
