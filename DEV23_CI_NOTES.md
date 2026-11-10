# DEV-23: CI cho repository tích hợp mẫu

Workflow `.github/workflows/ci-validate.yml` chạy khi mở/cập nhật pull request và có thể chạy thủ công. Job chỉ có quyền `contents: read`, kiểm tra `compose.yaml` và hai file README không rỗng, rồi lưu artifact chỉ chứa nội dung xác nhận cố định, không chứa secret. Workflow không chạy container, không build hoặc test UT.Bridora, không deploy.

## Cần team Code/T1 cung cấp để thiết lập CI cho dự án thật
- Cấu trúc thư mục frontend, backend, Compose và migration.
- Node/package manager, JDK/build tool và MySQL version được dự án dùng.
- Lệnh cài, lint, build, unit test và integration test, cùng điều kiện đạt.
- Tên và cách cấp biến môi trường test an toàn, không gửi giá trị secret trong tài liệu.
- Quy trình database test độc lập, migration, dữ liệu giả và dọn dẹp.
- Các kiểm tra bắt buộc, reviewer và quyền merge đã được thống nhất.

Các bước chưa có test hoặc chưa chạy phải ghi rõ chưa cấu hình/chưa chạy, không được tính là đạt.
