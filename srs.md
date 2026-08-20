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
Bước 2: Xác định các bên liên quan và cột 1 là stack holder 1 cột là vai trò của nó, vẽ 1 ma trận stack holder matrix cho biết Dùng memate github để vẽ các sơ đồ trong markdown,  
| Stakeholder                                        | Vai trò                                                                                                          |
| -------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **Khách hàng (Customer)**                          | Đăng ký, đăng nhập, đặt xe, theo dõi chuyến đi, thanh toán và đánh giá tài xế.                                   |
| **Tài xế (Driver)**                                | Đăng ký/nhận tài khoản, quản lý phương tiện, nhận hoặc từ chối chuyến, cập nhật trạng thái và hoàn thành chuyến. |
| **Nhân viên vận hành (Operator)**                  | Theo dõi chuyến đi, quản lý tài xế, hỗ trợ xử lý chuyến lỗi và giám sát hoạt động hằng ngày.                     |
| **Quản trị viên (Administrator)**                  | Quản lý tài khoản, phân quyền, cấu hình hệ thống và các chức năng quản trị nhạy cảm.                             |
| **Ban giám đốc (Management)**                      | Định hướng hoạt động, theo dõi doanh thu, số lượng chuyến, tỷ lệ hoàn thành/hủy và hiệu quả kinh doanh.          |
| **Bộ phận CSKH (Customer Service)**                | Tiếp nhận và xử lý khiếu nại, hỗ trợ khách hàng và tài xế khi có sự cố.                                          |
| **Bộ phận tài chính/kế toán (Finance)**            | Theo dõi doanh thu, giao dịch thanh toán và đối soát giao dịch.                                                  |
| **Nhà cung cấp thanh toán (Payment Provider)**     | Xử lý các giao dịch thanh toán điện tử bên ngoài hệ thống CAB.                                                   |
| **Nhà cung cấp thông báo (Notification Provider)** | Cung cấp SMS, Email, Push Notification hoặc các kênh thông báo khác.                                             |


Bước 3: Xác định mục đích của nghiệp vụ, Liệt kê các Bussiness Goal
Dựa trên yêu cầu của khách hàng, có thể xác định 10 Business Goals chính.
| ID       | Business Goal                                   | Ý nghĩa                                                             |
| -------- | ----------------------------------------------- | ------------------------------------------------------------------- |
| **BG01** | Tự động hóa quy trình đặt xe                    | Giảm phụ thuộc vào tổng đài và thao tác thủ công                    |
| **BG02** | Tăng tỷ lệ tìm được tài xế                      | Đảm bảo khách hàng có thể tìm được tài xế phù hợp                   |
| **BG03** | Giảm thời gian phân công tài xế                 | Tự động tìm và ưu tiên tài xế gần khách hàng                        |
| **BG04** | Nâng cao trải nghiệm khách hàng                 | Cho phép đặt xe, theo dõi chuyến, thanh toán và đánh giá thuận tiện |
| **BG05** | Tăng hiệu quả hoạt động của tài xế              | Giúp tài xế nhận các chuyến phù hợp và giảm thời gian chờ           |
| **BG06** | Quản lý tập trung dữ liệu                       | Tập trung dữ liệu khách hàng, tài xế, chuyến đi và thanh toán       |
| **BG07** | Tăng khả năng kiểm soát doanh nghiệp            | Cung cấp dashboard, báo cáo và audit log                            |
| **BG08** | Quản lý doanh thu và thanh toán hiệu quả        | Theo dõi giao dịch và giảm sai sót trong thanh toán                 |
| **BG09** | Đảm bảo hệ thống ổn định và có khả năng mở rộng | Đáp ứng số lượng khách hàng/tài xế tăng trong tương lai             |
| **BG10** | Tạo nền tảng phát triển lâu dài                 | Có thể bổ sung dịch vụ, phương thức thanh toán và notification mới  |

Bước 4: Xác định phạm vi yêu cầu cần phải làm ( không làm lung tung những cái ko cần thiết), và những phạm vi yêu cầu không nên làm.
Ví dụ: Quản lý KH, Tài xế,
