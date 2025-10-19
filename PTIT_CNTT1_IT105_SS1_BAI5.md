1. Planning (Lập kế hoạch)
   Đây là giai đoạn xác định "tại sao" chúng ta làm dự án này và liệu nó có khả thi hay không.
   • Xác định mục tiêu: Mục tiêu chính là xây dựng một hệ thống thay thế việc điểm danh thủ công, giúp tiết kiệm thời gian cho giảng viên và cung cấp số liệu thống kê tức thời, chính xác cho phòng đào tạo.
   • Khảo sát tính khả thi:
    o Kỹ thuật: Chúng ta có đủ công nghệ và chuyên môn để xây dựng ứng dụng di động, backend và xử lý QR code không? (Có, công nghệ này đã phổ biến).
    o Kinh tế: Chi phí phát triển (lương nhân sự, server) so với lợi ích (thời gian tiết kiệm, dữ liệu chính xác) có hợp lý không?
    o Vận hành: Giảng viên và sinh viên có sẵn sàng sử dụng không? (Hầu hết đều có smartphone). Hạ tầng mạng của trường có đủ đáp ứng không?
   • Lập kế hoạch dự án: Xác định phạm vi dự án (các chức năng chính), ước tính thời gian (timeline), phân bổ ngân sách và thành lập đội ngũ phát triển.

2. Requirement Analysis (Phân tích yêu cầu)
   Đây là giai đoạn xác định "cái gì" hệ thống cần phải làm, tập trung vào góc nhìn của người dùng.
   • Thu thập yêu cầu: Gặp gỡ và phỏng vấn 3 nhóm người dùng chính để hiểu nhu cầu của họ:
    o Giảng viên: "Tôi muốn tạo một mã QR cho buổi học của mình. Mã này nên tự động hết hạn sau 5 phút để tránh sinh viên ở ngoài quét."
    o Sinh viên: "Tôi chỉ muốn mở app, quét mã và được ghi nhận là có mặt. Tôi cũng muốn xem lại lịch sử điểm danh của mình."
    o Phòng đào tạo: "Tôi cần một trang web để xem và xuất báo cáo thống kê theo lớp, theo sinh viên, và theo môn học."
   • Phân tích và định nghĩa yêu cầu:
    o Yêu cầu chức năng (Functional): 1. (Giảng viên) Phải đăng nhập được. 2. (Giảng viên) Phải tạo được một buổi học và sinh ra mã QR duy nhất, có thời hạn. 3. (Sinh viên) Phải đăng nhập được. 4. (Sinh viên) Phải quét được mã QR để điểm danh. 5. (Phòng đào tạo) Phải xem và xuất được báo cáo thống kê.
    o Yêu cầu phi chức năng (Non-functional): 1. Bảo mật: Hệ thống phải chống gian lận (ví dụ: QR code thay đổi liên tục hoặc chỉ có giá trị trong thời gian ngắn). 2. Hiệu năng: Hệ thống phải xử lý được đồng thời (ví dụ: 100 sinh viên trong một lớp quét mã cùng lúc). 3. Dễ sử dụng: Giao diện phải trực quan, đơn giản cho cả 3 đối tượng.
   • Kết quả: Tạo ra tài liệu đặc tả yêu cầu (SRS) và vẽ biểu đồ Use Case để mô tả các tác nhân (Giảng viên, Sinh viên, P. Đào tạo) và các hành động của họ.

3. System Design (Thiết kế hệ thống)
   Đây là giai đoạn xác định "như thế nào" để xây dựng hệ thống, chuyển từ yêu cầu sang kế hoạch kỹ thuật.
   • Thiết kế kiến trúc: Quyết định kiến trúc tổng thể. Ví dụ:
    o Mobile App (Client): Xây dựng bằng React Native/Flutter (cho cả iOS/Android) để Giảng viên và Sinh viên sử dụng.
    o Web Portal (Client): Xây dựng bằng React/VueJS cho Phòng đào tạo.
    o Backend (Server): Một API (ví dụ: dùng Node.js/Java) để xử lý logic nghiệp vụ.
    o Database: (ví dụ: PostgreSQL/MySQL) để lưu trữ dữ liệu.
   • Thiết kế chi tiết:
    o Thiết kế Cơ sở dữ liệu: Vẽ biểu đồ ERD (Mô hình quan hệ thực thể). Cần các bảng chính như: Users (lưu tin Giảng viên, Sinh viên, P. Đào tạo), Classes, Sessions (buổi học), Attendance_Records (lưu lại ai đã điểm danh lúc nào).
    o Thiết kế Giao diện (UI/UX): Tạo wireframe (bản vẽ khung) và mockup (bản thiết kế hoàn chỉnh) cho các màn hình chính của ứng dụng (màn hình đăng nhập, màn hình quét QR, màn hình tạo QR, trang xem báo cáo).
    o Thiết kế luồng xử lý: Vẽ các biểu đồ Tuần tự (Sequence Diagram) để mô tả chi tiết các bước khi sinh viên điểm danh (VD: App gửi mã QR -> Server xác thực mã -> Server ghi nhận điểm danh -> Server trả kết quả về App).
