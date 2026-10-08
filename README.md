# DỊCH VỤ CÀY THUÊ SLAYER II (BY NGUYỄN HOÀNG TẤN)

Giao diện landing page bảng giá dịch vụ game **Project Slayer 2** chuẩn Gaming Dark Mode, tích hợp tính tiền tự động, thanh toán quét mã QR (Techcombank & MoMo) và hệ thống bảo vệ chống soi mã nguồn.

---

## 📁 Cấu Trúc Thư Mục

```text
slayer2-service/
├── index.html           # File giao diện chính (gồm toàn bộ HTML, CSS, JS, Modal thanh toán & Bảo mật)
├── vercel.json          # Cấu hình bảo mật HTTP Headers khi deploy lên Vercel
├── assets/
│   ├── my_tech.jpg      # Mã QR Techcombank (Chủ TK: NGUYỄN HOÀNG TẤN)
│   └── my_momo.jpg      # Mã QR Ví MoMo (Chủ TK: NGUYỄN HOÀNG TẤN)
└── README.md
```

---

## 🖼️ Tối Ưu Hiển Thị Mã QR & Tải Ảnh

- Ảnh mã QR hiển thị đúng tỉ lệ dọc nguyên bản, nằm gọn gàng trên nền thẻ bo tròn viền phát sáng cyan cao cấp.
- Nút **"Tải mã QR về máy (để quét)"**: Khách hàng bấm vào nút để tải file ảnh trực tiếp về thư viện ảnh trên điện thoại/máy tính để mở ứng dụng ngân hàng quét mã ngay.
- Cho phép thao tác **giữ tay / nhấp chuột phải** trực tiếp lên ảnh QR để lưu ảnh (không bị hạn chế bởi lớp bảo mật chống sao chép).

---

## 🔒 Về Tính Năng Bảo Mật Chống Soi Source Code

Trang đã được tích hợp sẵn 4 lớp bảo vệ:
1. **Khoá chuột phải**: Người dùng bấm chuột phải vào trang web sẽ bị chặn và hiện cảnh báo (ngoại trừ ảnh QR được phép lưu).
2. **Chặn phím tắt mở DevTools**: Chặn `F12`, `Ctrl + Shift + I`, `Ctrl + Shift + J`, `Ctrl + Shift + C`, `Ctrl + U` (xem mã nguồn), `Ctrl + S` (lưu trang).
3. **Debugger Trap & Console Clear**: Tự động bẫy luồng thực thi nếu có người cố tình cắm công cụ Debugger / F12 vào website.
4. **Bảo mật HTTP Headers qua `vercel.json`**:
   - `X-Frame-Options: DENY`: Chống nhúng trang vào iframe của web khác (chống Clickjacking).
   - `X-Content-Type-Options: nosniff`: Chống tấn công MIME type sniffing.
   - `X-XSS-Protection: 1; mode=block`.

---

## 🚀 Hướng Dẫn Deploy Lên Vercel Siêu Tốc (2 Cách)

### Cách 1: Kéo thả trực tiếp trên web Vercel (Dễ nhất, 1 phút)
1. Đăng nhập [Vercel.com](https://vercel.com).
2. Kéo thả cả thư mục `slayer2-service` vào mục **Add New... -> Project**.
3. Bấm **Deploy**. Vercel sẽ tự cấp cho bạn tên miền miễn phí cực đẹp (dạng: `slayer2-service.vercel.app`).

### Cách 2: Deploy qua Vercel CLI từ Terminal
1. Cài Vercel CLI (nếu chưa có):
   ```bash
   npm i -g vercel
   ```
2. Mở terminal tại thư mục này và gõ:
   ```bash
   vercel
   ```
3. Nhấn `Enter` theo các câu hỏi mặc định là xong!
