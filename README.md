# PAW HAVEN — Pet Depression Care Experience Platform

> **They Feel More Than They Can Tell.**  
> *Because Their Mental Health Matters Too.*

Website trình diễn startup học thuật phục vụ buổi pitching **Shark Tank Debate — Học phần Quản trị Marketing**. Dự án kết hợp 4 module thống nhất trên cùng một nền tảng tĩnh:

1. **PAW HAVEN** — Trang thương hiệu, sứ mệnh, 3 nhóm phương pháp hỗ trợ, quy trình 6 bước, bảng gói dịch vụ, chiến lược STP & 4P và Booking Demo.
2. **PAW UNIVERSE** — Không gian trung tâm chăm sóc 3D mặt cắt isometric gồm 6 phân khu tương tác kèm bản đồ 2D fallback mượt trên di động.
3. **PAW QUEST** — Story-based mini-game 4 cấp độ (2–3 phút) giáo dục người nuôi về quan sát hành vi và lựa chọn chăm sóc an toàn.
4. **INVESTOR HUB** — Khu vực Nhà đầu tư gồm tóm tắt mô hình kinh doanh, khung TAM/SAM/SOM chờ xác minh, Financial Simulator tương tác thời gian thực và khung Đề xuất Đầu tư & Rủi ro.

---

## 1. Hướng dẫn chạy trên máy cá nhân (Local Development)

1. Mở thư mục dự án trong **Google Antigravity** (hoặc VS Code / terminal).
2. Mở Terminal tại thư mục gốc dự án và cài đặt thư viện:
   ```bash
   npm install
   ```
   *(Hoặc `npm ci` nếu đã có `package-lock.json`; trên Windows PowerShell chặn script `.ps1`, có thể gõ `npm.cmd install`).*
3. Khởi chạy máy chủ phát triển:
   ```bash
   npm run dev
   ```
4. Kiểm tra bản build production và xem trước:
   ```bash
   npm run build
   npm run preview
   ```

---

## 2. Hướng dẫn Deploy miễn phí lên GitHub Pages (Cho người mới)

Dự án đã được cấu hình sẵn `HashRouter`, tự động nhận diện `base` path theo tên repository trong `vite.config.ts` và workflow tự động tại `.github/workflows/deploy.yml`. Không cần mua hosting hay cài đặt máy chủ.

Các bước thực hiện:

1. Mở thư mục dự án trong Antigravity.
2. Trong Terminal, đảm bảo dự án đã cài dependency (`npm install`) và chạy `npm run build` thành công.
3. Đăng nhập GitHub và **tạo một repository mới** (nên để chế độ **Public** để dùng GitHub Pages miễn phí).
4. Đẩy toàn bộ mã nguồn lên nhánh `main`:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: PAW HAVEN platform"
   git branch -M main
   git remote add origin https://github.com/<ten-tai-khoan>/<ten-repo>.git
   git push -u origin main
   ```
5. Trên giao diện GitHub của repository, mở **Settings** → **Pages** (cột menu bên trái).
6. Tại mục **Build and deployment** → **Source**, chọn **GitHub Actions**.
7. Mở tab **Actions** trên thanh menu trên cùng để kiểm tra workflow `Deploy PAW HAVEN to GitHub Pages` chạy sang tích xanh.
8. Quay lại **Settings** → **Pages** → bấm **Visit site** để mở đường link chính thức của website.

---

## 3. Lưu ý Quan trọng về Kiến trúc Tĩnh & Nội dung Y khoa

- **Static Hosting & Booking Demo:** GitHub Pages phục vụ website tĩnh miễn phí. Biểu mẫu đặt lịch tại `/#/booking` chỉ tạo mã hẹn minh họa và lưu vào `LocalStorage` ngay trên trình duyệt hiện tại của người dùng — **không gửi dữ liệu về máy chủ thực tế**, không thu thập SĐT/email/địa chỉ nhà riêng và không có thanh toán thật.
- **Giới hạn Y khoa & Học thuật:** PAW HAVEN là concept startup học thuật. Các phương pháp (Pet Therapeutic Massage, Botanical Support, Sound Therapy / Auditory Enrichment) được trình bày như các hướng hỗ trợ cần đánh giá theo từng cá thể và phối hợp bác sĩ thú y, không thay thế chẩn đoán hay điều trị thú y.
- **Minh bạch Số liệu Kinh doanh:** Các thông số mặc định trong `Financial Simulator` được trích từ `DATA/financial_model_demo.json` và gắn nhãn `DEMO ASSUMPTIONS — NOT ACTUAL RESULTS`. Bảng giá chính thức, số liệu TAM/SAM/SOM và điều khoản gọi vốn để ở trạng thái chờ nhóm bổ sung căn cứ thực tế.
- **Tài liệu Handoff Gốc:** Xem thêm `START_HERE.md`, `MASTER_PROMPT_ANTIGRAVITY.md`, `SPECIFICATION/` và `public/ASSET_CREDITS.md`.
