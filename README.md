# Bàn phím Android tiếng Dao Đầu Bằng (Kìm Mùn) — bản thử nghiệm 0.1.0

## Tính năng hiện có
- Android Input Method Service (IME) cài như bàn phím hệ thống.
- Màn hình hướng dẫn bật và chọn bàn phím.
- Gõ phụ âm ghép bằng cách nhập liên tiếp: bl, by, kl, ky, gy, gl, pl, py, đy, th, tk.
- Telex nguyên âm: `aw → ă`, `aa → â`, `ee → ê`, `oo → ô`, `ow → ơ`, `uw → ư`.
- Dấu thanh: `f` huyền, `s` sắc, `r` hỏi, `x` ngã, `j` nặng; `q` thêm vòng tròn trên; `v` thêm huyền + chấm trên; `z` xóa dấu thanh.
- Min SDK 16, target SDK 28 để ưu tiên tương thích thiết bị cũ; cần kiểm thử trên các phiên bản Android thực tế.

## Xây dựng APK
Yêu cầu: Android Studio hoặc Android SDK + Gradle, JDK 17 cho Android Gradle Plugin 8.7.3.
1. Giải nén thư mục dự án.
2. Mở thư mục `KimMunAndroid` bằng Android Studio.
3. Cho phép Gradle tải Android Gradle Plugin và SDK platform 35.
4. Chọn Build > Build Bundle(s) / APK(s) > Build APK(s).
5. APK thường nằm tại `app/build/outputs/apk/debug/app-debug.apk`.

## Cài và bật bàn phím
1. Cài APK.
2. Mở ứng dụng “Bàn phím Kìm Mùn”.
3. Chọn “Bật bàn phím Kìm Mùn” trong cài đặt hệ thống.
4. Chọn “Chọn bàn phím Kìm Mùn”.
5. Mở ứng dụng nhắn tin và thử gõ.

## Lưu ý quan trọng
- Đây là bản khung chạy thử đầu tiên, chưa phải bản phát hành chính thức.
- Mã dùng combining Unicode cho hai thanh riêng `q` và `v`; cần xác nhận hình dạng hiển thị trên nhiều font/điện thoại.
- Bản thử nghiệm chưa có gợi ý từ điển, trang ký hiệu đầy đủ, chọn ngôn ngữ, hoặc kiểm thử trên thiết bị thật.
- `?123` hiện là nút giữ chỗ; cần bổ sung trang ký hiệu ở vòng phát triển tiếp theo.
- Trước khi công bố chuẩn, nhóm cần xác nhận vị trí đặt thanh điệu trong vần, cách xử lý từ nhiều nguyên âm, và xung đột giữa ký tự chữ thường với phím Telex.


## Cách tạo APK khi không có Android Studio trên máy
Có kèm workflow `.github/workflows/build-apk.yml` để xây dựng APK bằng GitHub Actions:
1. Tạo một repository GitHub mới và tải toàn bộ nội dung thư mục dự án lên (không chỉ ZIP lồng bên trong).
2. Mở tab **Actions** và chạy workflow **Build Kìm Mùn APK**.
3. Khi workflow hoàn tất thành công, tải artifact `KimMun-debug-apk`; bên trong có `app-debug.apk`.
4. Chuyển APK sang điện thoại Android, cho phép cài ứng dụng từ nguồn này nếu được hỏi, rồi cài đặt.

APK debug được tạo theo cách này chỉ dùng thử nghiệm; chưa phải bản phát hành đã kiểm thử trên thiết bị thật.
