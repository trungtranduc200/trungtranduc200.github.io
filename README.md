# 👾 Pixel Pocket: Arcade Mini - Website Nhà Phát Triển & AdMob Verification

Website chính thức giới thiệu game di động **Pixel Pocket: Arcade Mini** (`com.pixelpocket.arcademini`), được thiết kế theo phong cách **Retro Neon Arcade / Cyberpunk** hiện đại, sẵn sàng triển khai lên **GitHub Pages** để phục vụ:
1. Xác minh tệp `app-ads.txt` cho **Google AdMob**.
2. Cung cấp trang **Chính sách quyền riêng tư (Privacy Policy)** bắt buộc cho **Google Play Console** & **Apple App Store**.
3. Cung cấp trang **Điều khoản dịch vụ (Terms of Service)** và trang **Liên hệ hỗ trợ (Support)**.

---

## 📂 Danh Sách Tệp

| Tệp tin | Vai trò |
| :--- | :--- |
| `index.html` | Trang chủ landing page giới thiệu 4 thể loại & 24 mini-games, thông số kỹ thuật 60 FPS, nút tải và xác minh AdMob. |
| `privacy-policy.html` | Chính sách quyền riêng tư chuẩn Google Play & AdMob (Offline play, SharedPreferences, AdMob SDK, GAID, COPPA). |
| `terms.html` | Điều khoản dịch vụ (quyền sở hữu trí tuệ, cơ chế xu ảo trong game, chống gian lận click ad). |
| `app-ads.txt` | Tệp xác thực nhà xuất bản ủy quyền của Google AdMob. |
| `.nojekyll` | Bắt buộc cho GitHub Pages để đảm bảo không bị Jekyll chặn tệp tĩnh. |
| `css/style.css` | Giao diện Neon Cyberpunk độc quyền, responsive 100% trên điện thoại và máy tính. |

---

## ⚠️ Lưu Ý CỰC KỲ QUAN TRỌNG Khi Triển Khai Trên GitHub Pages Cho AdMob

> Bot của Google AdMob sẽ quét tệp `app-ads.txt` tại **TÊN MIỀN GỐC (Root Domain)** mà bạn khai báo trong Google Play Store.

### Có 2 cách đặt tên Repository trên GitHub:

#### Cách 1: Tạo Repository đặc biệt dạng `<username>.github.io` (KHUYÊN DÙNG NHẤT - ĐẢM BẢO DUYỆT 100%)
- Trên GitHub, tạo 1 repository mới đặt tên đúng theo cú pháp:  
  **`<tên-tài-khoản-github-của-bạn>.github.io`**  
  *(Ví dụ nếu username GitHub của bạn là `trungdev`, thì đặt tên repo là `trungdev.github.io`)*.
- Khi đó, website của bạn sẽ chạy thẳng ở tên miền gốc:  
  `https://trungdev.github.io/`  
  Và tệp xác minh sẽ nằm ngay tại:  
  `https://trungdev.github.io/app-ads.txt`
- 👉 Đây là cách Google AdMob crawler tìm thấy tệp `app-ads.txt` ngay lập tức mà không bao giờ gặp lỗi đường dẫn!

#### Cách 2: Dùng tên miền riêng (Custom Domain)
- Bạn mua 1 tên miền riêng (ví dụ `pixelpocket.com` hoặc `.xyz` chỉ ~1$/năm) và gán vào Settings > Pages của GitHub.
- Bot AdMob sẽ quét thẳng tại `https://pixelpocket.com/app-ads.txt`.

---

## 🚀 Hướng Dẫn Từng Bước Đẩy Lên GitHub & Bật Kiếm Tiền

### Bước 1: Cập nhật Publisher ID AdMob của bạn
1. Đăng nhập [Google AdMob](https://admob.google.com).
2. Vào **Cài đặt (Settings)** > **Thông tin tài khoản (Account Information)**.
3. Tìm **Mã nhà xuất bản (Publisher ID)** có dạng `pub-XXXXXXXXXXXXXXXX` (16 chữ số).
4. Mở file `app-ads.txt` và sửa lại:
   ```text
   google.com, pub-XXXXXXXXXXXXXXXX, DIRECT, f08c47fec0942fa0
   ```
*(Lưu ý: Giữ nguyên `DIRECT, f08c47fec0942fa0`)*.

---

### Bước 2: Cập nhật Email hỗ trợ
Mở các file `index.html`, `privacy-policy.html`, `terms.html` và thay `support@yourdomain.com` bằng email thật của bạn để nhận phản hồi từ người chơi hoặc Google Play.

---

### Bước 3: Đẩy mã nguồn lên GitHub (Bằng Git CLI)
Mở Terminal hoặc PowerShell tại thư mục này (`d:\code\different_laguages\web_demo_admob`) và chạy:

```bash
# 1. Khởi tạo Git
git init

# 2. Thêm tất cả các file
git add .

# 3. Commit
git commit -m "feat: launch Pixel Pocket Arcade developer portal & app-ads.txt"

# 4. Đổi tên nhánh chính thành main
git branch -M main

# 5. Liên kết tới repository GitHub bạn vừa tạo (thay đường link thật của bạn vào)
git remote add origin https://github.com/<tên-username-của-bạn>/<tên-username-của-bạn>.github.io.git

# 6. Đẩy code lên GitHub
git push -u origin main
```

*(Nếu bạn không dùng Git dòng lệnh, bạn chỉ cần mở GitHub trên trình duyệt, tạo repo và kéo thả toàn bộ các file trong thư mục này lên web GitHub là xong)*.

---

### Bước 4: Kích hoạt GitHub Pages
1. Vào repository trên GitHub > Chọn tab **Settings**.
2. Ở thanh bên trái, chọn mục **Pages**.
3. Tại phần **Build and deployment**:
   - Source: Chọn `Deploy from a branch`.
   - Branch: Chọn `main` và thư mục `/ (root)`.
   - Bấm **Save**.
4. Chờ khoảng 1-2 phút, GitHub sẽ hiển thị đường link trang web của bạn:  
   `https://<username>.github.io/`

---

### Bước 5: Điền URL vào Google Play Console
1. Truy cập [Google Play Console](https://play.google.com/console) > Chọn app **Pixel Pocket: Arcade Mini**.
2. **Khai báo Website nhà phát triển:**
   - Vào **Sự hiện diện trong Cửa hàng (Store Presence)** > **Cài đặt trang thông tin trên Cửa hàng (Store Settings)**.
   - Nhập vào ô **Trang web (Website)**:  
     `https://<username>.github.io`
3. **Khai báo Chính sách quyền riêng tư:**
   - Vào **Nội dung ứng dụng (App Content)** > **Chính sách quyền riêng tư (Privacy Policy)**.
   - Nhập đường link:  
     `https://<username>.github.io/privacy-policy.html`
4. Bấm **Lưu (Save)**.

---

### Bước 6: Kiểm tra xác minh trên AdMob
1. Đăng nhập [Google AdMob](https://admob.google.com).
2. Vào **Ứng dụng (Apps)** > **Xem tất cả ứng dụng (View all apps)** > Tab **app-ads.txt**.
3. Khi Google bot hoàn tất thu thập (khoảng 24 - 48 giờ sau khi Google Play cập nhật), bạn sẽ thấy ứng dụng chuyển sang trạng thái:
   - 🟢 **Được ủy quyền (Authorized)**.
4. Mọi quảng cáo Adaptive Banner, Interstitial, và Rewarded Video trong app Flutter của bạn sẽ hiển thị với tỷ lệ lấp đầy (Fill Rate) tối đa 100%!
