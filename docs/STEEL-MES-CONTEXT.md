# STEEL-MES — Context bàn giao

> File này dùng để upload vào **Project knowledge**.
> Mục đích: mọi phiên chat / Cowork mới đều nắm ngay bối cảnh mà không cần kể lại.
> Cập nhật lần cuối: 2026-09-11

---

## 1. Người học

- Nguyễn Đăng Sang — Kỹ sư vận hành, dây chuyền CAGL (YNCAGL, thiết bị WISDRI)
- Nền: Embedded Software Engineer (C, AUTOSAR/MCAL, CAN, firmware)
- Mục tiêu: Embedded SW Engineer → MES/ERP Engineer

## 2. Trình độ đầu kỳ (tự khai, KHÔNG được đánh giá cao hơn)

| Kỹ năng | Mức |
|---|---|
| C | Làm việc được |
| C++ | Cơ bản |
| Python / JavaScript / VBA | ~0 — sản phẩm cũ là **vibe code** |
| SQL | ~0 |
| C# / .NET | Chưa từng |
| MES / ERP domain | **0 — tờ giấy trắng** |
| Công nghệ CAGL / quy trình thép | Tốt — kiến thức thật |

**Lưu ý cho mentor:** các sản phẩm trước đây (Streamlit OCR pipeline, regression model
air knife, app Next.js/Supabase, Excel VBA) **không** phản ánh năng lực coding.
Đừng suy ra trình độ từ sản phẩm đầu ra.

## 3. Ràng buộc

- Thời gian: **dưới 5 giờ/tuần**
- Session: 75–90 phút, mỗi buổi trọn vẹn một khái niệm, không giao bài kéo dài
- Ngôn ngữ: **tiếng Việt**, thuật ngữ chuyên ngành giữ **tiếng Anh**

## 4. Quyết định đã chốt

- **Stack:** SQL Server + C#/ASP.NET Core (KHÔNG dùng Postgres/Supabase)
- **Mục tiêu năm 1:** Phase 0 → C (~152 giờ, ~9 tháng). C#/ASP.NET Core hoãn sang năm 2
- **Dữ liệu:** dùng dữ liệu YNCAGL thật để seed, KHÔNG dùng synthetic data
- **Phase 0** (~12h) MES/ERP cơ bản, ISA-95
  **Phase A** (~30h) SQL fundamentals
  **Phase B** (~50h) Advanced SQL + Database design
  **Phase C** (~60h) SQL Server: T-SQL, index, execution plan, transaction

## 5. Quy tắc chống vibe code (bắt buộc)

1. Không viết code hộ. Thứ tự: hint → câu hỏi dẫn dắt → pseudocode → lời giải
2. Sang gõ tay từng dòng, không copy-paste
3. Mỗi lời giải phải **giải thích ngược lại được** mới tính là đã học
4. Chỉ đánh `[x]` trong roadmap khi tự viết được không cần tra cứu

## 6. Phân quyền ghi file (cho Cowork)

| Thư mục | Ai được ghi |
|---|---|
| `exercises/` | **Chỉ Sang** |
| `database/schema/`, `database/queries/` | **Chỉ Sang** |
| `notes/` | **Chỉ Sang** |
| `docs/` (gồm `00-roadmap.md`, `02-erd/`) | Cả hai |
| `database/seed/` | Cả hai |

Khi Sang bí ở `exercises/`: hướng dẫn trong chat, **KHÔNG ghi file**.

## 7. Cấu trúc folder

```
Desktop/STEEL-MES/
├── README.md
├── .gitignore              <- chặn *.xlsx *.csv *BM10*
├── docs/00-roadmap.md      <- checklist 38 chủ đề + bảng tiến độ
├── docs/01-requirements.md
├── docs/02-erd/
├── database/{schema,seed,queries}/
├── exercises/phase-{0,A,B,C}/
└── notes/TEMPLATE.md
```

## 8. Bảo mật dữ liệu

Dữ liệu sản xuất Nam Kim **không** đẩy lên GitHub. `.gitignore` đã chặn sẵn.
Phạm vi dữ liệu được mang ra khỏi công ty do Sang tự quyết định.

## 9. Trạng thái hiện tại

- Chưa bắt đầu Phase 0. Roadmap đã chốt, folder đã tạo, chưa gõ "Start"
- Chưa cài SQL Server Developer Edition + SSMS
- Chưa export dataset CAGL (267 coil T8/2026, ~939 records air knife, form BM10-QT02-SXPM)
- ISA-95 mới nghe qua một lần — trạng thái `[~]`, chưa kiểm tra
