# Đề 3: Website Quảng bá Sản phẩm (WordPress)

**Sinh viên thực hiện:** Nguyễn Văn Trường  
**Mã số sinh viên:** DTC245160025  
**Môn học:** Triển khai và Quản trị Hệ thống Phần mềm  

## 1. Giới thiệu kiến trúc hệ thống
Hệ thống được triển khai bằng Docker Compose theo kiến trúc Microservices, bao gồm các thành phần:
- **Nginx Reverse Proxy:** Xử lý request và cấu hình Security Headers.
- **WordPress:** Mã nguồn mở xây dựng website.
- **MariaDB & phpMyAdmin:** Hệ quản trị cơ sở dữ liệu.
- **Prometheus & Grafana:** Thu thập metrics và hiển thị Dashboard giám sát.
- **Loki & Promtail:** Thu thập và quản lý Log tập trung.

## 2. Yêu cầu hệ thống (Prerequisites)
- Hệ điều hành: Linux (Ubuntu/CentOS).
- Đã cài đặt `docker` và `docker compose`.
- Port yêu cầu: `80` (Web), `8081` (DB Admin), `3000` (Grafana).

## 3. Hướng dẫn chạy hệ thống (How to run)

**Bước 1:** Tạo file biến môi trường `.env` ẩn trong thư mục gốc dự án (không push file này lên Git) với nội dung mẫu sau:
MYSQL_ROOT_PASSWORD=MatKhauRootBaoMat!@#
MYSQL_DATABASE=wordpress_db
MYSQL_USER=wp_user
MYSQL_PASSWORD=WpPasswordManh!@#2024

**Bước 2:** Khởi chạy toàn bộ hệ thống bằng Docker Compose:
docker compose up -d

**Bước 3:** Kiểm tra trạng thái các container (Đảm bảo 8/8 dịch vụ trạng thái Up):
docker compose ps

## 4. Truy cập các dịch vụ
Sau khi hệ thống khởi chạy thành công, truy cập qua trình duyệt thông qua địa chỉ IP của máy chủ:
- **Trang chủ WordPress:** `http://<IP_Máy_Chủ>`
- **Quản trị Database phpMyAdmin:** `http://<IP_Máy_Chủ>:8081` 
  *(User: wp_user / Pass: cấu hình trong file .env)*
- **Giám sát Grafana / LogQL:** `http://<IP_Máy_Chủ>:3000` 
  *(User: admin / Pass: admin)*# Đề 3: Website Quảng bá Sản phẩm (WordPress)
Hệ thống quản lý bằng Docker Compose.
