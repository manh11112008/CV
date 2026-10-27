# BÁO CÁO KIỂM THỬ

## 1. Thông tin chung

- **Dự án:** Portfolio / CV cá nhân Hồ Đình Mạnh
- **Phiên bản:** v1.0
- **Ngày kiểm thử:** 27/10/2026
- **Môi trường:** Windows; trang được mở trực tiếp bằng trình duyệt tích hợp qua `file://`.
- **Phạm vi:** Kiểm tra giao diện và nội dung trang tĩnh, điều hướng trong trang, tài nguyên ảnh, cấu trúc HTML/CSS và khả năng triển khai theo tài liệu hiện có.

## 2. Tóm tắt kết quả

| Tiêu chí | Kết quả | Tóm tắt |
|---|---|---|
| Tính đúng đắn | Đạt có điều kiện | Trang và các phần chính hiển thị; phát hiện địa chỉ `mailto` không khớp email được hiển thị và nhiều liên kết còn là placeholder. |
| UI/UX | Cần cải thiện | Có bố cục responsive, nhưng độ tương phản chữ/nền thấp; ở viewport 214 px phát hiện tràn ngang nhẹ. |
| Khả năng vận hành - xử lý lỗi | Đạt có điều kiện | Trang và ảnh tải được khi mở trực tiếp; chưa có kiểm thử server, Docker hay kịch bản lỗi vận hành. |
| Bảo mật | Đạt trong phạm vi kiểm tra | Trang tĩnh, không có script hoặc đầu vào người dùng; chưa thực hiện kiểm thử xâm nhập hoặc kiểm tra cấu hình hosting. |
| Chất lượng mã nguồn | Đạt có điều kiện | Có cấu trúc HTML ngữ nghĩa, metadata và CSS riêng; còn nội dung/ghi chú chưa nhất quán và liên kết mẫu. |
| Khả năng triển khai | Chưa xác minh đầy đủ | Có hướng dẫn chạy bằng Python và Docker trong README; chưa chạy được server/Docker trong môi trường kiểm thử này. |

## 3. Chi tiết kiểm thử

### 3.1 Tính đúng đắn — Đạt có điều kiện

**Đã kiểm tra**

- Trang tải và hiển thị đúng tiêu đề **“Hồ Đình Mạnh · Frontend Developer”**.
- Các mục Giới thiệu, Kỹ năng, Dự án và Liên hệ đều có mặt; cả bốn liên kết điều hướng trỏ đến phần tử đích tồn tại.
- Ảnh đại diện và bốn ảnh minh họa dự án đều tải thành công.
- Phần dự án hiển thị bốn thẻ.

**Phát hiện**

- Email hiển thị là `manhh2761@gmail.com`, nhưng liên kết mở email lại dùng `mailto:an.manhh2761@gmail.com`.
- Liên kết “Xem chi tiết” của các dự án, GitHub và LinkedIn đang dùng `href="#"`, chưa dẫn tới đích thực tế.

**Minh chứng:** [Ảnh giao diện desktop](./screenshots/01-desktop-home.png).

### 3.2 UI/UX — Cần cải thiện

**Đã kiểm tra**

- CSS có bố cục mobile-first và breakpoint tại 768 px, 1280 px.
- Trang hiển thị được trên desktop và viewport hẹp; menu có thể xuống dòng.

**Phát hiện**

- Chữ phụ dùng màu `#64748b` trên nền xanh sáng `#3ee70b`, gây độ tương phản thấp và khó đọc.
- Tại viewport thực tế 214 px trong trình duyệt kiểm thử, chiều rộng nội dung là 221 px, lớn hơn viewport 7 px; có tràn ngang nhẹ.
- Màu nền xanh sáng chiếm diện tích lớn, làm giảm sự phân cấp thị giác và khả năng đọc nội dung.

**Minh chứng:** [Ảnh giao diện desktop](./screenshots/01-desktop-home.png), [ảnh giao diện viewport hẹp](./screenshots/02-mobile-home.png).

### 3.3 Khả năng vận hành - xử lý lỗi — Đạt có điều kiện

**Đã kiểm tra**

- Trang tĩnh mở được trực tiếp từ tệp HTML trên trình duyệt.
- Các ảnh được tham chiếu trên trang tải thành công.
- Không có JavaScript, API hoặc biểu mẫu cần xử lý trong phạm vi trang hiện tại.

**Giới hạn kiểm thử**

- Không kiểm tra được web server cục bộ: Python không khả dụng trong môi trường này.
- Không xác minh được hành vi khi máy chủ/đường truyền lỗi, do ứng dụng không có backend hoặc xử lý lỗi phía client.
- Chưa chạy Docker container để kiểm tra phân phối qua Nginx.

### 3.4 Bảo mật — Đạt trong phạm vi kiểm tra

**Đã kiểm tra**

- Trang không nạp thẻ `<script>`, không có biểu mẫu hoặc chức năng nhận dữ liệu người dùng.
- Nội dung hiện được phân phối dưới dạng HTML/CSS tĩnh, không có API key hay thông tin xác thực trong mã được kiểm tra.

**Phạm vi và giới hạn**

- Đây là kiểm tra cơ bản trên mã nguồn và trang đang mở, không phải kiểm thử xâm nhập hay đánh giá bảo mật toàn diện.
- Chưa đánh giá cấu hình máy chủ khi triển khai, HTTPS, security headers, quyền truy cập hoặc cấu hình Docker trên môi trường thật.

### 3.5 Chất lượng mã nguồn — Đạt có điều kiện

**Điểm tốt**

- Có `<!DOCTYPE html>`, khai báo ngôn ngữ tiếng Việt, metadata cơ bản và tiêu đề trang.
- Dùng các phần tử HTML ngữ nghĩa như `header`, `nav`, `main`, `section`, `article`, `footer`.
- CSS được tách riêng; có sử dụng Flexbox, Grid và media query.

**Cần cải thiện**

- Cập nhật các chú thích màu trong CSS cho đúng với giá trị màu đang sử dụng.
- Sửa email đích của liên kết để trùng với địa chỉ được hiển thị.
- Thay các liên kết `href="#"` bằng URL thật hoặc thể hiện rõ chúng chưa khả dụng.
- Chưa có bộ kiểm thử tự động hoặc quy trình lint/validate HTML-CSS được chạy trong lần kiểm thử này.

### 3.6 Khả năng triển khai — Chưa xác minh đầy đủ

- Tài liệu README có hướng dẫn mở trực tiếp, chạy bằng Python trên Windows/macOS/Linux và phục vụ bằng Docker/Nginx.
- Mở trực tiếp bằng trình duyệt thành công, phù hợp với bản chất website tĩnh.
- Chưa xác minh lệnh Python hoặc Docker end-to-end vì Python không có sẵn trong môi trường này và Docker chưa được kiểm tra.
- Trước khi phát hành công khai, cần cập nhật các liên kết mẫu, sửa email liên hệ và kiểm tra lại trang trên hosting mục tiêu.

## 4. Minh chứng hình ảnh

Ảnh được chụp trực tiếp từ trang trong trình duyệt kiểm thử và lưu trong `docs/screenshots/`:

1. [01-desktop-home.png](./screenshots/01-desktop-home.png) — giao diện desktop, toàn trang.
2. [02-mobile-home.png](./screenshots/02-mobile-home.png) — giao diện ở viewport hẹp, toàn trang.

## 5. Kết luận

Phiên bản hiện tại hoạt động như một portfolio tĩnh và các nội dung chính hiển thị được. Trước khi đánh giá là sẵn sàng phát hành, nên ưu tiên cải thiện độ tương phản, sửa địa chỉ email đích, thay các liên kết placeholder, xử lý tràn ngang ở màn hình hẹp và xác minh quy trình triển khai thực tế bằng Python server hoặc Docker.