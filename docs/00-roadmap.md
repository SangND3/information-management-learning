# STEEL-MES — Lộ trình & Tiến độ

Ngân sách thực tế: **dưới 5 giờ/tuần** (~200 giờ/năm)
Session: **75–90 phút**, mỗi buổi trọn vẹn một khái niệm.

---

## NĂM 1 — Phase 0 → C (~152 giờ, ~9 tháng)

| Phase | Nội dung | Giờ | Mốc hoàn thành |
|---|---|---:|---|
| 0 | MES/ERP cơ bản, ISA-95, MES vs ERP vs SCADA | ~12 | Vẽ được kiến trúc 5 tầng của nhà máy |
| A | SQL fundamentals | ~30 | Tự viết SELECT/WHERE/JOIN không cần tra |
| B | Advanced SQL + Database design | ~50 | ERD STEEL-MES v1.0 + chuẩn hóa xong |
| C | SQL Server: T-SQL, index, execution plan, transaction | ~60 | Đọc được execution plan, tối ưu 1 query thật |

## NĂM 2 (hoãn, không xóa)

| Phase | Nội dung | Giờ |
|---|---|---:|
| C.5 | C# fundamentals — OOP, GC, LINQ, async | ~50 |
| D | ASP.NET Core — 1 vertical slice (GET /api/coils/{id}/history) | ~40 |

---

## Trình độ đầu kỳ (tự khai, 2026-09)

| Kỹ năng | Mức |
|---|---|
| C | Làm việc được |
| C++ | Cơ bản |
| Python / JavaScript / VBA | ~0 (vibe code) |
| SQL | ~0 |
| C# / .NET | Chưa từng |
| MES / ERP domain | 0 — bắt đầu từ cơ bản |
| Công nghệ CAGL / quy trình thép | Tốt (tài sản, không phải vibe) |

---

## Bảng theo dõi tiến độ

Quy ước trạng thái:

- `[ ]` chưa học
- `[~]` đã tiếp xúc, CHƯA tự làm được
- `[x]` đã nắm — tiêu chuẩn: **giải thích ngược lại được** và tự viết được, không tra cứu

### Phase 0 — MES/ERP cơ bản

| # | Chủ đề | Trạng thái | Ngày | Ghi chú |
|---|---|---|---|---|
| 0.1 | MES là gì, tồn tại để giải quyết vấn đề gì | [ ] | | |
| 0.2 | ISA-95 — 5 tầng Level 0..4 | [~] | 2026-09-11 | mới nghe qua |
| 0.3 | MES vs ERP — ranh giới dữ liệu | [ ] | | |
| 0.4 | MES vs SCADA/HMI vs PLC | [ ] | | |
| 0.5 | Các module MES chính (Production, Quality, Equipment, OEE) | [ ] | | |
| 0.6 | Traceability & genealogy | [ ] | | |
| 0.7 | Ánh xạ khái niệm MES vào dây chuyền CAGL thật | [ ] | | |

### Phase A — SQL fundamentals

| # | Chủ đề | Trạng thái | Ngày | Ghi chú |
|---|---|---|---|---|
| A.1 | Khái niệm database, table, row, column | [ ] | | |
| A.2 | Data type (và bẫy FLOAT vs DECIMAL, VARCHAR vs NVARCHAR) | [ ] | | |
| A.3 | Primary key / Foreign key | [ ] | | |
| A.4 | SELECT / WHERE / ORDER BY / DISTINCT | [ ] | | |
| A.5 | NULL & logic ba giá trị | [ ] | | |
| A.6 | INSERT / UPDATE / DELETE | [ ] | | |
| A.7 | Constraint | [ ] | | |
| A.8 | Tư duy set-based (bỏ thói quen vòng lặp kiểu C) | [ ] | | |
| A.9 | Git cơ bản — init, commit, branch, push | [ ] | | |

### Phase B — Advanced SQL + Database design

| # | Chủ đề | Trạng thái | Ngày | Ghi chú |
|---|---|---|---|---|
| B.1 | INNER / LEFT / RIGHT / FULL JOIN | [ ] | | |
| B.2 | GROUP BY / HAVING / aggregate function | [ ] | | |
| B.3 | Subquery | [ ] | | |
| B.4 | CTE | [ ] | | |
| B.5 | CASE / UNION | [ ] | | |
| B.6 | Window function & ranking | [ ] | | |
| B.7 | Date/time & string function | [ ] | | |
| B.8 | Normalization (1NF, 2NF, 3NF) | [ ] | | |
| B.9 | ERD — thiết kế STEEL-MES v1.0 | [ ] | | |
| B.10 | Naming convention & audit field | [ ] | | |

### Phase C — SQL Server

| # | Chủ đề | Trạng thái | Ngày | Ghi chú |
|---|---|---|---|---|
| C.1 | Kiến trúc SQL Server, SSMS | [ ] | | |
| C.2 | T-SQL procedural (DECLARE, IF, WHILE) | [ ] | | |
| C.3 | View | [ ] | | |
| C.4 | Stored procedure & function | [ ] | | |
| C.5 | Trigger | [ ] | | |
| C.6 | Index — clustered vs nonclustered, B-tree | [ ] | | |
| C.7 | Execution plan — đọc và phân tích | [ ] | | |
| C.8 | SARGable & query optimization | [ ] | | |
| C.9 | Transaction & ACID | [ ] | | |
| C.10 | Locking & isolation level | [ ] | | |
| C.11 | Backup / restore | [ ] | | |
| C.12 | User, role, permission | [ ] | | |

---

## Việc chuẩn bị

- [ ] Cài SQL Server Developer Edition
- [ ] Cài SSMS
- [ ] Export dataset cơ tính 267 coil (T8/2026)
- [ ] Export dữ liệu air knife (~939 records)
- [ ] Export form BM10-QT02-SXPM mẫu
- [ ] Tạo tài khoản GitHub (nếu chưa có)

---

## Nhật ký buổi học

| Buổi | Ngày | Phase | Nội dung | Phút |
|---|---|---|---|---:|
| | | | | |
