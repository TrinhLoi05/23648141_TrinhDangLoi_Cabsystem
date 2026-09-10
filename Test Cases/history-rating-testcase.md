# TEST CASE – HISTORY & RATING

## 1. Thông tin chung

**Module:** History & Rating  
**Business Requirement:** BR14 – Đánh giá tài xế

Functional Requirements:

- FR14.01 – Đánh giá tài xế.
- FR14.02 – Lưu đánh giá.

> SRS hiện tại chưa có FR riêng cho chức năng xem lịch sử chuyến.

---

## 2. Test Cases

| Test Case ID | Test Scenario | FR | Pre-condition | Test Data | Test Steps | Expected Result | Priority | Status |
|---|---|---|---|---|---|---|---|---|
| TC-RATE-01 | TS-RATE-01 – Đánh giá chuyến hoàn thành | FR14.01 | Trip=COMPLETED | score=5 | Mở chuyến → đánh giá | Hệ thống cho phép đánh giá | High | Not Run |
| TC-RATE-02 | TS-RATE-02 – Lưu đánh giá | FR14.02 | Dữ liệu hợp lệ | score=5, comment=Tốt | Gửi đánh giá | Rating được lưu | High | Not Run |
| TC-RATE-03 | TS-RATE-03 – Điểm < 1 | FR14.01 | Trip hoàn thành | score=0 | Gửi đánh giá | Hệ thống từ chối | Medium | Not Run |
| TC-RATE-04 | TS-RATE-04 – Điểm > 5 | FR14.01 | Trip hoàn thành | score=6 | Gửi đánh giá | Hệ thống từ chối | Medium | Not Run |
| TC-RATE-05 | TS-RATE-05 – Trip chưa hoàn thành | FR14.01 | Trip=IN_PROGRESS | score=5 | Gửi đánh giá | Không cho phép đánh giá | High | Not Run |
| TC-RATE-06 | TS-RATE-06 – Đánh giá chuyến người khác | FR14.01 | Trip không thuộc Customer | TRIP002 | Gửi đánh giá | Hệ thống từ chối | High | Not Run |
| TC-RATE-07 | TS-RATE-07 – Đánh giá lần hai | FR14.02 | Trip đã có Rating | score=4 | Gửi lại đánh giá | Hệ thống xử lý theo chính sách | Medium | Not Run |

---

## 3. Traceability

| FR | API |
|---|---|
| FR14.01 | POST /trips/{tripId}/ratings |
| FR14.02 | POST /trips/{tripId}/ratings |
