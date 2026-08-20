Bước 1: Đọc và phân tích yêu cầu sơ khởi của khách hàng ở giai đoạn 1.(Hiểu được ngữ cảnh của dịch vụ là gì?)
# SRS – CAB System

## 1. Phân tích yêu cầu sơ khởi của khách hàng

### 1.1. Tổng quan dự án

CAB System là nền tảng đặt xe trực tuyến được xây dựng cho Công ty ABC.

Hệ thống nhằm thay thế và cải thiện hệ thống đặt xe hiện tại, trong đó khách hàng có thể yêu cầu xe thông qua tổng đài hoặc ứng dụng đơn giản. Hệ thống mới sẽ hỗ trợ toàn bộ quy trình từ khi khách hàng tạo yêu cầu đặt xe, tìm và phân công tài xế, thực hiện chuyến đi, tính cước, thanh toán, gửi thông báo đến đánh giá sau chuyến.

Thời gian xây dựng và triển khai sản phẩm dự kiến là 7 tuần.

### 1.2. Bối cảnh hiện tại

Hệ thống hiện tại của Công ty ABC còn một số hạn chế:

- Việc phân công tài xế chủ yếu được thực hiện thủ công.
- Khách hàng khó theo dõi trạng thái chuyến đi.
- Thông tin thanh toán chưa được quản lý tập trung.
- Bộ phận vận hành gặp khó khăn trong việc quản lý khách hàng, tài xế và chuyến đi.
- Khả năng mở rộng hệ thống còn hạn chế.
- Việc xử lý các trường hợp tài xế từ chối hoặc không phản hồi chưa được tự động hóa tốt.
- Doanh nghiệp chưa có đầy đủ dữ liệu để theo dõi doanh thu, số lượng chuyến, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả hoạt động của tài xế.

### 1.3. Vấn đề cần giải quyết

Dựa trên yêu cầu của khách hàng, CAB System cần giải quyết các vấn đề chính sau:

1. Tự động hóa quá trình tìm kiếm và phân công tài xế.
2. Cho phép khách hàng dễ dàng tạo và theo dõi chuyến đi.
3. Cho phép tài xế nhận, từ chối và cập nhật trạng thái chuyến.
4. Quản lý thông tin khách hàng, tài xế và phương tiện tập trung.
5. Hỗ trợ tính cước và thanh toán.
6. Tích hợp với nhà cung cấp thanh toán bên ngoài.
7. Cung cấp hệ thống thông báo cho khách hàng và tài xế.
8. Hỗ trợ nhân viên vận hành theo dõi và xử lý các chuyến đi.
9. Cung cấp báo cáo phục vụ quản lý và ra quyết định.
10. Đảm bảo hệ thống có tính bảo mật, ổn định và có khả năng mở rộng.

### 1.4. Mục tiêu của hệ thống

CAB System được xây dựng với các mục tiêu:

- Cung cấp nền tảng đặt xe trực tuyến cho khách hàng.
- Tự động tìm tài xế phù hợp dựa trên vị trí và trạng thái hoạt động.
- Giảm sự phụ thuộc vào việc phân công tài xế thủ công.
- Cho phép khách hàng theo dõi trạng thái chuyến đi.
- Hỗ trợ tài xế quản lý và thực hiện chuyến.
- Quản lý tập trung thông tin chuyến đi và thanh toán.
- Hỗ trợ nhiều phương thức thanh toán.
- Cung cấp thông báo cho khách hàng và tài xế.
- Hỗ trợ nhân viên vận hành quản lý hoạt động của hệ thống.
- Cung cấp báo cáo về hoạt động kinh doanh.
- Đảm bảo hệ thống có khả năng mở rộng để phát triển thêm các tính năng trong tương lai.

### 1.5. Các nhóm người dùng chính

Hệ thống có 3 nhóm người dùng chính:

| Người dùng | Mô tả |
|---|---|
| Khách hàng | Sử dụng hệ thống để đăng ký, đặt xe, theo dõi chuyến đi, thanh toán và đánh giá tài xế. |
| Tài xế | Nhận chuyến, thực hiện chuyến và cập nhật trạng thái chuyến đi. |
| Nhân viên vận hành | Quản lý khách hàng, tài xế, phương tiện, chuyến đi và hỗ trợ xử lý sự cố. |

Ngoài 3 nhóm người dùng chính, hệ thống còn có thể tương tác với các hệ thống bên ngoài như:

- Nhà cung cấp thanh toán.
- Dịch vụ bản đồ/vị trí.
- Nhà cung cấp dịch vụ thông báo.

### 1.6. Phạm vi sơ bộ của hệ thống

#### Trong phạm vi hệ thống

CAB System dự kiến bao gồm:

- Quản lý tài khoản khách hàng.
- Quản lý tài khoản tài xế.
- Quản lý phương tiện.
- Đặt xe.
- Tìm kiếm và phân công tài xế.
- Theo dõi trạng thái chuyến đi.
- Cập nhật vị trí tài xế.
- Quản lý chuyến đi.
- Tính cước.
- Thanh toán.
- Thông báo.
- Đánh giá tài xế.
- Quản lý vận hành.
- Quản lý và tra cứu lịch sử giao dịch.
- Báo cáo thống kê.
- Phân quyền nhân viên.
- Ghi log các thao tác quan trọng.

#### Ngoài phạm vi hoặc chưa xác định

Một số nội dung hiện chưa được khách hàng xác định rõ:

- Công thức tính cước cụ thể.
- Tiêu chí ưu tiên tài xế.
- Thời gian tài xế phải phản hồi.
- Chính sách hủy chuyến.
- Chính sách xử lý thanh toán thất bại.
- Cách xử lý khi mất kết nối mạng.
- Thời gian lưu trữ dữ liệu.
- Chi tiết về nhà cung cấp thanh toán.
- Chi tiết về nhà cung cấp bản đồ/vị trí.
- Các kênh thông báo cụ thể.

Các nội dung trên cần được Business Analyst trao đổi và xác nhận với các bên liên quan trước khi triển khai.

### 1.7. Quy trình nghiệp vụ tổng quát

Quy trình đặt xe cơ bản của CAB System:

1. Khách hàng đăng nhập hệ thống.
2. Khách hàng nhập điểm đón và điểm đến.
3. Khách hàng lựa chọn loại xe/dịch vụ.
4. Khách hàng gửi yêu cầu đặt xe.
5. Hệ thống tiếp nhận yêu cầu.
6. Hệ thống tìm kiếm tài xế phù hợp.
7. Hệ thống gửi yêu cầu đến tài xế.
8. Tài xế chấp nhận hoặc từ chối chuyến.
9. Nếu tài xế từ chối hoặc không phản hồi, hệ thống tiếp tục tìm tài xế khác.
10. Nếu tìm được tài xế, hệ thống thông báo cho khách hàng.
11. Tài xế di chuyển đến điểm đón.
12. Tài xế cập nhật trạng thái đã đến điểm đón.
13. Tài xế đón khách và bắt đầu chuyến.
14. Tài xế cập nhật trạng thái đang di chuyển.
15. Tài xế hoàn thành chuyến.
16. Hệ thống tính cước.
17. Khách hàng thanh toán bằng tiền mặt hoặc phương thức điện tử.
18. Hệ thống thông báo kết quả thanh toán.
19. Khách hàng đánh giá tài xế.
20. Hệ thống lưu lịch sử chuyến đi và giao dịch.

### 1.8. Yêu cầu tổng quát

Từ yêu cầu sơ khởi, hệ thống cần đáp ứng các nhóm yêu cầu sau:

#### Yêu cầu chức năng

- Đăng ký và đăng nhập.
- Quản lý thông tin cá nhân.
- Quản lý tài xế.
- Quản lý phương tiện.
- Đặt xe.
- Tìm và phân công tài xế.
- Theo dõi chuyến đi.
- Cập nhật trạng thái chuyến.
- Tính cước.
- Thanh toán.
- Gửi thông báo.
- Đánh giá tài xế.
- Quản lý vận hành.
- Báo cáo thống kê.
- Phân quyền người dùng.
- Ghi nhận lịch sử thao tác.

#### Yêu cầu phi chức năng

- Hệ thống hoạt động ổn định khi số lượng người dùng tăng cao.
- Có khả năng mở rộng độc lập các thành phần.
- Đảm bảo bảo mật thông tin người dùng.
- Bảo vệ dữ liệu vị trí và dữ liệu giao dịch.
- Kiểm soát quyền truy cập.
- Ghi log các thao tác quan trọng.
- Lỗi ở thanh toán hoặc thông báo không được làm toàn bộ hệ thống đặt xe ngừng hoạt động.
- Có khả năng tích hợp thêm nhà cung cấp thanh toán và thông báo trong tương lai.
- Có khả năng bổ sung các loại dịch vụ mới.

### 1.9. Các vấn đề cần làm rõ với khách hàng

Hiện tại yêu cầu của khách hàng chưa đầy đủ. Business Analyst cần xác nhận thêm:

| STT | Vấn đề cần làm rõ |
|---:|---|
| 1 | Công thức tính giá cước cụ thể là gì? |
| 2 | Những tiêu chí nào được sử dụng để lựa chọn tài xế? |
| 3 | Tài xế phải phản hồi yêu cầu trong bao lâu? |
| 4 | Khi tài xế không phản hồi thì hệ thống xử lý như thế nào? |
| 5 | Chính sách hủy chuyến của khách hàng và tài xế là gì? |
| 6 | Khi thanh toán điện tử thất bại thì được thử lại bao nhiêu lần? |
| 7 | Khi mất kết nối mạng thì hệ thống phải xử lý như thế nào? |
| 8 | Doanh nghiệp muốn lưu dữ liệu trong bao lâu? |
| 9 | Những nhân viên vận hành nào được phép thực hiện thao tác nhạy cảm? |
| 10 | Doanh nghiệp sử dụng nhà cung cấp thanh toán nào? |
| 11 | Hệ thống sử dụng nhà cung cấp bản đồ/vị trí nào? |
| 12 | Hệ thống cần hỗ trợ những kênh thông báo nào? |
| 13 | Số lượng khách hàng và tài xế dự kiến trong giai đoạn đầu là bao nhiêu? |
| 14 | Số lượng chuyến đi tối đa dự kiến trong thời gian cao điểm là bao nhiêu? |

### 1.10. Kết luận bước 1

Qua phân tích yêu cầu sơ khởi, CAB System là một nền tảng đặt xe trực tuyến có phạm vi chính gồm:

**Đặt xe → Tìm tài xế → Phân công tài xế → Thực hiện chuyến → Tính cước → Thanh toán → Thông báo → Đánh giá → Quản lý và báo cáo.**

Hệ thống có 3 nhóm người dùng chính:

**Khách hàng – Tài xế – Nhân viên vận hành.**

Ngoài ra, hệ thống cần tích hợp với các hệ thống bên ngoài như thanh toán, bản đồ/vị trí và dịch vụ thông báo.

Do một số nghiệp vụ quan trọng chưa được khách hàng xác định đầy đủ, Business Analyst cần tiếp tục làm rõ các yêu cầu trước khi nhóm phát triển thiết kế và xây dựng hệ thống.
BƯỚC 2: xác định những stakeholders (lọc ra bảng gồm 2 cột, cột thứ nhất gồm tên stakeholders, cột thứ 2 là vai trò của nó) phần 2 là vẽ ma trận stakeholder matrix (ma trận này sẽ cho chúng ta biết tầm ảnh hưởng quan trọng của stakeholders trong hệ thống - dùng công cụ mermaid để vẽ các sơ đồ trong markdown 
## 2. Xác định Stakeholder

### 2.1. Danh sách Stakeholder

| Stakeholder | Vai trò |
|---|---|
| Khách hàng | Người sử dụng hệ thống để đăng ký, đặt xe, theo dõi chuyến đi, thanh toán và đánh giá tài xế. |
| Tài xế | Người nhận chuyến, di chuyển đến điểm đón, thực hiện chuyến và cập nhật trạng thái chuyến đi. |
| Nhân viên vận hành | Quản lý khách hàng, tài xế, phương tiện và chuyến đi; theo dõi và xử lý các trường hợp bất thường. |
| Quản lý vận hành | Theo dõi hoạt động của hệ thống, hiệu quả tài xế, tỷ lệ hoàn thành và tỷ lệ hủy chuyến. |
| Ban giám đốc | Theo dõi doanh thu, số lượng chuyến, hiệu quả hoạt động và sử dụng báo cáo để đưa ra quyết định kinh doanh. |
| Bộ phận tài chính/kế toán | Theo dõi thông tin thanh toán, doanh thu và lịch sử giao dịch. |
| Quản trị hệ thống | Quản lý tài khoản, phân quyền và các cấu hình quan trọng của hệ thống. |
| Nhà cung cấp thanh toán | Cung cấp dịch vụ xử lý thanh toán điện tử cho CAB System. |
| Nhà cung cấp bản đồ/vị trí | Cung cấp dữ liệu bản đồ, vị trí, khoảng cách và hỗ trợ xác định tài xế gần khách hàng. |
| Nhà cung cấp dịch vụ thông báo | Cung cấp các kênh gửi thông báo đến khách hàng và tài xế. |
| Nhóm phát triển hệ thống | Phân tích, thiết kế, xây dựng, kiểm thử và triển khai CAB System. |
| Business Analyst | Thu thập, phân tích và làm rõ yêu cầu giữa khách hàng và nhóm phát triển. |

Bước 3:  xác định business, mục tiêu nghiệp vụ ,thiết kế business goal hay tên gọi là gì tôi nghe không rõ (bg01 là gì bg02 là gì) hệ thống có chức năng tự động tìm tài xế , Ví dụ lấy 1 cái như bg02 là cho phép thanh toán bằng tiền mặt hoặc trực tuyến .

# 3. Business Goals – Mục tiêu nghiệp vụ

## 3.1. Tổng quan

Business Goal (BG) là các mục tiêu nghiệp vụ mà Công ty ABC mong muốn đạt được khi xây dựng hệ thống CAB System.

Các mục tiêu này được xác định dựa trên yêu cầu sơ khởi của khách hàng và các vấn đề của hệ thống hiện tại.

Mỗi Business Goal được đặt một mã định danh theo dạng:

- BG01
- BG02
- BG03
- ...

Các Business Goal sẽ là cơ sở để xác định các chức năng và yêu cầu của hệ thống ở các bước phân tích tiếp theo.

---

## 3.2. Danh sách Business Goals

| Mã | Business Goal | Mô tả |
|---|---|---|
| BG01 | Tự động hóa quá trình tìm và phân công tài xế | Hệ thống tự động tìm tài xế phù hợp dựa trên vị trí, trạng thái sẵn sàng và các tiêu chí vận hành thay vì phụ thuộc chủ yếu vào phân công thủ công. |
| BG02 | Hỗ trợ thanh toán linh hoạt | Cho phép khách hàng thanh toán bằng tiền mặt hoặc phương thức thanh toán điện tử thông qua nhà cung cấp thanh toán bên ngoài. |
| BG03 | Cải thiện trải nghiệm đặt xe của khách hàng | Cho phép khách hàng dễ dàng đăng ký, đặt xe, theo dõi chuyến đi và nhận thông báo về trạng thái chuyến. |
| BG04 | Quản lý tập trung thông tin chuyến đi và giao dịch | Lưu trữ và quản lý tập trung thông tin chuyến đi, cước phí, thanh toán và lịch sử giao dịch. |
| BG05 | Nâng cao hiệu quả vận hành | Cung cấp cho nhân viên vận hành công cụ theo dõi khách hàng, tài xế, phương tiện và các chuyến đi đang diễn ra. |
| BG06 | Cung cấp thông tin và báo cáo cho doanh nghiệp | Cung cấp báo cáo về số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả hoạt động của tài xế. |
| BG07 | Nâng cao độ tin cậy và khả năng hoạt động của hệ thống | Đảm bảo lỗi ở một thành phần như thanh toán hoặc thông báo không làm toàn bộ hệ thống đặt xe ngừng hoạt động. |
| BG08 | Đảm bảo an toàn và bảo mật dữ liệu | Bảo vệ thông tin cá nhân, dữ liệu phương tiện, dữ liệu vị trí, dữ liệu giao dịch và kiểm soát quyền truy cập. |
| BG09 | Hỗ trợ khả năng mở rộng trong tương lai | Cho phép doanh nghiệp bổ sung loại dịch vụ, phương thức thanh toán, nhà cung cấp thông báo và thay đổi thành phần kỹ thuật mà không phải xây dựng lại toàn bộ hệ thống. |
| BG10 | Nâng cao chất lượng dịch vụ thông qua phản hồi khách hàng | Cho phép khách hàng đánh giá tài xế sau khi hoàn thành chuyến để doanh nghiệp theo dõi và cải thiện chất lượng dịch vụ. |

---

## 3.3. Phân tích chi tiết Business Goals

### BG01 – Tự động hóa quá trình tìm và phân công tài xế

**Mục tiêu:**

Giảm sự phụ thuộc vào việc phân công tài xế thủ công và rút ngắn thời gian tìm tài xế cho khách hàng.

**Hệ thống cần hỗ trợ:**

- Xác định các tài xế đang sẵn sàng nhận chuyến.
- Xác định tài xế phù hợp với yêu cầu của khách hàng.
- Ưu tiên tài xế phù hợp và gần khách hàng.
- Gửi yêu cầu nhận chuyến đến tài xế.
- Cho phép tài xế chấp nhận hoặc từ chối chuyến.
- Nếu tài xế không phản hồi hoặc từ chối, hệ thống tiếp tục tìm tài xế khác.
- Thông báo cho khách hàng nếu không tìm được tài xế.

---

### BG02 – Hỗ trợ thanh toán linh hoạt

**Mục tiêu:**

Cho phép khách hàng lựa chọn phương thức thanh toán phù hợp và hỗ trợ doanh nghiệp quản lý kết quả thanh toán.

**Hệ thống cần hỗ trợ:**

- Thanh toán bằng tiền mặt.
- Thanh toán điện tử.
- Tích hợp với nhà cung cấp thanh toán bên ngoài.
- Không lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán trong CAB System.
- Thông báo kết quả thanh toán cho khách hàng.
- Cho phép xử lý lại thanh toán khi giao dịch điện tử thất bại theo chính sách của doanh nghiệp.

---

### BG03 – Cải thiện trải nghiệm đặt xe của khách hàng

**Mục tiêu:**

Giúp khách hàng thực hiện quá trình đặt xe nhanh chóng và dễ dàng.

**Hệ thống cần hỗ trợ:**

- Đăng ký tài khoản.
- Đăng nhập.
- Cập nhật thông tin cá nhân.
- Nhập điểm đón.
- Nhập điểm đến.
- Lựa chọn loại xe.
- Gửi yêu cầu đặt xe.
- Theo dõi trạng thái chuyến.
- Xem thông tin tài xế.
- Xem lịch sử chuyến.
- Đánh giá tài xế.

---

### BG04 – Quản lý tập trung thông tin chuyến đi và giao dịch

**Mục tiêu:**

Tập trung dữ liệu liên quan đến chuyến đi và thanh toán để doanh nghiệp dễ dàng tra cứu và quản lý.

**Hệ thống cần hỗ trợ:**

- Lưu thông tin chuyến đi.
- Lưu trạng thái chuyến.
- Lưu thông tin tài xế.
- Lưu thông tin khách hàng.
- Lưu cước phí.
- Lưu trạng thái thanh toán.
- Tra cứu lịch sử giao dịch.

---

### BG05 – Nâng cao hiệu quả vận hành

**Mục tiêu:**

Giúp nhân viên vận hành theo dõi và xử lý hoạt động đặt xe trên một hệ thống tập trung.

**Hệ thống cần hỗ trợ:**

- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Theo dõi chuyến đang diễn ra.
- Kiểm tra trạng thái tài xế.
- Xử lý các trường hợp chuyến bị lỗi.
- Tra cứu lịch sử chuyến và giao dịch.

---

### BG06 – Cung cấp thông tin và báo cáo cho doanh nghiệp

**Mục tiêu:**

Cung cấp dữ liệu cần thiết để doanh nghiệp đánh giá hoạt động kinh doanh và hiệu quả vận hành.

**Hệ thống cần cung cấp:**

- Số lượng chuyến.
- Doanh thu.
- Tỷ lệ chuyến hoàn thành.
- Tỷ lệ hủy chuyến.
- Hiệu quả hoạt động của tài xế.
- Lịch sử giao dịch.

---

### BG07 – Nâng cao độ tin cậy và khả năng hoạt động

**Mục tiêu:**

Đảm bảo hệ thống vẫn có thể phục vụ các chức năng chính khi một thành phần gặp lỗi.

**Yêu cầu định hướng:**

- Lỗi thanh toán không làm chức năng đặt xe ngừng hoạt động.
- Lỗi dịch vụ thông báo không làm toàn bộ hệ thống ngừng hoạt động.
- Các thành phần có thể được mở rộng độc lập khi tải tăng.
- Cho phép triển khai chức năng mới từng phần.

---

### BG08 – Đảm bảo an toàn và bảo mật dữ liệu

**Mục tiêu:**

Bảo vệ dữ liệu của khách hàng, tài xế và doanh nghiệp.

**Hệ thống cần hỗ trợ:**

- Xác thực người dùng.
- Phân quyền người dùng.
- Kiểm soát quyền truy cập chức năng quản trị.
- Bảo vệ thông tin cá nhân.
- Bảo vệ thông tin phương tiện.
- Bảo vệ dữ liệu vị trí.
- Bảo vệ dữ liệu giao dịch.
- Ghi log các thao tác quan trọng.

---

### BG09 – Hỗ trợ khả năng mở rộng trong tương lai

**Mục tiêu:**

Xây dựng nền tảng CAB có thể phát triển lâu dài.

**Hệ thống cần có khả năng:**

- Thêm loại dịch vụ mới.
- Thêm phương thức thanh toán.
- Thêm nhà cung cấp thanh toán.
- Thêm nhà cung cấp thông báo.
- Thay đổi một số thành phần kỹ thuật.
- Mở rộng số lượng khách hàng và tài xế.
- Bổ sung chức năng mới mà hạn chế ảnh hưởng đến chức năng đang hoạt động.

---

### BG10 – Nâng cao chất lượng dịch vụ

**Mục tiêu:**

Thu thập phản hồi của khách hàng để doanh nghiệp đánh giá chất lượng phục vụ của tài xế.

**Hệ thống cần hỗ trợ:**

- Khách hàng đánh giá tài xế sau khi hoàn thành chuyến.
- Lưu kết quả đánh giá.
- Cho phép doanh nghiệp tra cứu thông tin đánh giá.
- Sử dụng dữ liệu đánh giá để theo dõi chất lượng dịch vụ.

---

## 3.4. Mối quan hệ giữa Business Goal và chức năng hệ thống

Business Goal mô tả **doanh nghiệp muốn đạt được điều gì**, còn chức năng mô tả **hệ thống phải làm gì để hỗ trợ đạt mục tiêu đó**.

Ví dụ:

**BG01 – Tự động hóa tìm và phân công tài xế**

Có thể được hỗ trợ bởi các chức năng:

- Đăng ký/đăng nhập tài xế.
- Cập nhật trạng thái sẵn sàng.
- Cập nhật vị trí tài xế.
- Tìm tài xế phù hợp.
- Gửi yêu cầu nhận chuyến.
- Chấp nhận/từ chối chuyến.
- Tìm tài xế tiếp theo.
- Thông báo không tìm được tài xế.

**BG02 – Hỗ trợ thanh toán linh hoạt**

Có thể được hỗ trợ bởi:

- Tính cước.
- Chọn phương thức thanh toán.
- Thanh toán tiền mặt.
- Thanh toán điện tử.
- Kiểm tra kết quả thanh toán.
- Thông báo kết quả thanh toán.
- Xử lý lại thanh toán thất bại.

---

## 3.5. Tổng kết

Các Business Goal chính của CAB System được xác định gồm:

**BG01:** Tự động hóa tìm và phân công tài xế.  
**BG02:** Hỗ trợ thanh toán linh hoạt.  
**BG03:** Cải thiện trải nghiệm đặt xe.  
**BG04:** Quản lý tập trung chuyến đi và giao dịch.  
**BG05:** Nâng cao hiệu quả vận hành.  
**BG06:** Cung cấp báo cáo cho doanh nghiệp.  
**BG07:** Nâng cao độ tin cậy và khả năng hoạt động.  
**BG08:** Đảm bảo an toàn và bảo mật dữ liệu.  
**BG09:** Hỗ trợ khả năng mở rộng trong tương lai.  
**BG10:** Nâng cao chất lượng dịch vụ thông qua phản hồi khách hàng.

Bước 4: Xác định phạm vi yêu cầu cần phải làm ( không làm lung tung những cái ko cần thiết), và những phạm vi yêu cầu không nên làm.
Ví dụ: Quản lý KH, Tài xế,

# 4. Phạm vi yêu cầu của hệ thống

## 4.1. Mục đích xác định phạm vi

Phạm vi hệ thống được xác định nhằm làm rõ những chức năng CAB System cần thực hiện trong dự án và những chức năng chưa được triển khai.

Việc xác định phạm vi giúp nhóm phát triển tập trung vào các yêu cầu chính, tránh phát triển những chức năng không cần thiết và hạn chế việc mở rộng phạm vi ngoài kế hoạch.

Thời gian xây dựng và triển khai sản phẩm dự kiến là **7 tuần**, vì vậy hệ thống trong giai đoạn đầu tập trung vào các chức năng cốt lõi của nền tảng đặt xe.

---

## 4.2. Phạm vi yêu cầu cần thực hiện (In Scope)

Các chức năng sau nằm trong phạm vi của CAB System.

| STT | Phạm vi | Nội dung cần thực hiện |
|---:|---|---|
| 1 | Quản lý khách hàng | Đăng ký, đăng nhập, cập nhật thông tin cá nhân và quản lý tài khoản khách hàng. |
| 2 | Quản lý tài xế | Quản lý tài khoản, hồ sơ, trạng thái hoạt động và thông tin tài xế. |
| 3 | Quản lý phương tiện | Quản lý thông tin phương tiện được sử dụng để thực hiện chuyến đi. |
| 4 | Đặt xe | Khách hàng nhập điểm đón, điểm đến, lựa chọn loại xe và gửi yêu cầu đặt xe. |
| 5 | Tìm tài xế | Hệ thống tìm tài xế phù hợp dựa trên vị trí, trạng thái sẵn sàng và tiêu chí vận hành. |
| 6 | Phân công tài xế | Gửi yêu cầu đến tài xế và xử lý trường hợp tài xế chấp nhận, từ chối hoặc không phản hồi. |
| 7 | Theo dõi chuyến đi | Khách hàng theo dõi tài xế và trạng thái hiện tại của chuyến đi. |
| 8 | Quản lý trạng thái chuyến | Tài xế cập nhật các trạng thái: đã đến điểm đón, đã đón khách, đang di chuyển và hoàn thành chuyến. |
| 9 | Quản lý vị trí tài xế | Lưu và sử dụng thông tin vị trí tài xế để hỗ trợ tìm tài xế gần khách hàng. |
| 10 | Tính cước | Xác định số tiền khách hàng phải trả dựa trên loại dịch vụ và thông tin chuyến đi. |
| 11 | Thanh toán | Hỗ trợ thanh toán tiền mặt và thanh toán điện tử thông qua nhà cung cấp bên ngoài. |
| 12 | Xử lý thanh toán thất bại | Thông báo kết quả và hỗ trợ xử lý lại thanh toán theo chính sách doanh nghiệp. |
| 13 | Thông báo | Gửi thông báo cho khách hàng và tài xế về các sự kiện quan trọng của chuyến đi. |
| 14 | Đánh giá tài xế | Cho phép khách hàng đánh giá tài xế sau khi hoàn thành chuyến. |
| 15 | Quản lý vận hành | Nhân viên vận hành quản lý khách hàng, tài xế, phương tiện và chuyến đi. |
| 16 | Xử lý chuyến có vấn đề | Cho phép nhân viên vận hành kiểm tra và hỗ trợ các trường hợp chuyến bị lỗi. |
| 17 | Quản lý giao dịch | Tra cứu lịch sử thanh toán và giao dịch. |
| 18 | Phân quyền | Kiểm soát quyền truy cập các chức năng quản trị. |
| 19 | Báo cáo | Báo cáo số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế. |
| 20 | Bảo mật và ghi log | Xác thực, phân quyền, bảo vệ dữ liệu và ghi nhận các thao tác quan trọng. |

---

## 4.3. Các phạm vi chính của hệ thống

Để dễ quản lý trong quá trình phát triển, phạm vi CAB System được chia thành các nhóm chính:

### 4.3.1. Quản lý khách hàng

Bao gồm:

- Đăng ký tài khoản.
- Đăng nhập.
- Cập nhật thông tin cá nhân.
- Xem lịch sử chuyến đi.
- Xem thông tin thanh toán.
- Đánh giá tài xế.

### 4.3.2. Quản lý tài xế

Bao gồm:

- Tạo và quản lý tài khoản tài xế.
- Cập nhật hồ sơ tài xế.
- Quản lý thông tin phương tiện.
- Bật/tắt trạng thái sẵn sàng nhận chuyến.
- Cập nhật vị trí.
- Nhận yêu cầu chuyến.
- Chấp nhận hoặc từ chối chuyến.

### 4.3.3. Quản lý chuyến đi

Bao gồm:

- Tạo yêu cầu đặt xe.
- Tìm tài xế.
- Phân công tài xế.
- Theo dõi trạng thái chuyến.
- Cập nhật trạng thái chuyến.
- Hoàn thành hoặc hủy chuyến theo chính sách.
- Lưu lịch sử chuyến đi.

### 4.3.4. Quản lý thanh toán

Bao gồm:

- Tính cước.
- Thanh toán tiền mặt.
- Thanh toán điện tử.
- Kiểm tra trạng thái thanh toán.
- Xử lý thanh toán thất bại.
- Lưu lịch sử giao dịch.

CAB System không lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán mà sử dụng nhà cung cấp thanh toán bên ngoài.

### 4.3.5. Quản lý thông báo

Bao gồm thông báo cho khách hàng và tài xế khi:

- Yêu cầu đặt xe được tiếp nhận.
- Tài xế nhận chuyến.
- Tài xế đến điểm đón.
- Chuyến đi hoàn thành.
- Thanh toán thành công hoặc thất bại.
- Có thay đổi liên quan đến chuyến đi.

Hệ thống được thiết kế theo hướng có thể bổ sung thêm các kênh thông báo trong tương lai.

### 4.3.6. Quản lý vận hành

Nhân viên vận hành có thể:

- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Xem các chuyến đang diễn ra.
- Kiểm tra trạng thái tài xế.
- Hỗ trợ xử lý chuyến bị lỗi.
- Tra cứu lịch sử chuyến.
- Tra cứu lịch sử giao dịch.

### 4.3.7. Báo cáo

Hệ thống cung cấp các báo cáo cơ bản:

- Số lượng chuyến.
- Doanh thu.
- Tỷ lệ hoàn thành chuyến.
- Tỷ lệ hủy chuyến.
- Hiệu quả hoạt động của tài xế.

---

# 4.4. Phạm vi không thực hiện (Out of Scope)

Các chức năng dưới đây **không nằm trong phạm vi triển khai cơ bản của dự án 7 tuần**, trừ khi khách hàng có yêu cầu bổ sung và nhóm dự án thống nhất thay đổi phạm vi.

| STT | Chức năng không thực hiện | Lý do |
|---:|---|---|
| 1 | Phát triển hệ thống quản lý kế toán đầy đủ | CAB chỉ quản lý thông tin thanh toán và giao dịch cần thiết cho dịch vụ đặt xe. |
| 2 | Lưu trực tiếp thông tin thẻ ngân hàng | Không cần thiết và làm tăng rủi ro bảo mật; sử dụng nhà cung cấp thanh toán bên ngoài. |
| 3 | Xây dựng nhà cung cấp thanh toán riêng | Doanh nghiệp đã định hướng tích hợp với nhà cung cấp bên ngoài. |
| 4 | Xây dựng hệ thống bản đồ riêng | Sử dụng dịch vụ bản đồ/vị trí bên ngoài. |
| 5 | Xây dựng hệ thống viễn thông hoặc SMS riêng | Có thể tích hợp nhà cung cấp thông báo bên ngoài. |
| 6 | Hệ thống tuyển dụng tài xế | Không thuộc quy trình đặt và quản lý chuyến đi cốt lõi. |
| 7 | Quản lý lương và nhân sự tài xế | Không thuộc phạm vi nghiệp vụ chính của CAB System. |
| 8 | Hệ thống chăm sóc khách hàng CRM hoàn chỉnh | Chỉ hỗ trợ các chức năng vận hành cần thiết trong phạm vi dự án. |
| 9 | Chương trình khuyến mãi phức tạp | Chưa có yêu cầu cụ thể từ khách hàng. |
| 10 | Hệ thống tích điểm thành viên | Chưa được xác định trong yêu cầu hiện tại. |
| 11 | Hệ thống quảng cáo | Không phục vụ trực tiếp quy trình đặt xe cốt lõi. |
| 12 | Chức năng mạng xã hội | Không thuộc phạm vi của nền tảng đặt xe. |
| 13 | Dự đoán nhu cầu bằng AI/Machine Learning | Không phải yêu cầu bắt buộc của giai đoạn đầu. |
| 14 | Xe tự lái | Không thuộc phạm vi nghiệp vụ của CAB System hiện tại. |
| 15 | Phân tích dữ liệu nâng cao bằng AI | Chưa cần thiết trong giai đoạn triển khai cơ bản. |

---

# 4.5. Phạm vi ưu tiên

Do thời gian triển khai chỉ 7 tuần, các chức năng được ưu tiên theo mức độ quan trọng.

### Mức 1 – Chức năng cốt lõi

Đây là các chức năng bắt buộc để CAB System có thể thực hiện quy trình đặt xe:

1. Quản lý khách hàng.
2. Quản lý tài xế.
3. Quản lý phương tiện.
4. Đặt xe.
5. Tìm tài xế.
6. Phân công tài xế.
7. Cập nhật trạng thái chuyến.
8. Theo dõi chuyến.
9. Tính cước.
10. Thanh toán.
11. Thông báo.

### Mức 2 – Chức năng hỗ trợ

- Đánh giá tài xế.
- Quản lý vận hành.
- Tra cứu lịch sử.
- Xử lý chuyến bị lỗi.
- Phân quyền.
- Báo cáo cơ bản.

### Mức 3 – Chức năng có thể phát triển sau

- Thêm loại dịch vụ mới.
- Thêm phương thức thanh toán.
- Thêm nhà cung cấp thông báo.
- Chương trình khuyến mãi.
- Tích điểm thành viên.
- Phân tích dữ liệu nâng cao.
- Các tính năng AI/ML.

---

## 4.6. Sơ đồ phạm vi hệ thống

```mermaid
flowchart LR
    KH[Khách hàng]
    TX[Tài xế]
    NV[Nhân viên vận hành]

    subgraph CAB["CAB System"]
        QLKH[Quản lý khách hàng]
        QLTX[Quản lý tài xế]
        QLPT[Quản lý phương tiện]
        DATXE[Đặt xe]
        TIMTX[Tìm và phân công tài xế]
        CHUYEN[Quản lý chuyến đi]
        CUOC[Tính cước]
        TT[Thanh toán]
        TB[Thông báo]
        DG[Đánh giá]
        VH[Quản lý vận hành]
        BC[Báo cáo]
    end

    PAYMENT[Nhà cung cấp thanh toán]
    MAP[Nhà cung cấp bản đồ / vị trí]
    NOTIFY[Nhà cung cấp thông báo]

    KH --> QLKH
    KH --> DATXE
    KH --> CHUYEN
    KH --> TT
    KH --> DG

    TX --> QLTX
    TX --> QLPT
    TX --> TIMTX
    TX --> CHUYEN

    NV --> VH
    NV --> BC

    DATXE --> TIMTX
    TIMTX --> MAP
    CHUYEN --> CUOC
    CUOC --> TT
    TT --> PAYMENT
    TB --> NOTIFY
    CHUYEN --> TB
Bước 5: Sau khi xong 4 thì cần gặp KH xác nhận lại nếu đúng và tiếp đến chuyển những yêu cầu thành Bussiness requiment, Xác nhận những cái BR ( ví dụ Br01 đặt chuyến xe) lập cái bảng ( cột 1 mã, cột 2 tên, cột 3 diễn giải )  

# 5. Business Requirements – Yêu cầu nghiệp vụ

## 5.1. Xác nhận yêu cầu với khách hàng

Sau khi hoàn thành việc phân tích sơ khởi, xác định Stakeholder, Business Goal và phạm vi hệ thống, Business Analyst cần trao đổi với khách hàng và các bên liên quan để xác nhận lại các nội dung đã phân tích.

Mục đích của bước xác nhận:

- Đảm bảo nhóm phát triển hiểu đúng nhu cầu của doanh nghiệp.
- Xác nhận các chức năng nằm trong phạm vi dự án.
- Xác nhận các chức năng không thuộc phạm vi.
- Phát hiện những yêu cầu còn thiếu.
- Làm rõ những yêu cầu chưa xác định.
- Tránh việc phát triển chức năng không cần thiết.
- Làm cơ sở để xây dựng Business Requirement.

### Nội dung cần xác nhận

| Nội dung | Trạng thái |
|---|---|
| Stakeholder | Cần xác nhận |
| Business Goal | Cần xác nhận |
| Phạm vi hệ thống | Cần xác nhận |
| Các chức năng chính | Cần xác nhận |
| Phương thức thanh toán | Cần xác nhận |
| Quy tắc tìm tài xế | Cần xác nhận |
| Chính sách hủy chuyến | Cần xác nhận |
| Chính sách thanh toán thất bại | Cần xác nhận |
| Chính sách lưu trữ dữ liệu | Cần xác nhận |

> **Lưu ý:** Trong tài liệu SRS, các nội dung chưa được khách hàng xác nhận cần được đánh dấu là "Cần xác nhận" thay vì tự giả định.

---

## 5.2. Business Requirement

Business Requirement (BR) mô tả những yêu cầu nghiệp vụ mà doanh nghiệp mong muốn hệ thống CAB System hỗ trợ.

Các Business Requirement được đánh mã theo dạng:

- BR01
- BR02
- BR03
- ...


## 5.3. Danh sách Business Requirements

| Mã | Tên Business Requirement | Diễn giải |
|---|---|---|
| BR01 | Đặt chuyến xe | Hệ thống phải cho phép khách hàng tạo yêu cầu đặt xe bằng cách nhập điểm đón, điểm đến và lựa chọn loại xe/dịch vụ. |
| BR02 | Quản lý khách hàng | Hệ thống phải hỗ trợ đăng ký, đăng nhập và quản lý thông tin tài khoản khách hàng. |
| BR03 | Quản lý tài xế | Hệ thống phải hỗ trợ quản lý thông tin tài khoản, hồ sơ và trạng thái hoạt động của tài xế. |
| BR04 | Quản lý phương tiện | Hệ thống phải hỗ trợ quản lý thông tin phương tiện của tài xế. |
| BR05 | Tìm kiếm tài xế | Hệ thống phải tự động tìm các tài xế phù hợp dựa trên vị trí, trạng thái sẵn sàng và các tiêu chí vận hành. |
| BR06 | Phân công tài xế | Hệ thống phải gửi yêu cầu chuyến đến tài xế phù hợp và xử lý trường hợp tài xế chấp nhận, từ chối hoặc không phản hồi. |
| BR07 | Theo dõi chuyến đi | Hệ thống phải cho phép khách hàng theo dõi tài xế và trạng thái hiện tại của chuyến đi. |
| BR08 | Cập nhật trạng thái chuyến | Hệ thống phải cho phép tài xế cập nhật trạng thái chuyến như đã đến điểm đón, đã đón khách, đang di chuyển và hoàn thành chuyến. |
| BR09 | Quản lý vị trí tài xế | Hệ thống phải ghi nhận thông tin vị trí của tài xế để hỗ trợ tìm kiếm và lựa chọn tài xế phù hợp. |
| BR10 | Tính cước chuyến đi | Hệ thống phải xác định số tiền khách hàng cần thanh toán dựa trên loại dịch vụ và thông tin chuyến đi. |
| BR11 | Thanh toán | Hệ thống phải hỗ trợ khách hàng thanh toán bằng tiền mặt hoặc phương thức thanh toán điện tử. |
| BR12 | Xử lý thanh toán thất bại | Hệ thống phải thông báo khi thanh toán điện tử thất bại và hỗ trợ xử lý lại theo chính sách của doanh nghiệp. |
| BR13 | Quản lý thông báo | Hệ thống phải gửi thông báo cho khách hàng và tài xế về các sự kiện quan trọng của chuyến đi và thanh toán. |
| BR14 | Đánh giá tài xế | Hệ thống phải cho phép khách hàng đánh giá tài xế sau khi chuyến đi hoàn thành. |
| BR15 | Quản lý vận hành | Hệ thống phải cung cấp giao diện cho nhân viên vận hành quản lý khách hàng, tài xế, phương tiện và chuyến đi. |
| BR16 | Xử lý chuyến có vấn đề | Hệ thống phải hỗ trợ nhân viên vận hành kiểm tra và xử lý các trường hợp chuyến đi bị lỗi hoặc bất thường. |
| BR17 | Quản lý giao dịch | Hệ thống phải cho phép tra cứu lịch sử thanh toán và giao dịch liên quan đến chuyến đi. |
| BR18 | Phân quyền người dùng | Hệ thống phải kiểm soát quyền truy cập dựa trên vai trò của người dùng. |
| BR19 | Báo cáo hoạt động | Hệ thống phải cung cấp báo cáo về số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả hoạt động của tài xế. |
| BR20 | Ghi nhận lịch sử thao tác | Hệ thống phải ghi lại các thao tác quan trọng để phục vụ kiểm tra và xử lý sự cố. |

## 5.4. Liên kết Business Goal và Business Requirement

| Business Goal | Business Requirement liên quan |
|---|---|
| BG01 – Tự động hóa tìm và phân công tài xế | BR05, BR06, BR09 |
| BG02 – Hỗ trợ thanh toán linh hoạt | BR10, BR11, BR12, BR17 |
| BG03 – Cải thiện trải nghiệm đặt xe | BR01, BR02, BR07, BR08, BR13, BR14 |
| BG04 – Quản lý tập trung chuyến đi và giao dịch | BR01, BR07, BR10, BR11, BR17 |
| BG05 – Nâng cao hiệu quả vận hành | BR03, BR04, BR15, BR16 |
| BG06 – Cung cấp thông tin và báo cáo | BR17, BR19 |
| BG07 – Nâng cao độ tin cậy | BR12, BR13, BR16 |
| BG08 – Đảm bảo an toàn và bảo mật | BR02, BR03, BR18, BR20 |
| BG09 – Hỗ trợ khả năng mở rộng | BR11, BR13 và các yêu cầu kiến trúc ở giai đoạn thiết kế |
| BG10 – Nâng cao chất lượng dịch vụ | BR14, BR19 |


Bước 6: XD các Bussiness Process.
### 6.2. Business Process tổng quát

```mermaid
flowchart TD
    A([Bắt đầu]) --> B[Khách hàng đăng nhập]
    B --> C[Nhập điểm đón và điểm đến]
    C --> D[Chọn loại xe]
    D --> E[Gửi yêu cầu đặt xe]

    E --> F[Hệ thống tìm tài xế]
    F --> G{Có tài xế phù hợp?}

    G -- Không --> H[Thông báo không tìm được tài xế]
    H --> Z([Kết thúc])

    G -- Có --> I[Gửi yêu cầu cho tài xế]
    I --> J{Tài xế chấp nhận?}

    J -- Không --> F
    J -- Có --> K[Phân công tài xế]

    K --> L[Tài xế đến điểm đón]
    L --> M[Đón khách]
    M --> N[Thực hiện chuyến]
    N --> O[Hoàn thành chuyến]

    O --> P[Tính cước]
    P --> Q[Thanh toán]
    Q --> R[Đánh giá tài xế]
    R --> S[Lưu lịch sử]
    S --> Z
```


Bước 7: Tiếp đến phân rã yêu cầu nghiệp vụ (FR) 

# 7. Functional Requirements – Phân rã yêu cầu chức năng

## 7.1. Khái niệm

Functional Requirement (FR) là các yêu cầu mô tả những chức năng mà hệ thống CAB System phải thực hiện để đáp ứng các Business Requirement (BR).

Business Requirement trả lời câu hỏi:

> Doanh nghiệp yêu cầu hệ thống hỗ trợ nghiệp vụ gì?

Functional Requirement trả lời câu hỏi:

> Hệ thống phải thực hiện những gì để hỗ trợ nghiệp vụ đó?

Các Functional Requirement được phân rã từ Business Requirement và được đánh mã theo dạng:

- FR01.01
- FR01.02
- FR01.03
- ...

Trong đó:

- FR01 là nhóm chức năng tương ứng với một Business Requirement.
- .01, .02, .03... là các chức năng nhỏ được phân rã từ Business Requirement đó.

---

## 7.2. Nguyên tắc phân rã

Mỗi Business Requirement có thể được phân rã thành một hoặc nhiều Functional Requirement.

Ví dụ:

**BR01 – Đặt chuyến xe**

được phân rã thành:

- FR01.01 – Nhập điểm đón.
- FR01.02 – Nhập điểm đến.
- FR01.03 – Lựa chọn loại xe.
- FR01.04 – Gửi yêu cầu đặt xe.
- FR01.05 – Kiểm tra thông tin đặt xe.
- FR01.06 – Tạo chuyến đi.

---

# 7.3. Danh sách Functional Requirements

| Mã FR | Mã BR | Tên Functional Requirement | Diễn giải |
|---|---|---|---|
| FR01.01 | BR01 | Nhập điểm đón | Hệ thống phải cho phép khách hàng nhập hoặc lựa chọn điểm đón. |
| FR01.02 | BR01 | Nhập điểm đến | Hệ thống phải cho phép khách hàng nhập hoặc lựa chọn điểm đến. |
| FR01.03 | BR01 | Lựa chọn loại xe | Hệ thống phải cho phép khách hàng lựa chọn loại xe/dịch vụ phù hợp. |
| FR01.04 | BR01 | Gửi yêu cầu đặt xe | Hệ thống phải cho phép khách hàng gửi yêu cầu đặt xe sau khi nhập đầy đủ thông tin. |
| FR01.05 | BR01 | Kiểm tra yêu cầu đặt xe | Hệ thống phải kiểm tra thông tin bắt buộc trước khi tạo chuyến. |
| FR01.06 | BR01 | Tạo chuyến đi | Hệ thống phải tạo yêu cầu chuyến đi và lưu thông tin chuyến. |
| FR02.01 | BR02 | Đăng ký khách hàng | Hệ thống phải cho phép khách hàng tạo tài khoản. |
| FR02.02 | BR02 | Đăng nhập | Hệ thống phải cho phép khách hàng đăng nhập bằng thông tin xác thực hợp lệ. |
| FR02.03 | BR02 | Cập nhật thông tin | Hệ thống phải cho phép khách hàng cập nhật thông tin cá nhân. |
| FR03.01 | BR03 | Quản lý hồ sơ tài xế | Hệ thống phải cho phép quản lý thông tin hồ sơ tài xế. |
| FR03.02 | BR03 | Cập nhật trạng thái tài xế | Hệ thống phải cho phép tài xế chuyển trạng thái sẵn sàng hoặc không sẵn sàng nhận chuyến. |
| FR03.03 | BR03 | Quản lý tài khoản tài xế | Hệ thống phải hỗ trợ tạo, cập nhật và quản lý tài khoản tài xế. |
| FR04.01 | BR04 | Quản lý phương tiện | Hệ thống phải cho phép lưu và cập nhật thông tin phương tiện. |
| FR04.02 | BR04 | Gán phương tiện cho tài xế | Hệ thống phải cho phép quản lý phương tiện được sử dụng bởi tài xế. |
| FR05.01 | BR05 | Tìm tài xế sẵn sàng | Hệ thống phải tìm các tài xế đang ở trạng thái sẵn sàng nhận chuyến. |
| FR05.02 | BR05 | Kiểm tra vị trí tài xế | Hệ thống phải sử dụng thông tin vị trí để xác định tài xế phù hợp. |
| FR05.03 | BR05 | Lọc tài xế phù hợp | Hệ thống phải lọc tài xế dựa trên loại dịch vụ và các tiêu chí vận hành. |
| FR05.04 | BR05 | Ưu tiên tài xế | Hệ thống phải ưu tiên tài xế theo tiêu chí do doanh nghiệp xác nhận. |
| FR06.01 | BR06 | Gửi yêu cầu nhận chuyến | Hệ thống phải gửi thông tin yêu cầu chuyến đến tài xế phù hợp. |
| FR06.02 | BR06 | Tài xế chấp nhận chuyến | Hệ thống phải ghi nhận khi tài xế chấp nhận chuyến. |
| FR06.03 | BR06 | Tài xế từ chối chuyến | Hệ thống phải ghi nhận khi tài xế từ chối chuyến. |
| FR06.04 | BR06 | Xử lý tài xế không phản hồi | Hệ thống phải xử lý trường hợp tài xế không phản hồi trong thời gian quy định. |
| FR06.05 | BR06 | Tìm tài xế tiếp theo | Hệ thống phải tiếp tục tìm tài xế khác khi tài xế được đề xuất từ chối hoặc không phản hồi. |
| FR06.06 | BR06 | Thông báo không tìm được tài xế | Hệ thống phải thông báo cho khách hàng khi không tìm được tài xế phù hợp. |
| FR07.01 | BR07 | Xem trạng thái chuyến | Hệ thống phải cho phép khách hàng xem trạng thái hiện tại của chuyến đi. |
| FR07.02 | BR07 | Xem thông tin tài xế | Hệ thống phải cho phép khách hàng xem thông tin tài xế đã nhận chuyến. |
| FR07.03 | BR07 | Theo dõi vị trí tài xế | Hệ thống phải hiển thị thông tin vị trí tài xế theo khả năng của dịch vụ vị trí được tích hợp. |
| FR08.01 | BR08 | Cập nhật đã đến điểm đón | Tài xế phải có thể cập nhật trạng thái đã đến điểm đón. |
| FR08.02 | BR08 | Cập nhật đã đón khách | Tài xế phải có thể cập nhật trạng thái đã đón khách. |
| FR08.03 | BR08 | Cập nhật đang di chuyển | Tài xế phải có thể cập nhật trạng thái đang di chuyển. |
| FR08.04 | BR08 | Cập nhật hoàn thành chuyến | Tài xế phải có thể cập nhật trạng thái hoàn thành chuyến. |
| FR09.01 | BR09 | Ghi nhận vị trí tài xế | Hệ thống phải ghi nhận thông tin vị trí của tài xế khi tài xế đang hoạt động. |
| FR09.02 | BR09 | Cập nhật vị trí | Hệ thống phải cập nhật vị trí tài xế theo cơ chế được xác định. |
| FR10.01 | BR10 | Tính cước | Hệ thống phải tính số tiền khách hàng cần thanh toán sau khi chuyến hoàn thành. |
| FR10.02 | BR10 | Xác định loại dịch vụ | Hệ thống phải sử dụng loại dịch vụ của chuyến để tính cước. |
| FR10.03 | BR10 | Lưu thông tin cước | Hệ thống phải lưu số tiền và thông tin cước của chuyến. |
| FR11.01 | BR11 | Chọn phương thức thanh toán | Hệ thống phải cho phép khách hàng lựa chọn phương thức thanh toán. |
| FR11.02 | BR11 | Thanh toán tiền mặt | Hệ thống phải hỗ trợ phương thức thanh toán bằng tiền mặt. |
| FR11.03 | BR11 | Thanh toán điện tử | Hệ thống phải hỗ trợ thanh toán điện tử thông qua nhà cung cấp bên ngoài. |
| FR11.04 | BR11 | Nhận kết quả thanh toán | Hệ thống phải nhận và cập nhật kết quả từ nhà cung cấp thanh toán. |
| FR12.01 | BR12 | Ghi nhận thanh toán thất bại | Hệ thống phải ghi nhận giao dịch thanh toán thất bại. |
| FR12.02 | BR12 | Thông báo thanh toán thất bại | Hệ thống phải thông báo cho khách hàng khi thanh toán thất bại. |
| FR12.03 | BR12 | Xử lý lại thanh toán | Hệ thống phải hỗ trợ xử lý lại thanh toán theo chính sách của doanh nghiệp. |
| FR13.01 | BR13 | Thông báo tiếp nhận yêu cầu | Hệ thống phải thông báo khi yêu cầu đặt xe được tiếp nhận. |
| FR13.02 | BR13 | Thông báo tài xế nhận chuyến | Hệ thống phải thông báo khi tài xế nhận chuyến. |
| FR13.03 | BR13 | Thông báo tài xế đến | Hệ thống phải thông báo khi tài xế đến điểm đón. |
| FR13.04 | BR13 | Thông báo hoàn thành chuyến | Hệ thống phải thông báo khi chuyến hoàn thành. |
| FR13.05 | BR13 | Thông báo kết quả thanh toán | Hệ thống phải thông báo kết quả thanh toán cho khách hàng. |
| FR14.01 | BR14 | Đánh giá tài xế | Hệ thống phải cho phép khách hàng đánh giá tài xế sau chuyến đi. |
| FR14.02 | BR14 | Lưu đánh giá | Hệ thống phải lưu thông tin đánh giá của khách hàng. |
| FR15.01 | BR15 | Quản lý khách hàng | Nhân viên vận hành phải có thể tra cứu và quản lý thông tin khách hàng theo quyền được cấp. |
| FR15.02 | BR15 | Quản lý tài xế | Nhân viên vận hành phải có thể tra cứu và quản lý thông tin tài xế theo quyền được cấp. |
| FR15.03 | BR15 | Quản lý phương tiện | Nhân viên vận hành phải có thể tra cứu và quản lý thông tin phương tiện. |
| FR15.04 | BR15 | Theo dõi chuyến đang diễn ra | Nhân viên vận hành phải có thể xem các chuyến đang thực hiện. |
| FR16.01 | BR16 | Xem chuyến có vấn đề | Nhân viên vận hành phải có thể xem thông tin các chuyến gặp sự cố. |
| FR16.02 | BR16 | Hỗ trợ xử lý chuyến | Nhân viên vận hành phải có thể thực hiện các thao tác hỗ trợ theo quyền được cấp. |
| FR17.01 | BR17 | Tra cứu giao dịch | Nhân viên được phân quyền phải có thể tra cứu lịch sử giao dịch. |
| FR17.02 | BR17 | Xem trạng thái giao dịch | Hệ thống phải hiển thị trạng thái của giao dịch. |
| FR18.01 | BR18 | Xác thực người dùng | Hệ thống phải xác thực người dùng trước khi cho phép truy cập chức năng yêu cầu tài khoản. |
| FR18.02 | BR18 | Phân quyền | Hệ thống phải kiểm soát quyền truy cập dựa trên vai trò. |
| FR18.03 | BR18 | Kiểm soát thao tác quản trị | Hệ thống phải hạn chế các thao tác nhạy cảm đối với người dùng không có quyền. |
| FR19.01 | BR19 | Báo cáo số lượng chuyến | Hệ thống phải cung cấp báo cáo về số lượng chuyến. |
| FR19.02 | BR19 | Báo cáo doanh thu | Hệ thống phải cung cấp báo cáo doanh thu. |
| FR19.03 | BR19 | Báo cáo tỷ lệ hoàn thành | Hệ thống phải cung cấp tỷ lệ chuyến hoàn thành. |
| FR19.04 | BR19 | Báo cáo tỷ lệ hủy | Hệ thống phải cung cấp tỷ lệ chuyến bị hủy. |
| FR19.05 | BR19 | Báo cáo hiệu quả tài xế | Hệ thống phải cung cấp thông tin phục vụ đánh giá hiệu quả tài xế. |
| FR20.01 | BR20 | Ghi log thao tác | Hệ thống phải ghi nhận các thao tác quan trọng. |
| FR20.02 | BR20 | Tra cứu log | Người dùng có quyền phải có thể tra cứu lịch sử thao tác phục vụ kiểm tra sự cố. |

---

# 7.4. Phân rã một số Business Requirement quan trọng

## BR01 – Đặt chuyến xe

Business Requirement:

> Hệ thống phải cho phép khách hàng tạo yêu cầu đặt xe.

Được phân rã thành:

```text
BR01 – Đặt chuyến xe
        │
        ├── FR01.01 – Nhập điểm đón
        ├── FR01.02 – Nhập điểm đến
        ├── FR01.03 – Lựa chọn loại xe
        ├── FR01.04 – Gửi yêu cầu đặt xe
        ├── FR01.05 – Kiểm tra yêu cầu
        └── FR01.06 – Tạo chuyến đi
