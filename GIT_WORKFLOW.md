# Bài thực hành Git workflow

## Branch
Branch là nhánh làm việc riêng. Trong bài này, nhánh `dev07-git-workflow` được tạo từ `main` để chuẩn bị thay đổi mà không sửa trực tiếp nhánh chính.

## Commit và push
Commit ghi nhận một nhóm thay đổi trong lịch sử Git. Push đưa commit ở máy lên nhánh tương ứng trên GitHub để có thể chia sẻ và xem xét.

## Pull Request và code review
Pull Request (PR) là đề xuất gộp thay đổi từ nhánh làm việc vào nhánh đích. Người review đọc nội dung thay đổi, đặt câu hỏi, góp ý và đối chiếu kết quả kiểm tra trước khi quyết định chấp nhận hoặc yêu cầu sửa.

## CI trong bài này
Workflow GitHub Actions chạy khi có push, pull request hoặc yêu cầu chạy thủ công. Nó kiểm tra README.md và tài liệu này tồn tại, có nội dung. Kết quả thành công chỉ cho thấy các bước kiểm tra đã cấu hình đạt, chưa chứng minh ứng dụng được triển khai hoặc toàn bộ nội dung chính xác.