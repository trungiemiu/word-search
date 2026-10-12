# Love Letters — Word Search

Trang game tìm chữ dành cho 1 hoặc 2 người, gồm 281 bộ từ được tách riêng theo từng set. Các set 274–281 là chủ đề cặp đôi và điểm đến Việt Nam. Game hỗ trợ chơi một mình, hai người trên cùng thiết bị và hai người online bằng mã phòng.

## Chạy thử trên máy

Do trình duyệt không cho HTML mở trực tiếp đọc file JSON, hãy chạy một web server tại thư mục này:

```powershell
python -m http.server 8000
```

Sau đó mở `http://localhost:8000`.

## Đăng lên GitHub Pages

1. Tạo một repository mới trên GitHub.
2. Upload toàn bộ nội dung của thư mục này vào nhánh `main`.
3. Vào **Settings → Pages**.
4. Chọn **Deploy from a branch**, nhánh **main**, thư mục **/(root)** rồi bấm **Save**.
5. Chờ GitHub tạo đường dẫn công khai và gửi đường dẫn đó cho người chơi cùng.

## Cấu trúc

- `index.html`: toàn bộ giao diện và logic game.
- `database.json`: 281 set, ID liên tục từ 1 đến 281.
- `firebase-config.js`: cấu hình Firebase cho chế độ online.
- `firebase-rules.json`: rules bảo vệ phòng chơi trong Realtime Database.
- `FIREBASE_SETUP.md`: hướng dẫn bật chế độ chơi trên hai thiết bị.
- `.nojekyll`: yêu cầu GitHub Pages phục vụ nguyên trạng các file tĩnh.

