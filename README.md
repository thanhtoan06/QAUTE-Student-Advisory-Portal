## Giới thiệu website

QAUTE là hệ thống tư vấn trực tuyến dành cho sinh viên Đại học Công nghệ Kỹ thuật TP.HCM (HCMUTE). Website được phát triển nhằm giải quyết các vấn đề thường gặp của sinh viên trong quá trình học tập, từ những câu hỏi cơ bản về quy định nhà trường, đăng ký tín chỉ, học phí, cho đến các vấn đề chuyên sâu liên quan đến từng ngành học.

Hệ thống hoạt động như một cầu nối giữa sinh viên và đội ngũ tư vấn viên (Manager), giúp sinh viên có thể nhanh chóng tìm kiếm câu trả lời cho các thắc mắc thông qua hệ thống FAQ (Câu hỏi thường gặp), gửi yêu cầu tư vấn qua hệ thống Ticket, trò chuyện trực tiếp với tư vấn viên qua Chat thời gian thực, hoặc đặt lịch hẹn để được tư vấn trực tiếp. Đối với nhà trường, hệ thống cung cấp công cụ quản lý toàn diện cho Quản trị viên (Admin) và Tư vấn viên (Manager), giúp theo dõi, phân tích và cải thiện chất lượng dịch vụ tư vấn.

Với giao diện thân thiện, hiện đại sử dụng Bootstrap Tabler, QAUTE mang lại trải nghiệm người dùng tốt trên cả máy tính và thiết bị di động. Hệ thống tích hợp nhiều tính năng hiện đại như xác thực JWT, chat thời gian thực qua WebSocket, quản lý lịch hẹn thông minh, và hệ thống báo cáo thống kê chi tiết, giúp tối ưu hóa quy trình tư vấn và nâng cao sự hài lòng của sinh viên.

---

## Công nghệ sử dụng

- **Ngôn ngữ và nền tảng:** Java 25, Spring Boot 3.5.16, Maven
- **Web:** Spring MVC, JSP, JSTL, Apache Tomcat, SiteMesh
- **Giao diện:** Tabler, Bootstrap Icons, CSS và JavaScript thuần
- **Cơ sở dữ liệu:** MySQL, Spring Data JPA/Hibernate
- **Quản lý phiên bản cơ sở dữ liệu:** Flyway
- **Bảo mật:** Spring Security, JWT, Google OAuth 2.0, mã hóa mật khẩu và phân quyền theo vai trò
- **Thời gian thực:** WebSocket
- **Email:** Spring Boot Mail/SMTP
- **Lưu trữ tệp:** Cloudinary
- **Tiện ích:** Lombok, Apache Tika, OWASP Java HTML Sanitizer, Bucket4j

---

## 4 vai trò trong hệ thống

Hệ thống QAUTE có 4 vai trò người dùng chính:

1. **Guest (Khách)**: Người dùng chưa đăng nhập, có thể xem FAQ công khai và thông báo công khai
2. **Student (Sinh viên)**: Người dùng chính của hệ thống, sinh viên HCMUTE
3. **Manager (Tư vấn viên)**: Nhân viên tư vấn, hỗ trợ sinh viên theo phạm vi được phân công
4. **Admin (Quản trị viên)**: Quản trị hệ thống, có toàn quyền quản lý

---

## Chức năng theo vai trò

### 1. Guest (Khách - Chưa đăng nhập)

#### 1.1. Trang chủ

- Xem danh mục FAQ theo cấu trúc cây
- Xem FAQ nổi bật
- Xem FAQ xem nhiều nhất
- Xem FAQ mới nhất
- Xem thông báo công khai
- Xem thống kê nhanh
- Xem thông tin liên hệ

#### 1.2. Tra cứu FAQ công khai

- Tìm kiếm FAQ theo từ khóa
- Lọc FAQ theo danh mục
- Lọc FAQ theo tag
- Sắp xếp FAQ theo: mới nhất, xem nhiều, hữu ích nhất
- Xem chi tiết FAQ
- Xem FAQ liên quan
- Phân trang danh sách FAQ

#### 1.3. Xem thông báo công khai

- Xem danh sách thông báo công khai
- Xem chi tiết thông báo
- Phân trang thông báo

#### 1.4. Đăng nhập

- Đăng nhập bằng email hoặc MSSV
- Đăng nhập bằng Google OAuth2
- Quên mật khẩu: gửi OTP qua email để đặt lại

---

### 2. Student (Sinh viên)

#### 2.1. Dashboard cá nhân

- Xem tổng quan: số ticket, số chat, số lịch hẹn
- Xem thông báo mới
- Truy cập nhanh đến các chức năng

#### 2.2. FAQ

- Tra cứu FAQ với đầy đủ tính năng công khai
- Bookmark (lưu lại) FAQ yêu thích
- Xem danh sách FAQ đã bookmark
- Đánh giá FAQ: hữu ích hoặc không hữu ích
- Xem FAQ đã xem gần đây
- Gửi đề xuất FAQ mới
- Tìm kiếm FAQ với lịch sử tìm kiếm cá nhân
- Xem FAQ theo tab: mới nhất, xem nhiều, hữu ích, đã lưu

#### 2.3. Ticket

- Tạo ticket mới với đầy đủ thông tin
- Chọn danh mục/phòng ban
- Chọn mức độ ưu tiên
- Upload file đính kèm (tối đa 10MB)
- Xem danh sách ticket của mình
- Lọc ticket theo trạng thái, danh mục
- Xem chi tiết ticket
- Theo dõi trạng thái ticket
- Xem lịch sử tương tác trên ticket
- Phản hồi ticket

#### 2.4. Chat

- Bắt đầu phiên chat mới
- Chọn danh mục vấn đề
- Nhập câu hỏi ban đầu
- Chat thời gian thực với tư vấn viên qua WebSocket
- Xem lịch sử chat
- Đánh giá phiên chat (1-5 sao)
- Gửi kèm file trong chat
- Chuyển chat thành ticket nếu cần
- Hủy phiên chat

#### 2.5. Lịch hẹn

- Xem lịch làm việc của các tư vấn viên
- Chọn tư vấn viên theo danh mục
- Xem các khung giờ trống
- Đặt lịch hẹn
- Xem danh sách lịch hẹn: sắp tới, đã qua, đã hủy
- Xem chi tiết lịch hẹn
- Hủy lịch hẹn (với lý do bắt buộc)
- Đổi lịch hẹn sang khung giờ khác
- Tải file ICS để thêm vào calendar
- Nhận thông báo nhắc lịch hẹn

#### 2.6. Thông báo

- Nhận thông báo về: ticket mới, phản hồi ticket, chat mới, lịch hẹn, FAQ được duyệt
- Xem danh sách thông báo
- Lọc thông báo đã đọc/chưa đọc
- Đánh dấu thông báo đã đọc
- Đánh dấu tất cả đã đọc
- Ẩn thông báo
- Click thông báo để chuyển đến trang liên quan
- Thống kê số thông báo chưa đọc
- Tùy chọn thông báo: tắt/bật loại thông báo muốn nhận

#### 2.7. Quản lý hồ sơ

- Xem và cập nhật thông tin cá nhân (họ tên, email, số điện thoại)
- Thay đổi mật khẩu
- Upload avatar (ảnh đại diện)
- Xem thông tin tài khoản
- Xem session đang đăng nhập
- Đăng xuất an toàn

---

### 3. Manager (Tư vấn viên)

#### 3.1. Dashboard cá nhân

- Xem tổng quan: số ticket đã xử lý, số chat đã xử lý, số lịch hẹn
- Xem ticket đang chờ xử lý
- Xem chat đang chờ
- Xem thống kê hiệu suất cá nhân

#### 3.2. Xử lý Ticket

- Xem hàng đợi ticket theo phạm vi quản lý
- Lọc ticket theo: danh mục, ưu tiên, trạng thái, manager phụ trách, độ tuổi ticket
- Nhận ticket để xử lý
- Phản hồi ticket
- Chuyển ticket cho manager khác (trong phạm vi)
- Ghi chú nội bộ
- Can thiệp ticket với lý do bắt buộc
- Đóng ticket
- Đánh dấu ticket khẩn cấp
- Chuyển ticket thành FAQ
- Sử dụng mẫu trả lời nhanh
- Xem lịch sử thay đổi ticket

#### 3.3. Chat Desk

- Xem hàng chờ chat theo phạm vi quản lý
- Lọc theo danh mục
- Nhận phiên chat
- Chat thời gian thực với sinh viên
- Xem thông tin sinh viên đang chat
- Chuyển phiên chat cho manager khác
- Kết thúc phiên chat
- Xem các phiên chat đang xử lý
- Sử dụng mẫu trả lời nhanh
- Kiểm tra sức chứa (số phiên chat tối đa)

#### 3.4. Quản lý FAQ

- Tạo FAQ mới trong phạm vi chuyên môn
- Chỉnh sửa FAQ bản nháp
- Gửi FAQ chờ duyệt
- Xem lịch sử thay đổi FAQ
- Chuyển ticket thành FAQ
- Quản lý FAQ theo trạng thái: nháp, chờ duyệt, đã xuất bản, từ chối
- Xem FAQ theo trạng thái

#### 3.5. Quản lý Lịch hẹn

- Xem lịch làm việc cá nhân theo tuần
- Xem các lịch hẹn đã đặt
- Xem lịch hẹn theo trạng thái: sắp tới, đã hoàn tất, vắng mặt, đã hủy
- Chấp nhận lịch hẹn (nếu cần duyệt)
- Hoàn tất lịch hẹn với ghi chú kết quả
- Đánh dấu sinh viên vắng mặt
- Hủy lịch hẹn (với lý do bắt buộc)
- Xem thông tin sinh viên đặt lịch

#### 3.6. Quản lý Lịch làm việc

- Xem lịch làm việc theo tuần/lưới 7 ngày
- Tạo quy tắc lịch làm việc (ví dụ: thứ 2-6, 8h-17h)
- Thiết lập thời gian mỗi slot (ví dụ: 30 phút)
- Chặn khung giờ cụ thể (ví dụ: họp, nghỉ)
- Xóa quy tắc lịch làm việc
- Xóa khung chặn
- Tự động tạo khung giờ dựa trên quy tắc

#### 3.7. Hồ sơ sinh viên

- Xem thông tin cá nhân sinh viên
- Xem lịch sử ticket của sinh viên
- Xem lịch sử chat của sinh viên
- Xem lịch sử lịch hẹn của sinh viên
- Xem FAQ sinh viên đã xem
- Xem FAQ sinh viên đã bookmark
- Kiểm tra quyền truy cập trước khi xem

#### 3.8. Mẫu trả lời nhanh

- Tạo mẫu trả lời nhanh
- Chỉnh sửa mẫu trả lời
- Xóa mẫu trả lời
- Gán mẫu trả lời theo danh mục
- Sử dụng biến động (ví dụ: tên sinh viên, mã ticket)
- Sử dụng mẫu khi phản hồi ticket
- Sử dụng mẫu khi chat

#### 3.9. Báo cáo cá nhân

- Xem thống kê ticket đã xử lý
- Xem thống kê chat đã xử lý
- Xem thống kê lịch hẹn
- Xuất báo cáo ra file CSV

#### 3.10. Quản lý hồ sơ cá nhân

- Xem và cập nhật thông tin cá nhân
- Thay đổi mật khẩu
- Upload avatar
- Xem session đang đăng nhập
- Đăng xuất

---

### 4. Admin (Quản trị viên)

#### 4.1. Dashboard toàn hệ thống

- Xem tổng quan toàn hệ thống: số user, số ticket, số FAQ, số chat, số lịch hẹn
- Xem thống kê theo thời gian
- Xem hoạt động gần đây

#### 4.2. Quản lý người dùng

- Tạo tài khoản mới (Admin, Manager, Student)
- Chỉnh sửa thông tin tài khoản
- Khóa/mở khóa tài khoản
- Vô hiệu hóa tài khoản
- Hạ vai trò (demote)
- Gửi email mời kích hoạt tài khoản
- Gửi lại email kích hoạt
- Import danh sách user từ file CSV
- Xuất danh sách user ra file CSV
- Xem chi tiết user
- Quản lý Manager Scope: phân công Manager quản lý theo phòng ban/danh mục

#### 4.3. Quản lý FAQ toàn hệ thống

- Duyệt hoặc từ chối FAQ do Manager đề xuất
- Tạo/sửa/xóa FAQ toàn hệ thống
- Quản lý phiên bản FAQ
- Xem lịch sử thay đổi FAQ
- Quản lý lý do từ chối FAQ
- Import FAQ từ file CSV
- Xuất FAQ ra file CSV

#### 4.4. Quản lý Ticket toàn hệ thống

- Xem tất cả ticket toàn hệ thống
- Can thiệp ticket bất kỳ
- Chuyển ticket bất kỳ
- Đóng ticket bất kỳ
- Xem thống kê ticket
- Xuất báo cáo ticket ra file CSV

#### 4.5. Quản lý phòng ban

- Tạo, chỉnh sửa, xóa phòng ban
- Cấu trúc cây phòng ban
- Bật/tắt phòng ban
- Kiểm tra ticket đang mở trước khi tắt

#### 4.6. Quản lý danh mục

- Tạo, chỉnh sửa, xóa danh mục FAQ/ticket
- Cấu trúc cây danh mục
- Gán danh mục cho phòng ban

#### 4.7. Quản lý SLA

- Cấu hình thời gian phản hồi theo loại vấn đề
- Cấu hình thời gian xử lý theo mức độ ưu tiên
- Tạo/sửa/xóa cấu hình SLA
- Theo dõi vi phạm SLA

#### 4.8. Quản lý Settings

- Cấu hình thông tin website: tên, email liên hệ, số điện thoại
- Cấu hình giới hạn upload file
- Cấu hình giới hạn chat
- Cấu hình các thông số hệ thống khác
- Cấu hình email SMTP
- Cấu hình Cloudinary (nếu dùng)

#### 4.9. Quản lý Tag và Synonym

- Tạo, chỉnh sửa, xóa tag
- Quản lý từ đồng nghĩa (synonym) để cải thiện tìm kiếm
- Gán tag cho FAQ

#### 4.10. Quản lý thông báo công khai

- Tạo thông báo công khai
- Chọn đối tượng: tất cả, sinh viên, manager
- Upload ảnh bìa
- Viết nội dung HTML (được sanitize)
- Thiết lập thời gian hiển thị
- Sửa/xóa thông báo
- Xem danh sách thông báo

#### 4.11. Audit Log

- Ghi log tất cả thao tác quan trọng
- Xem lịch sử hoạt động
- Lọc theo người dùng, hành động, thời gian
- Xuất audit log ra file CSV
- Ghi log: tạo user, khóa user, can thiệp ticket, duyệt FAQ, v.v.

#### 4.12. Health Check

- Kiểm tra kết nối database
- Kiểm tra kết nối email
- Kiểm tra dịch vụ hệ thống
- Gửi email test

#### 4.13. Báo cáo toàn hệ thống

- Thống kê ticket theo trạng thái, danh mục, manager
- Thống kê thời gian phản hồi và xử lý
- Thống kê chat và đánh giá
- Thống kê lịch hẹn
- Thống kê FAQ xem nhiều, hữu ích
- Xuất tất cả báo cáo ra file CSV

#### 4.14. Quản lý Media

- Xem danh sách file đã upload
- Xóa file không dùng
- Kiểm tra dung lượng lưu trữ

---

## Kiến trúc và cấu trúc thư mục

Ứng dụng được tổ chức theo kiến trúc nhiều lớp, tách biệt phần giao diện, xử lý nghiệp vụ, truy cập dữ liệu và cấu hình bảo mật.

```text
qaute/
├── pom.xml                         # Khai báo phụ thuộc và cấu hình Maven
├── mvnw, mvnw.cmd                  # Maven Wrapper
├── src/main/java/.../qaute/
│   ├── config/                     # Cấu hình ứng dụng, WebSocket, Cloudinary
│   ├── controller/                 # Controller cho các trang và luồng nghiệp vụ
│   ├── dto/                        # Đối tượng truyền dữ liệu
│   ├── entity/                     # Entity JPA
│   ├── repository/                 # Truy vấn và thao tác dữ liệu
│   ├── security/                   # Xác thực, phân quyền và JWT
│   ├── service/                    # Xử lý nghiệp vụ
│   └── websocket/                  # Chức năng chat thời gian thực
├── src/main/resources/
│   ├── application*.properties     # Cấu hình theo môi trường
│   ├── db/migration/                # Các migration Flyway
│   ├── mail-templates/              # Mẫu email
│   └── static/                      # CSS, JavaScript và hình ảnh
└── src/main/webapp/WEB-INF/
    ├── decorators/                  # Layout theo từng nhóm người dùng
    ├── tags/                        # JSP tag dùng chung
    └── views/                       # Các trang JSP
```

---

## Yêu cầu hệ thống

- JDK **25**
- MySQL Server đang hoạt động
- Maven 3.9 trở lên (không bắt buộc nếu sử dụng Maven Wrapper)
- Trình duyệt hiện đại như Chrome, Edge hoặc Firefox
- Kết nối Internet nếu sử dụng Google OAuth2, SMTP hoặc Cloudinary

---

## Cấu hình môi trường

Ứng dụng sử dụng các profile Spring Boot sau:

- `dev`: kết nối MySQL cục bộ và cấu hình dịch vụ phát triển
- `demo`: tạo dữ liệu mẫu và các tài khoản demo
- `google`: bật đăng nhập bằng Google OAuth2

Có thể tạo tệp `src/main/resources/application-local.properties` để ghi đè cấu hình cục bộ. Hãy thêm tệp này vào `.gitignore` trước khi lưu thông tin nhạy cảm; không đưa mật khẩu, khóa JWT, thông tin SMTP, OAuth2 hoặc Cloudinary lên kho mã nguồn.

Các cấu hình quan trọng gồm:

| Cấu hình                                                      | Mục đích                        |
| --------------------------------------------------------------- | ---------------------------------- |
| `spring.datasource.url`                                       | Địa chỉ cơ sở dữ liệu MySQL |
| `spring.datasource.username` / `spring.datasource.password` | Tài khoản MySQL                  |
| `spring.mail.*`                                               | Cấu hình máy chủ gửi email    |
| `app.jwt.secret`                                              | Khóa ký JWT                      |
| `app.otp.hmac-secret`                                         | Khóa bảo vệ OTP                 |
| `spring.security.oauth2.client.*`                             | Thông tin Google OAuth2           |
| `cloudinary.url`                                              | Kết nối dịch vụ lưu trữ tệp |

Flyway sẽ tự động chạy các migration trong `src/main/resources/db/migration` khi ứng dụng khởi động. Cơ sở dữ liệu `qaute` có thể được tạo tự động khi chuỗi kết nối cho phép `createDatabaseIfNotExist=true`.

---

## Hướng dẫn chạy trên Windows

### 1. Chuẩn bị cơ sở dữ liệu

Khởi động MySQL và bảo đảm tài khoản trong cấu hình có quyền tạo hoặc sử dụng cơ sở dữ liệu `qaute`. Nếu thông tin kết nối mặc định không phù hợp, hãy ghi đè bằng `application-local.properties`.

### 2. Khởi động ứng dụng

Mở PowerShell tại thư mục gốc dự án và chạy Maven Wrapper:

```powershell
.\mvnw.cmd spring-boot:run "-Dspring-boot.run.profiles=dev,demo"
```

Nếu đã cài Maven, có thể dùng lệnh tương đương:

```powershell
mvn spring-boot:run "-Dspring-boot.run.profiles=dev,demo"
```

Chờ log `Tomcat started on port 8090`, sau đó mở `http://localhost:8090/auth/login`. Giữ terminal mở trong khi sử dụng ứng dụng và nhấn **Ctrl+C** để dừng.

Để bật thêm Google OAuth2, bảo đảm đã cấu hình thông tin OAuth2 hợp lệ rồi chạy:

```powershell
.\mvnw.cmd spring-boot:run "-Dspring-boot.run.profiles=dev,demo,google"
```

Chỉ chạy một phiên QAUTE trên cổng 8090 tại một thời điểm.

### 3. Đóng gói ứng dụng

```powershell
.\mvnw.cmd clean package
```

Tệp WAR sau khi đóng gói nằm trong thư mục `target/`.

---

## Tài khoản demo

| Vai trò         | Email hoặc MSSV                                    | Mật khẩu        |
| ---------------- | --------------------------------------------------- | ----------------- |
| Quản trị viên | `admin@qaute.edu.vn`                              | `Admin@12345`   |
| Tư vấn viên   | `manager.daotao@qaute.edu.vn`                     | `Manager@12345` |
| Tư vấn viên   | `manager.ctsv@qaute.edu.vn`                       | `Manager@12345` |
| Tư vấn viên   | `manager.taichinh@qaute.edu.vn`                   | `Manager@12345` |
| Tư vấn viên   | `manager.ktx@qaute.edu.vn`                        | `Manager@12345` |
| Tư vấn viên   | `manager.cntt@qaute.edu.vn`                       | `Manager@12345` |
| Tư vấn viên   | `manager.thuvien@qaute.edu.vn`                    | `Manager@12345` |
| Tư vấn viên   | `manager.qhdn@qaute.edu.vn`                       | `Manager@12345` |
| Tư vấn viên   | `manager.khcn@qaute.edu.vn`                       | `Manager@12345` |
| Tư vấn viên   | `manager.yte@qaute.edu.vn`                        | `Manager@12345` |
| Tư vấn viên   | `manager.csvc@qaute.edu.vn`                       | `Manager@12345` |
| Tư vấn viên   | `manager.qlcl@qaute.edu.vn`                       | `Manager@12345` |
| Tư vấn viên   | `manager.saudh@qaute.edu.vn`                      | `Manager@12345` |
| Sinh viên       | `111111@qaute.edu.vn` ... `111130@qaute.edu.vn` | `Student@12345` |

---

## Đường dẫn để test

Sau khi chạy ứng dụng thành công, hãy truy cập các đường dẫn sau để kiểm tra chức năng:

### Trang công khai (không cần đăng nhập)

- Trang chủ: `http://localhost:8090/`
- FAQ công khai: `http://localhost:8090/faq`
- Thông báo công khai: `http://localhost:8090/announcements`
- Đăng nhập: `http://localhost:8090/auth/login`

---

## Xử lý lỗi thường gặp

- **Không kết nối được MySQL:** kiểm tra MySQL đang chạy, tên cơ sở dữ liệu, cổng, tài khoản và mật khẩu trong cấu hình.
- **Cổng 8090 đã được sử dụng:** dừng tiến trình đang dùng cổng hoặc đổi `server.port`.
- **Lỗi migration Flyway:** kiểm tra quyền truy cập cơ sở dữ liệu và thứ tự các tệp trong `db/migration`.
- **Không đăng nhập được Google:** kiểm tra profile `google`, Client ID/Client Secret và URI chuyển hướng đã đăng ký.
- **Không gửi được email hoặc tải tệp:** kiểm tra cấu hình SMTP hoặc Cloudinary; các chức năng này cần thông tin dịch vụ hợp lệ.

---
