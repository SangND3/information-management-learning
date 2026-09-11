# Git workflow — STEEL-MES

Liên quan roadmap **A.9**. Mục tiêu: đưa repo lên GitHub và commit được sau mỗi buổi học.

> **Quy tắc:** gõ tay từng lệnh. Sau mỗi lệnh, đọc output trước khi chạy lệnh tiếp theo.
> Đừng dán cả block một lúc — bạn sẽ không biết lệnh nào gây ra lỗi gì.

---

## 0. KIỂM TRA BẢO MẬT TRƯỚC KHI LÀM BẤT CỨ ĐIỀU GÌ

Repo này liên quan dữ liệu sản xuất Nam Kim. Git **rất khó xoá sạch** một file đã commit — nó nằm trong history mãi mãi, kể cả sau khi bạn `rm`.

Nên thứ tự là: **kiểm tra `.gitignore` trước → commit sau**. Không bao giờ ngược lại.

`.gitignore` hiện tại đã chặn `*.xlsx`, `*.csv`, `**/*BM10*`, `database/seed/data/`. Tốt.

Sau khi `git add`, **bắt buộc** chạy `git status` và đọc từng tên file trong danh sách staged. Nếu thấy bất cứ file dữ liệu nào — dừng lại, sửa `.gitignore`, `git reset` rồi làm lại.

---

## 1. Cài đặt một lần (5 phút)

### 1.1 Kiểm tra Git đã có chưa

```
git --version
```

Nếu lỗi → tải Git for Windows từ `https://git-scm.com/download/win`, cài mặc định.

### 1.2 Khai báo danh tính

Hai lệnh này ghi vào config toàn máy, chỉ làm 1 lần. Thay bằng tên và email GitHub của bạn:

```
git config --global user.name "Nguyen Dang Sang"
git config --global user.email "sangnds2001@gmail.com"
```

### 1.3 Đặt nhánh mặc định là `main`

```
git config --global init.defaultBranch main
```

Vì sao: GitHub dùng `main`, Git cũ mặc định `master`. Lệch tên nhánh sẽ gây rắc rối lúc push đầu tiên.

### 1.4 Xử lý line ending trên Windows

```
git config --global core.autocrlf true
```

Vì sao: Windows kết thúc dòng bằng `CRLF`, Linux/Git dùng `LF`. Không đặt cái này thì sau vài commit, `git diff` sẽ báo "toàn bộ file đã thay đổi" trong khi bạn chỉ sửa 1 dòng.

---

## 2. Khởi tạo repo local

Mở **Git Bash** hoặc **PowerShell**, `cd` vào thư mục dự án:

```
cd ~/Desktop/STEEL-MES
```

### 2.1 Tạo repo

```
git init
```

Lệnh này tạo thư mục ẩn `.git/`. Toàn bộ history nằm trong đó. Xoá `.git/` là xoá sạch history.

### 2.2 Xem Git đang thấy gì

```
git status
```

Đọc kỹ output. Các file màu đỏ = **untracked**, Git biết có nhưng chưa quản lý.

### 2.3 Kiểm tra `.gitignore` có hoạt động

Trước khi add, kiểm tra thử một file dữ liệu giả định có bị chặn không:

```
git check-ignore -v test.xlsx
```

Nếu in ra dòng chỉ đúng rule trong `.gitignore` → đúng. Nếu **không in gì** → `.gitignore` không chặn, phải sửa ngay.

### 2.4 Stage và kiểm tra

```
git add .
git status
```

**Dừng lại ở đây.** Đọc từng tên file trong mục `Changes to be committed`. Không có file `.xlsx`, `.csv`, không có `BM10` chứ? Nếu có → `git reset`, sửa `.gitignore`, làm lại.

### 2.5 Commit đầu tiên

```
git commit -m "chore: khoi tao repo STEEL-MES - cau truc thu muc + roadmap"
```

Xem lại:

```
git log --oneline
```

---

## 3. Đẩy lên GitHub

### 3.1 Tạo repository trên GitHub

Vào `https://github.com/new`:

| Trường | Giá trị |
|---|---|
| Repository name | `steel-mes` |
| Description | MES simulation for steel CGL/CAGL line — SQL Server learning project |
| Visibility | **Private** lúc đầu. Chuyển Public sau, khi bạn đã soát lại không còn dữ liệu nội bộ. |
| Initialize with README | **KHÔNG tích.** Bạn đã có README rồi. Tích vào sẽ gây xung đột ở push đầu tiên. |

### 3.2 Nối local với GitHub

GitHub sẽ hiện sẵn URL. Chạy:

```
git remote add origin https://github.com/<tên-github-của-bạn>/steel-mes.git
git remote -v
```

### 3.3 Push

```
git branch -M main
git push -u origin main
```

Giải thích `-u origin main`: đặt **upstream**, tức gắn nhánh `main` local với `main` trên GitHub. Làm 1 lần. Từ lần sau chỉ cần `git push`.

### 3.4 Xác thực

Windows sẽ mở cửa sổ đăng nhập GitHub — chọn **Sign in with your browser**. Credential Manager sẽ nhớ, không phải nhập lại.

Nếu nó hỏi **password** trong terminal: GitHub đã **bỏ xác thực bằng password** từ 2021. Bạn cần **Personal Access Token**: GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token → tích scope `repo`. Dùng token đó thay cho password.

### 3.5 Kiểm tra

Refresh trang GitHub. Phải thấy README + cây thư mục. **Kiểm tra lại lần nữa: không có file dữ liệu nào.**

---

## 4. Quy trình sau mỗi buổi học

Đây là vòng lặp bạn dùng suốt 9 tháng tới:

```
git status                      # xem đã sửa gì
git add .
git status                      # ĐỌC danh sách staged, bước không được bỏ
git commit -m "<message>"
git push
```

### Quy ước commit message

Dùng **Conventional Commits** — chuẩn phổ biến trong industry, và là thứ nhà tuyển dụng sẽ thấy khi xem GitHub của bạn.

```
<type>: <mô tả ngắn, thể mệnh lệnh, không dấu chấm cuối>
```

| type | Dùng khi |
|---|---|
| `feat` | Thêm chức năng / bảng / query mới |
| `fix` | Sửa lỗi |
| `docs` | Sửa tài liệu, roadmap, notes |
| `refactor` | Sửa lại cấu trúc, không đổi hành vi |
| `chore` | Việc lặt vặt: .gitignore, cấu trúc thư mục |

Ví dụ cho dự án này:

```
docs: hoan thanh Phase 0.1 - MES la gi
docs: phan tang ISA-95 cho day chuyen YNCAGL
feat: tao bang Coil v0.1 voi constraint
fix: sua data type Thickness tu FLOAT sang DECIMAL(4,3)
```

> Viết commit message **không dấu** để tránh lỗi encoding trên Windows terminal. Nội dung file thì cứ viết tiếng Việt có dấu bình thường.

---

## 5. Khi nào dùng branch

Hiện tại bạn làm một mình → **cứ commit thẳng vào `main`**. Đừng tạo branch cho có. Branch không đúng mục đích chỉ làm bạn rối.

Bắt đầu dùng branch khi bạn tới **Phase B — thiết kế ERD**, vì lúc đó bạn sẽ muốn thử 2 phương án schema khác nhau mà không phá cái đang chạy:

```
git checkout -b feature/erd-coil-v2     # tạo + chuyển sang nhánh mới
# ... làm việc, commit ...
git checkout main                        # về nhánh chính
git merge feature/erd-coil-v2            # gộp vào
git branch -d feature/erd-coil-v2        # xoá nhánh đã gộp
```

Tôi sẽ dạy kỹ phần này ở A.9, kèm cả pull request và code review — đó mới là cách team thật làm việc.

---

## 6. Bốn lệnh cứu nguy

Học 4 lệnh này trước khi bạn cần đến chúng:

| Tình huống | Lệnh |
|---|---|
| Đã `git add` nhầm file, **chưa** commit | `git reset <file>` |
| Muốn xem mình đã sửa gì so với commit trước | `git diff` |
| Sửa nhầm một file, muốn quay về như commit gần nhất | `git restore <file>` |
| Commit rồi nhưng muốn sửa lại message | `git commit --amend -m "message moi"` |

**Cảnh báo:** `git restore` **xoá vĩnh viễn** thay đổi chưa commit của file đó. Không có Undo.

Nếu bạn đã commit và push một file dữ liệu nội bộ lên GitHub: `git rm` **không đủ** — file vẫn nằm trong history và vẫn tải về được. Trường hợp đó hãy dừng lại và hỏi tôi, đừng tự xử lý.
