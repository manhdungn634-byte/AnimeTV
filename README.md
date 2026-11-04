# AnimeTV (giao diện TV) - build APK bằng GitHub Actions

App Android TV bọc giao diện TV của AnimeTV (WebView), điều khiển bằng remote.

## Cách lấy file APK
1. Tạo repo mới trên GitHub, upload **toàn bộ** nội dung thư mục này (nhớ cả thư mục `.github`).
2. Vào tab **Actions** > workflow **Build APK** > chờ chạy xong (khoảng 3-5 phút).
   Nếu không tự chạy: chọn **Run workflow**.
3. Mở lần chạy đó, mục **Artifacts** > tải **AnimeTV-TV-apk** (giải nén ra `AnimeTV-TV.apk`).

## Tạo bản Release có link tải trực tiếp
Tạo tag bắt đầu bằng `v`, ví dụ `v1.0`: workflow sẽ đính kèm `AnimeTV-TV.apk` vào mục **Releases**.

## Cài lên Android TV
- Bật Tùy chọn nhà phát triển và Gỡ lỗi ADB trên TV.
- `adb connect IP_CUA_TV:5555` rồi `adb install AnimeTV-TV.apk`
- Hoặc chép APK vào USB, mở bằng trình quản lý file trên TV (cho phép cài từ nguồn không xác định).

## Sửa giao diện
Sửa `app/src/main/assets/index.html`, commit lên GitHub, APK mới sẽ được build lại.
APK là bản debug (ký bằng khóa debug), cài trực tiếp được nhưng không dùng để đưa lên Google Play.
