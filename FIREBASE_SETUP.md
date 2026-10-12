# Bật chế độ chơi online bằng Firebase

GitHub Pages chỉ phục vụ file tĩnh. Chế độ hai thiết bị sử dụng Firebase Authentication và Realtime Database để đồng bộ phòng chơi.

## 1. Tạo Firebase project và Web App

1. Mở <https://console.firebase.google.com> và chọn **Create a project**.
2. Trong trang tổng quan của project, bấm biểu tượng **Web `</>`**.
3. Đặt nickname cho app rồi bấm **Register app**.
4. Firebase hiển thị một object `firebaseConfig`. Sao chép các giá trị đó vào file `firebase-config.js` trong folder này.

Ví dụ:

```js
window.FIREBASE_CONFIG = {
  apiKey: "...",
  authDomain: "...",
  databaseURL: "https://....firebasedatabase.app",
  projectId: "...",
  storageBucket: "...",
  messagingSenderId: "...",
  appId: "..."
};
```

## 2. Bật đăng nhập ẩn danh

1. Trong Firebase Console, mở **Build → Authentication**.
2. Bấm **Get started** nếu được hỏi.
3. Mở **Sign-in method → Anonymous**.
4. Chọn **Enable** rồi lưu.

Trong **Authentication → Settings → Authorized domains**, thêm domain GitHub Pages của bạn, ví dụ `ten-github.github.io`.

## 3. Tạo Realtime Database

1. Mở **Build → Realtime Database → Create Database**.
2. Chọn vị trí gần người chơi.
3. Chọn **Locked mode** rồi tạo database.
4. Nếu `firebaseConfig` chưa có `databaseURL`, sao chép URL hiển thị ở đầu trang Data và thêm nó vào file cấu hình.

## 4. Cài Database Rules

1. Trong Realtime Database, mở tab **Rules**.
2. Sao chép toàn bộ nội dung file `firebase-rules.json` vào trình chỉnh sửa Rules.
3. Bấm **Publish**.

Rules yêu cầu người chơi đăng nhập ẩn danh, giới hạn phòng ở hai người và chỉ thành viên phòng mới được cập nhật ván đấu.

## 5. Cập nhật GitHub Pages

Upload lại các file sau vào thư mục gốc repository và commit:

- `index.html`
- `firebase-config.js`
- `firebase-rules.json`
- `FIREBASE_SETUP.md`

Đợi GitHub Pages cập nhật, sau đó chọn **Online → Tạo phòng**. Gửi link mời cho người còn lại; link sẽ tự điền mã phòng.

