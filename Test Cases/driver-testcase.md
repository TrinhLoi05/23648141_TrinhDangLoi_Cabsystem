# TEST CASE – DRIVER

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-DRIVER-001 | TS-DRIVER-01 – Quản lý hồ sơ tài xế | Tạo tài xế với dữ liệu hợp lệ | Admin/Operator có quyền. | 1. POST /drivers.<br>2. Nhập fullName và phone hợp lệ. | fullName: Nguyễn Văn B<br>phone: 0912345678<br>licenseNumber: GPLX123 | Tạo Driver thành công. | High |
| TC-DRIVER-002 | TS-DRIVER-01 – Quản lý hồ sơ tài xế | Thiếu fullName | Admin/Operator có quyền. | 1. Để fullName rỗng.<br>2. Gửi request. | fullName: empty<br>phone: 0912345678 | Hệ thống báo lỗi. | High |
| TC-DRIVER-003 | TS-DRIVER-01 – Quản lý hồ sơ tài xế | Thiếu phone | Admin/Operator có quyền. | 1. Để phone rỗng.<br>2. Gửi request. | phone: empty | Hệ thống báo lỗi. | High |
| TC-DRIVER-004 | TS-DRIVER-01 – Quản lý hồ sơ tài xế | Cập nhật hồ sơ hợp lệ | Driver tồn tại; user có quyền. | 1. PATCH /drivers/{driverId}.<br>2. Sửa thông tin.<br>3. Kiểm tra dữ liệu. | driverId: DRV001<br>fullName: Nguyễn Văn Bình | Cập nhật thành công. | High |
| TC-DRIVER-005 | TS-DRIVER-01 – Quản lý hồ sơ tài xế | Không có quyền quản lý Driver | Customer đã đăng nhập. | 1. Gửi yêu cầu quản lý Driver.<br>2. Kiểm tra kết quả. | Token Customer | Hệ thống từ chối theo BRULE10/EX07. | High |
| TC-DRIVER-006 | TS-DRIVER-02 – Cập nhật trạng thái sẵn sàng | Cập nhật trạng thái AVAILABLE | Driver đã đăng nhập. | 1. PATCH /drivers/{driverId}/availability.<br>2. Gửi status.<br>3. Kiểm tra kết quả. | status: AVAILABLE | Cập nhật thành công; status=AVAILABLE. | High |
| TC-DRIVER-007 | TS-DRIVER-02 – Cập nhật trạng thái sẵn sàng | Cập nhật trạng thái BUSY | Driver đã đăng nhập. | 1. PATCH /drivers/{driverId}/availability.<br>2. Gửi status.<br>3. Kiểm tra kết quả. | status: BUSY | Cập nhật thành công; status=BUSY. | High |
| TC-DRIVER-008 | TS-DRIVER-02 – Cập nhật trạng thái sẵn sàng | Cập nhật trạng thái OFFLINE | Driver đã đăng nhập. | 1. PATCH /drivers/{driverId}/availability.<br>2. Gửi status.<br>3. Kiểm tra kết quả. | status: OFFLINE | Cập nhật thành công; status=OFFLINE. | High |
| TC-DRIVER-009 | TS-DRIVER-02 – Cập nhật trạng thái sẵn sàng | Status rỗng | Driver đã đăng nhập. | 1. Gửi status rỗng.<br>2. Kiểm tra kết quả. | status: empty | Hệ thống báo dữ liệu không hợp lệ. | High |
| TC-DRIVER-010 | TS-DRIVER-02 – Cập nhật trạng thái sẵn sàng | Status ngoài enum | Driver đã đăng nhập. | 1. Gửi status không hợp lệ.<br>2. Kiểm tra kết quả. | status: READY | Hệ thống từ chối dữ liệu. | High |
| TC-DRIVER-011 | TS-DRIVER-02 – Cập nhật trạng thái sẵn sàng | Driver BUSY/OFFLINE không được tìm để nhận chuyến | Driver đang BUSY hoặc OFFLINE. | 1. Cập nhật BUSY/OFFLINE.<br>2. Thực hiện matching.<br>3. Kiểm tra Driver được chọn. | status: BUSY | Driver không được chọn theo BRULE02. | High |
| TC-DRIVER-012 | TS-VEHICLE-01 – Quản lý phương tiện | Thêm phương tiện hợp lệ | Driver tồn tại; user có quyền. | 1. POST /drivers/{driverId}/vehicles.<br>2. Nhập vehicleType và licensePlate. | vehicleType: CAR_4_SEAT<br>licensePlate: 51A-123.45 | Tạo Vehicle thành công. | High |
| TC-DRIVER-013 | TS-VEHICLE-01 – Quản lý phương tiện | Thiếu vehicleType | Driver tồn tại. | 1. Để vehicleType rỗng.<br>2. Gửi request. | vehicleType: empty | Hệ thống báo lỗi. | High |
| TC-DRIVER-014 | TS-VEHICLE-01 – Quản lý phương tiện | Thiếu licensePlate | Driver tồn tại. | 1. Để licensePlate rỗng.<br>2. Gửi request. | licensePlate: empty | Hệ thống báo lỗi. | High |
| TC-DRIVER-015 | TS-VEHICLE-01 – Quản lý phương tiện | Cập nhật phương tiện hợp lệ | Vehicle tồn tại; user có quyền. | 1. PATCH /vehicles/{vehicleId}.<br>2. Sửa thông tin.<br>3. Kiểm tra kết quả. | vehicleId: VEH001<br>brand: Toyota | Cập nhật thành công. | High |
| TC-DRIVER-016 | TS-VEHICLE-01 – Quản lý phương tiện | Vehicle không tồn tại | User có quyền. | 1. PATCH vehicleId không tồn tại.<br>2. Kiểm tra kết quả. | vehicleId: VEH999 | Hệ thống báo không tìm thấy. | High |
