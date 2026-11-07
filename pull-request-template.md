# Mẫu Pull Request – bài lab DevOps

> Mẫu đề xuất cho repository thực hành; quy định áp dụng cho dự án chung cần nhóm thống nhất. Chỉ đánh dấu khi đã kiểm tra thực tế.

## Mục đích và phạm vi
- Vấn đề / mục tiêu:
- Nội dung thay đổi:
- Phạm vi ảnh hưởng; phần chưa thực hiện:

## Kiểm tra và kết quả
- [ ] Ghi rõ lệnh, môi trường và kết quả kiểm tra thực tế.
- [ ] Đối chiếu các check CI bắt buộc trên commit mới nhất của PR.
- [ ] Nêu hạn chế: CI kiểm tra cấu hình không đồng nghĩa dịch vụ đã chạy hoặc ứng dụng đã được kiểm thử.
- Link run / log:

## Minh chứng
- [ ] Đính kèm ảnh, log đã loại bỏ dữ liệu nhạy cảm, hoặc liên kết bằng chứng phù hợp.
- Minh chứng:

## Khôi phục (rollback)
- Ảnh hưởng nếu thay đổi gây lỗi:
- Phương án quay lại phiên bản ổn định hoặc revert commit; người phụ trách và cách kiểm tra sau khôi phục cần được thống nhất trước khi triển khai.
- PR tài liệu/lab chưa triển khai: ghi rõ không có rollback triển khai; nếu cần hoàn tác trên Git, đề xuất revert theo quy trình nhóm.

## Kiểm tra thông tin nhạy cảm
- [ ] Xem diff và file mới để phát hiện mật khẩu, token, API key, private key, file .env hoặc dữ liệu thật không được phép đưa lên Git.
- [ ] Nếu nghi ngờ lộ secret, dừng chia sẻ và báo người phụ trách để xử lý/thu hồi theo quy trình; không dán secret vào PR hay log.
- Phạm vi đã kiểm tra / công cụ nếu có:

## Review và điều kiện merge đề xuất
- [ ] Có reviewer phù hợp xem diff, test và nêu ý kiến; ghi comment hoặc phản hồi khi có.
- [ ] Check bắt buộc trên commit mới nhất thành công; không bỏ qua CI lỗi.
- [ ] Các ý kiến cần sửa đã được xử lý, không còn hội thoại bắt buộc chưa giải quyết.
- [ ] Các quyền/điều kiện và người quyết định merge được nhóm xác nhận.
- [ ] Xác nhận phương án khôi phục phù hợp nếu thay đổi có triển khai.

CI fail có thể do kiểm thử thất bại, cấu hình sai hoặc môi trường chạy lỗi; phải đọc log để xác định. CI xanh chỉ phản ánh những bước workflow thực sự chạy, không khẳng định toàn hệ thống đã được kiểm thử hay an toàn.