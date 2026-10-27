# Hồ Đình Mạnh — Portfolio / CV

## Tên dự án

**Portfolio cá nhân của Hồ Đình Mạnh** — trang web giới thiệu thông tin cá nhân, kỹ năng, dự án và cách liên hệ.

## Mô tả

Đây là website tĩnh được xây dựng để giới thiệu hồ sơ Frontend Developer. Giao diện sử dụng HTML ngữ nghĩa và CSS responsive, có thể chạy trực tiếp trên trình duyệt hoặc phục vụ bằng web server tĩnh. Dự án không cần cơ sở dữ liệu, backend hay bước biên dịch.

## Chức năng

- Điều hướng nhanh đến các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Hiển thị phần giới thiệu và ảnh đại diện.
- Trình bày danh sách kỹ năng và các dự án mẫu.
- Cung cấp thông tin liên hệ qua email, cùng các liên kết GitHub và LinkedIn đang là nội dung mẫu.
- Bố cục tự điều chỉnh theo kích thước màn hình điện thoại, máy tính bảng và máy tính.
- Có liên kết cuộn về đầu trang.

## Công nghệ

- **HTML5**: cấu trúc và nội dung trang.
- **CSS3**: giao diện, bố cục Flexbox/Grid và responsive.
- **Docker + Nginx** (tùy chọn): phục vụ trang tĩnh trong container.

## Yêu cầu môi trường

Để mở trang trực tiếp, chỉ cần một trình duyệt hiện đại. Để chạy qua web server cục bộ, cần **Python 3**. Để chạy bằng Docker, cần **Docker Engine**; trên Windows và macOS, có thể cài Docker Desktop.

Không cần cài Node.js, không cần cài thư viện phụ thuộc và không cần API key.

## Cài đặt

Tải hoặc sao chép mã nguồn về máy, sau đó mở terminal tại thư mục dự án. Cấu trúc chính:

```text
.
├── index.html
├── CHANGELOG.md
└── assets/
    ├── css/
    │   └── styles.css
    └── img/
        ├── addmin.jpg
        └── avatar.jpg
```

Nếu dùng Git:

```bash
git clone <địa-chỉ-repository>
cd <thư-mục-dự-án>
```

Thay `<địa-chỉ-repository>` bằng URL repository thực tế. Nếu đã tải mã nguồn dạng ZIP, giải nén rồi mở terminal tại thư mục vừa giải nén.

## Cấu hình

Dự án hiện không có tệp cấu hình riêng hoặc biến môi trường. Có thể tùy chỉnh nội dung trực tiếp:

- Sửa thông tin, phần giới thiệu, kỹ năng, dự án và liên hệ trong `index.html`.
- Thay ảnh trong `assets/img/` và cập nhật đường dẫn `src` tương ứng trong `index.html`.
- Chỉnh màu sắc, kiểu chữ, khoảng cách và breakpoint responsive trong `assets/css/styles.css`.
- Thay các liên kết mẫu `href="#"` của dự án, GitHub và LinkedIn bằng URL thật trước khi phát hành.

## Chạy thử

### Mở trực tiếp

Mở `index.html` bằng trình duyệt. Cách này phù hợp để xem nhanh giao diện; chạy qua web server cục bộ được khuyến nghị để mô phỏng cách website tĩnh được phân phối.

### Windows

Mở PowerShell tại thư mục dự án và chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có nhưng đã cài Python 3, dùng:

```powershell
python -m http.server 8000
```

### macOS

Mở Terminal tại thư mục dự án và chạy:

```bash
python3 -m http.server 8000
```

### Linux

Mở terminal tại thư mục dự án và chạy:

```bash
python3 -m http.server 8000
```

Trên Windows, macOS hoặc Linux, sau khi server khởi động, mở <http://localhost:8000> trong trình duyệt. Nhấn `Ctrl+C` trong terminal để dừng server.

## Chạy bằng Docker

Cần cài và khởi động Docker trước. Các lệnh dưới đây gắn thư mục dự án hiện tại vào Nginx ở chế độ chỉ đọc, rồi phục vụ website tại cổng `8080`. Lần đầu chạy, Docker cần tải image `nginx:alpine`.

### Windows (PowerShell)

Chạy tại thư mục dự án:

```powershell
docker run --rm -d --name cv-portfolio -p 8080:80 --mount "type=bind,source=${PWD},target=/usr/share/nginx/html,readonly" nginx:alpine
```

### macOS và Linux

Chạy tại thư mục dự án:

```bash
docker run --rm -d --name cv-portfolio -p 8080:80 --mount "type=bind,source=$(pwd),target=/usr/share/nginx/html,readonly" nginx:alpine
```

Mở <http://localhost:8080> để kiểm tra. Dừng container bằng:

```bash
docker stop cv-portfolio
```

Nếu cổng `8080` đang được sử dụng, đổi phần `-p 8080:80` thành một cổng khác, ví dụ `-p 8081:80`, rồi truy cập cổng tương ứng trên trình duyệt.

## Thông tin liên hệ

- **Tên:** Hồ Đình Mạnh
- **Email:** `manhh2761@gmail.com`
- **GitHub và LinkedIn:** liên kết trên trang hiện là nội dung mẫu; vui lòng cập nhật trong `index.html`.
