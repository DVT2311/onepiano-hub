# One Piano Hub

Web app quản trị nội bộ của One Piano, thiết kế theo brand guide của onepiano.vn.

## Tính năng

- **Bộ lọc chi nhánh** trên thanh tiêu đề – xem toàn hệ thống hoặc lọc mọi màn hình (tổng quan, lớp, học viên, điểm danh, sĩ số, hồ sơ) theo từng chi nhánh. Lựa chọn được nhớ trên trình duyệt.
- **Tổng quan** – số liệu học viên, lớp, học phí, chuyên cần; biểu đồ theo tình trạng và đăng ký theo tháng; bảng so sánh hiệu quả 7 chi nhánh (khi xem toàn hệ thống) hoặc thông tin chi nhánh (khi đã lọc).
- **Chi nhánh** – thẻ từng chi nhánh: quản lý, địa chỉ, học viên, lấp đầy, chuyên cần, học phí đã thu và danh sách lớp.
- **Lớp học** – danh sách lớp, học phí, ưu đãi, giáo trình, lịch học, sĩ số.
- **Học viên** – lọc theo 6 tình trạng (Đang học, Học thử, Bảo lưu, Quay lại, Chờ xếp lớp, Kết thúc).
- **Điểm danh** – lưới theo buổi, bấm để đổi có mặt / vắng.
- **Sĩ số theo lớp** và **Hồ sơ học viên**.
- **Công việc Marketing** – bảng Kanban kéo-thả, burndown sprint, khối lượng theo thành viên.
- **Thiết lập** – danh mục dùng chung.

Responsive cho desktop, tablet (menu dạng icon) và mobile (menu ngăn kéo). Có thể thêm ra màn hình chính điện thoại/tablet như một ứng dụng (PWA manifest + apple-touch-icon).

## Cấu trúc

```
index.html              – toàn bộ app (HTML, CSS, JS thuần, không cần build)
manifest.webmanifest    – cấu hình cài đặt lên màn hình chính
favicon.ico
icons/                  – favicon SVG/PNG, apple-touch-icon, icon 192/512, maskable
```

Biểu tượng được tách trực tiếp từ logo trên onepiano.vn (`/userfiles/images/Logo/logo_one_1200_630.png`), màu cam thương hiệu `#F26B22`.

## Chạy thử

Mở `index.html` bằng trình duyệt, hoặc chạy một web server tĩnh:

```bash
python3 -m http.server 8080
```

## Deploy lên GitHub Pages

1. Vào **Settings → Pages** của repo.
2. **Source**: *Deploy from a branch* → branch `main`, thư mục `/ (root)` → **Save**.
3. Sau 1–2 phút, app chạy tại `https://dvt2311.github.io/onepiano-hub/`.

## Lưu ý dữ liệu

Dữ liệu trong app hiện là dữ liệu minh hoạ. Trạng thái bảng Marketing được lưu trong trình duyệt (localStorage) của từng người; điểm danh và thiết lập chỉ giữ trong phiên. Để cả team dùng chung cần nối một backend (ví dụ Google Sheets API, Supabase hoặc Firebase).
