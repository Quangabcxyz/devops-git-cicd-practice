# DEV-27 – Bàn giao CI và quy trình Pull Request

Trạng thái: tài liệu thực hành, nội dung áp dụng dự án cần team Code/leader xác nhận. Không tự triển khai hoặc thêm secret.

## 1. Luồng PR lab
Repo cá nhân: https://github.com/Quangabcxyz/devops-git-cicd-practice
Nhánh dev23-ci-integration -> devops-lab, PR #3: https://github.com/Quangabcxyz/devops-git-cicd-practice/pull/3
Workflow .github/workflows/ci-validate.yml chạy khi pull_request hoặc workflow_dispatch; checkout, docker compose config --quiet, kiểm tra README.md và README_LAB.md không rỗng, xuất artifact nội dung cố định. Quyền contents: read; không deploy, không thêm secret.
Run đã ghi nhận Success: https://github.com/Quangabcxyz/devops-git-cicd-practice/actions/runs/42559521379 (commit 05b44a8). PR Draft, chưa merge tại thời điểm ghi nhận; reviewer/merge theo quy trình nhóm.

## 2. Giải thích fail/pass
Lỗi lab có chủ đích DEV-11: commit 23d7667 làm services sai kiểu, Compose báo services must be a mapping, run https://github.com/Quangabcxyz/devops-git-cicd-practice/actions/runs/42175187322 thất bại. Commit 44c8029 sửa cấu trúc, run https://github.com/Quangabcxyz/devops-git-cicd-practice/actions/runs/42175299453 thành công. Đây là minh chứng workflow Compose trước đó, không phải lỗi của run DEV-23; CI xanh chỉ chứng minh những bước đã chạy.

## 3. Đối chiếu dự án tại commit f1ef2176041c5b0892d5bb107f01d601616755c2
`.github/workflows/verify.yml` có job contracts (Python 3.12, kiểm contract/fixture) và verify (Java 21, Node 24, npm ci/build, Playwright Chromium, mvn -B -Dfrontend.e2e=true verify, tải báo cáo test). Đây là cấu hình đọc được, chưa thực thi kiểm thử dự án trong task này. `web-demo/package.json` có build gồm typecheck tests. Compose local chứa frontend, backend, MySQL và Mailpit.

## 4. Yêu cầu cần xác nhận trước khi áp dụng CI/CD
- Team Code/T1 xác nhận nhánh, commit, bộ kiểm tra và điều kiện đạt bắt buộc; cấu trúc frontend/backend và các test chưa có/chưa chạy.
- Xác nhận môi trường runner/Docker, test database độc lập, dữ liệu giả, biến môi trường và chính sách log/artifact.
- Xác nhận quyền tối thiểu, reviewer, branch protection/required checks, người vận hành và quy trình xử lý CI thất bại.
- CI tự build/test không đồng nghĩa đã triển khai. CD staging/production cần thiết kế, kiểm tra sức khỏe, rollback, quyền và phê duyệt theo nhóm; chưa cấu hình deploy tại đây.
- Không dùng credential production hoặc dữ liệu thật trong lab. Không khẳng định deploy, pass test ứng dụng hay gate bắt buộc khi chưa có bằng chứng.
