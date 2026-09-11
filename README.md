# STEEL-MES

Mô phỏng hệ thống **MES** (Manufacturing Execution System) cho nhà máy thép,
dựa trên dây chuyền **CGL/CAGL** thực tế.

Tác giả: Nguyễn Đăng Sang
Bắt đầu: 2026-09

---

## Mục tiêu

Chuyển từ **Embedded Software Engineer** sang **MES/ERP Engineer**,
lấy STEEL-MES làm môi trường thực hành chính.

**Mục tiêu NĂM 1:** làm chủ **SQL Server + Database Design**,
có database STEEL-MES chạy trên dữ liệu CAGL thật,
đủ tự tin phỏng vấn vị trí **MES / Database Engineer (junior)**.

C# + ASP.NET Core: hoãn sang năm 2.

---

## Tech stack

| Lớp | Công nghệ | Trạng thái |
|---|---|---|
| Database | Microsoft SQL Server (Developer Edition) | Năm 1 |
| Tool | SQL Server Management Studio (SSMS) | Năm 1 |
| Ngôn ngữ truy vấn | T-SQL | Năm 1 |
| Backend | C# + ASP.NET Core | Năm 2 |
| ORM | Entity Framework Core | Năm 2 |
| Version control | Git + GitHub | Cuối Phase A |

---

## Cấu trúc thư mục

```
STEEL-MES/
├── README.md
├── .gitignore
├── docs/
│   ├── 00-roadmap.md        <- lộ trình + tiến độ
│   ├── 01-requirements.md   <- yêu cầu hệ thống
│   └── 02-erd/              <- sơ đồ quan hệ thực thể (ERD)
├── database/
│   ├── schema/              <- CREATE TABLE scripts
│   ├── seed/                <- script nạp dữ liệu CAGL
│   └── queries/             <- query dùng lại được
├── exercises/
│   ├── phase-0/             <- MES/ERP cơ bản
│   ├── phase-A/             <- SQL fundamentals
│   ├── phase-B/             <- Advanced SQL + DB design
│   └── phase-C/             <- SQL Server internals
└── notes/                   <- ghi chú từng buổi học
```

---

## Nguồn dữ liệu

Database được nạp bằng **dữ liệu thật từ dây chuyền YNCAGL** (Nam Kim CAGL,
thiết bị WISDRI), KHÔNG dùng dữ liệu giả:

- Dataset cơ tính 267 coil (T8/2026): pyrometer P1-P10, SPM force/elongation, YS/TS/EL
- Dữ liệu air knife (~939 records)
- Form theo dõi thông số BM10-QT02-SXPM

> **LƯU Ý BẢO MẬT:** file dữ liệu gốc KHÔNG nằm trong repo này.
> Xem `.gitignore`. Cân nhắc kỹ phạm vi dữ liệu được phép mang ra ngoài công ty.

---

## Quy tắc làm việc

1. Không copy-paste code. Gõ tay từng dòng.
2. Mỗi lời giải nhận được phải giải thích ngược lại được, nếu không thì coi như chưa học.
3. Mỗi buổi học ghi lại vào `notes/` và cập nhật `docs/00-roadmap.md`.
