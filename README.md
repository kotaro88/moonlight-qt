## Cài đặt ban đầu

```bash
git remote add upstream https://github.com/moonlight-stream/moonlight-qt.git
```

---

### ✅ 1. Clone project của P

Giả sử bạn đã thực hiện rồi:

```bash
git clone https://github.com/P/project.git
cd project
```

Lúc này, bạn có remote tên `origin` trỏ về repo của bạn (nếu bạn đã fork) hoặc repo của P.
✅ 2. Thêm remote `upstream` trỏ đến repo gốc của P
Nếu bạn đã fork repo và `origin` trỏ về repo riêng của bạn, thì giờ bạn nên thêm remote `upstream` trỏ về repo của P:

```bash
git remote add upstream https://github.com/P/project.git
```

Kiểm tra:

```bash
git remote -v
```

Bạn sẽ thấy:

```bash
origin    https://github.com/yourname/project.git (fetch)
origin    https://github.com/yourname/project.git (push)
upstream  https://github.com/P/project.git (fetch)
upstream  https://github.com/P/project.git (push)
```

---

### ✅ 3. Cập nhật code mới nhất từ P và merge vào code của bạn

#### 📥 Bước 1: Fetch dữ liệu mới từ P

```bash
git fetch upstream
```

🔀 Bước 2: Merge code từ nhánh chính của P (ví dụ: `main`)

```bash
git checkout main  # Hoặc nhánh bạn đang làm việc
git merge upstream/main
```

> Nếu có conflict thì Git sẽ yêu cầu bạn giải quyết thủ công.

#### ✅ Sau đó bạn có thể commit, push như bình thường:

```bash
git push origin main
```

---

## 📌 Lưu ý

- Nếu bạn làm việc trên một nhánh riêng (ví dụ: `feature-xyz`), hãy merge từ `upstream/main` vào nhánh đó:

```bash
git checkout feature-xyz
git merge upstream/main
```

---

🧠 Gợi ý thêm: Dùng `rebase` thay vì `merge` (tùy trường hợp)

```bash
git checkout main
git fetch upstream
git rebase upstream/main
```

> `rebase` giúp lịch sử commit sạch hơn nhưng cần cẩn thận nếu bạn đã push lên remote rồi.

---
