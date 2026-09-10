# TEST CASE – HISTORY-RATING

> Bộ Test Case cơ bản cho người mới học. Chỉ giữ các case quan trọng để đủ độ phủ theo yêu cầu.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-RATE-001 | TS-RATE-01 – Đánh giá tài xế sau chuyến | Đánh giá hợp lệ | Trip đã COMPLETED; Customer là chủ chuyến. | 1. POST /trips/{tripId}/ratings.<br>2. Gửi score hợp lệ.<br>3. Kiểm tra dữ liệu. | score: 3<br>comment: Tài xế tốt | Lưu đánh giá thành công. | High |
| TC-RATE-002 | TS-RATE-01 – Đánh giá tài xế sau chuyến | Giá trị biên dưới | Trip đã COMPLETED. | 1. Gửi score=1.<br>2. Kiểm tra kết quả. | score: 1 | Chấp nhận score=1. | High |
| TC-RATE-003 | TS-RATE-01 – Đánh giá tài xế sau chuyến | Giá trị biên trên | Trip đã COMPLETED. | 1. Gửi score=5.<br>2. Kiểm tra kết quả. | score: 5 | Chấp nhận score=5. | High |
| TC-RATE-004 | TS-RATE-01 – Đánh giá tài xế sau chuyến | Score dưới biên | Trip đã COMPLETED. | 1. Gửi score=0.<br>2. Kiểm tra kết quả. | score: 0 | Hệ thống từ chối dữ liệu. | High |
| TC-RATE-005 | TS-RATE-01 – Đánh giá tài xế sau chuyến | Score trên biên | Trip đã COMPLETED. | 1. Gửi score=6.<br>2. Kiểm tra kết quả. | score: 6 | Hệ thống từ chối dữ liệu. | High |
| TC-RATE-006 | TS-RATE-01 – Đánh giá tài xế sau chuyến | Score rỗng | Trip đã COMPLETED. | 1. Để score rỗng.<br>2. Gửi đánh giá. | score: null | Hệ thống báo lỗi. | High |
| TC-RATE-007 | TS-RATE-01 – Đánh giá tài xế sau chuyến | Đánh giá khi chuyến chưa hoàn thành | Trip đang IN_PROGRESS. | 1. Gửi đánh giá.<br>2. Kiểm tra kết quả. | score: 5 | Hệ thống từ chối theo BRULE09. | High |
| TC-RATE-008 | TS-RATE-01 – Đánh giá tài xế sau chuyến | Đánh giá chuyến của người khác | Trip thuộc Customer B; Customer A đăng nhập. | 1. Customer A gửi rating cho Trip B.<br>2. Kiểm tra kết quả. | score: 5 | Hệ thống từ chối theo BRULE10/EX07. | High |
