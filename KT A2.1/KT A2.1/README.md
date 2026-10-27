# Hồ Đình Mạnh — Portfolio CV

Website portfolio cá nhân giới thiệu Hồ Đình Mạnh, Frontend Developer. Trang trình bày thông tin giới thiệu, kỹ năng, các dự án tiêu biểu và cách liên hệ; giao diện được thiết kế responsive cho điện thoại, máy tính bảng và máy tính.

## Chức năng

- Điều hướng nhanh đến các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Hiển thị ảnh đại diện, mô tả cá nhân và lời mời liên hệ.
- Trình bày kỹ năng dưới dạng thẻ.
- Hiển thị bốn dự án mẫu: Landing Page Sản Phẩm, Ứng dụng Todo List, Weather Dashboard và Blog Cá Nhân.
- Bố cục responsive, dùng Flexbox và CSS Grid; có liên kết cuộn về đầu trang.
- Cung cấp email và các hồ sơ GitHub, LinkedIn trong phần liên hệ.

## Công nghệ

- HTML5: cấu trúc nội dung và các vùng ngữ nghĩa.
- CSS3: giao diện, biến CSS, Flexbox, CSS Grid, hiệu ứng và media query.
- Không sử dụng framework, thư viện JavaScript, backend, cơ sở dữ liệu hoặc công cụ build.

## Cấu trúc dự án

```text
.
├── index.html
├── README.md
└── assets/
    ├── css/
    │   └── styles.css
    └── img/
        ├── addmin.jpg
        └── avatar.jpg
```

## Yêu cầu môi trường

Để xem trang, bạn chỉ cần một trình duyệt hiện đại. Có thể mở `index.html` trực tiếp hoặc chạy một máy chủ web tĩnh để kiểm tra trong môi trường gần với triển khai thực tế hơn.

| Cách chạy | Yêu cầu |
|---|---|
| Mở trực tiếp | Trình duyệt web hiện đại |
| Máy chủ Python | Python 3 |
| Docker | Docker Engine hoặc Docker Desktop đang hoạt động |

Không cần cài Node.js, không cần tải các gói phụ thuộc và không cần tạo file biến môi trường.

## Cài đặt

1. Tải hoặc sao chép mã nguồn dự án về máy.
2. Mở terminal tại thư mục chứa `index.html` và `README.md`.
3. Chọn một trong các cách chạy bên dưới.

> Nếu tải về từ kho lưu trữ, hãy giải nén trước. Các lệnh dưới đây cần được chạy tại thư mục gốc của dự án (thư mục có `index.html`).

## Cấu hình và tùy chỉnh

Dự án hiện không có cấu hình chạy riêng. Để cá nhân hóa nội dung:

- Chỉnh tên, phần giới thiệu, kỹ năng, mô tả dự án và thông tin liên hệ trong `index.html`.
- Thay ảnh đại diện tại `assets/img/` và cập nhật đường dẫn `src` tương ứng trong `index.html`.
- Chỉnh màu sắc, phông chữ, khoảng cách và bố cục trong `assets/css/styles.css`; các biến màu và thông số giao diện được khai báo trong `:root`.
- Thay các liên kết mẫu `href="#"` của GitHub, LinkedIn và nút xem dự án bằng URL thật trước khi công khai website.
- Đảm bảo đường dẫn đến ảnh và stylesheet còn đúng sau khi đổi tên hoặc di chuyển tệp.

## Chạy thử

### Windows

**Mở trực tiếp:** mở `index.html` bằng trình duyệt.

**Dùng Python 3 (PowerShell):**

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có trên máy, thử:

```powershell
python -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000). Dừng máy chủ bằng `Ctrl+C`.

### macOS

Mở Terminal tại thư mục dự án. Có thể mở `index.html` bằng trình duyệt hoặc chạy máy chủ Python:

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000). Dừng máy chủ bằng `Ctrl+C`.

### Linux

Mở terminal tại thư mục dự án. Có thể mở `index.html` bằng trình duyệt hoặc chạy:

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000). Dừng máy chủ bằng `Ctrl+C`.

### Docker

Cài đặt và khởi động Docker trước. Không cần Dockerfile; lệnh bên dưới phục vụ các tệp của dự án qua Nginx.

**Windows (PowerShell):**

```powershell
docker run --rm -d --name portfolio-cv -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

**macOS / Linux:**

```bash
docker run --rm -d --name portfolio-cv -p 8080:80 -v "$(pwd):/usr/share/nginx/html:ro" nginx:alpine
```

Sau khi container khởi động, mở [http://localhost:8080](http://localhost:8080). Lần đầu chạy, Docker có thể cần tải image `nginx:alpine`.

Dừng container:

```bash
docker stop portfolio-cv
```

`--rm` sẽ tự xóa container sau khi dừng. Thư mục dự án được gắn ở chế độ chỉ đọc bên trong container.

## Thông tin liên hệ

Thông tin hiện được hiển thị trong trang:

- **Tên:** Hồ Đình Mạnh
- **Email:** [manhh2761@gmail.com](mailto:manhh2761@gmail.com)
- **GitHub:** `github.com/hodinhmanh`
- **LinkedIn:** `linkedin.com/in/hodinhmanh`

Các địa chỉ GitHub và LinkedIn trong HTML hiện là nội dung hiển thị với liên kết `#`; hãy xác nhận và cập nhật URL hồ sơ thật trước khi triển khai.
