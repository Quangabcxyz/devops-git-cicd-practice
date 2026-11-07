# Lab kiểm tra cấu hình Docker Compose

Bài thực hành DEV-11: GitHub Actions kiểm tra file `compose.yaml` mỗi khi push hoặc mở pull request. Cấu hình chỉ có một dịch vụ Nginx minh họa và không chứa mật khẩu.

## Kiểm tra trên máy có Docker Compose

```bash
docker compose -f compose.yaml config --quiet
```

Lệnh hợp lệ kết thúc với mã 0; cấu hình sai khiến lệnh trả mã khác 0. Lệnh kiểm tra cấu hình, không khởi động container hoặc chứng minh dịch vụ hoạt động.

## Kiểm tra trên GitHub

Mở tab Actions hoặc Checks của pull request, xem workflow `Kiem tra cau hinh Compose` và bước kiểm tra Compose. Thử lỗi phải được đánh dấu rõ, sửa lại và chạy kiểm tra xanh trước khi xem xét merge.