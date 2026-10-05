# Các bước thực hiện

## Bước 1: Khởi tạo 4 commit ban đầu

```bash
# Commit 1
echo "console.log('auth');" > auth.js
git add auth.js
git commit -m "feat: khoi tao module auth"

# Commit 2
echo "// fix typo" >> auth.js
git add auth.js
git commit -m "fix typo"

# Commit 3
echo "// utility functions" >> auth.js
git add auth.js
git commit -m "adds utility functions"

# Commit 4
echo "debug" > temp.txt
git add temp.txt
git commit -m "add temp file for debug"

```

## Bước 2: Chạy lệnh Interactive Rebase

```bash
git rebase -i --root

```

## Bước 3: Cấu hình các lệnh pick, squash, drop

Trong giao diện soạn thảo, chỉnh sửa cấu hình các dòng:

```text
pick   <mã-hash> feat: khoi tao module auth
squash <mã-hash> fix typo
squash <mã-hash> adds utility functions
drop   <mã-hash> add temp file for debug

```

## Bước 4: Đổi thông điệp (Commit message)

Sau khi lưu cấu hình rebase, tiếp tục thay đổi thông điệp commit gộp ở bảng soạn thảo tiếp theo thành:

```text
feat: hoan thien module authentication

```

Lưu và thoát trình soạn thảo (`:wq`).

## Bước 5: Kiểm tra lịch sử

Chạy lệnh kiểm tra để đảm bảo chỉ còn duy nhất một commit sạch sẽ:

```bash
git log --oneline
```
