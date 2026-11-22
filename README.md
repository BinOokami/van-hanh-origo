# Origo – trang vận hành

Trang dành cho nhân viên Origo, gồm một file `index.html` tĩnh. Nhân viên đăng nhập bằng mã nhân viên và mã PIN (tab "Nhân viên" trong Google Sheet). Mọi dữ liệu đọc và ghi qua Apps Script.

- Có hai màn: **Vận hành** (xếp chuyến, kéo thả, sửa vé, lấy vé QR) và **Sân bay** (xác nhận đã đón, thanh toán, hủy chuyến của khách). Chuyển màn bằng nút ở góc phải. Ai đăng nhập cũng dùng được cả hai màn.
- Xem thử không cần máy chủ: thêm `?demo=1` vào địa chỉ. Tài khoản demo là `demo-vh` (Vận hành), `demo-sb` (Sân bay) hoặc `demo-ad` (Admin, có thêm trang Quản trị xem doanh thu), PIN `123456`. Dữ liệu giả chỉ lưu trong trình duyệt.
- Mở thẳng một vé: thêm `?t=<mã vé>` vào địa chỉ. Mã QR trên vé chỉ chứa mã vé (không có địa chỉ trang): khách quét bằng camera thường chỉ thấy mã, nhân viên quét bằng nút “Quét QR” trong trang. Trang vẫn đọc được QR cũ có địa chỉ.
- Địa chỉ Apps Script nằm ở hằng `API_URL`, đầu đoạn script trong `index.html`.

## Chạy trên máy

```
python -m http.server 4330
```

Mở `http://127.0.0.1:4330/?demo=1`.

## Đưa lên mạng

GitHub Pages: Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`.
Camera quét QR chỉ chạy được trên HTTPS.

## Thư viện đi kèm

- `qrcode.js`: qrcode-generator 1.4.4 của Kazuhiko Arase, giấy phép MIT.
- `jsQR.js`: jsQR 1.4.0, giấy phép Apache-2.0 (xem `jsQR.LICENSE.txt`).
