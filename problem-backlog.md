# Problem backlog

Những trường hợp guideline chưa trả lời rõ và các pain point về công cụ trong quá trình gán nhãn.

## Danh sách

| Mã | Tóm tắt | Loại | Mục guideline | Trạng thái | Kết quả |
|---|---|---|---|---|---|
| [P-001](#p-001) | Drivable area: chỉ làn ego hay toàn bộ mặt đường quan sát được | Guideline mơ hồ | §4.1 | 🗣️ Đang bàn | — |
| [P-002](#p-002) | Crosswalk/lane marking: từng vạch hay một đường đại diện | Guideline mơ hồ | §4.2 | 🗣️ Đang bàn | — |
| [P-003](#p-003) | Polyline lane marking dài tốn nhiều thao tác | Pain point công cụ | §4.2 | 🔴 Mở | — |
| [P-004](#p-004) | Export dùng cả `traffic sign` và `traffic_sign` | Guideline / taxonomy mâu thuẫn | — | 🔴 Mở | — |
| [P-005](#p-005) | Automatic Annotation chưa có model khả dụng | Pain point công cụ | — | 🔴 Mở | — |
| [P-006](#p-006) | Night/low-light: khó xác định boundary xe ở xa hoặc xe tối màu | Guideline mơ hồ | §3.1 | 🗣️ Đang bàn | — |
| [P-007](#p-007) | CVAT/server mất kết nối, nguy cơ mất annotation chưa persist | Pain point công cụ | — | 🔴 Mở | — |

**Trạng thái:** 🔴 Mở · 🗣️ Đang bàn · ↗️ Hỏi BTC · ✅ Đã chốt (trỏ sang QĐ) · 🛠️ Làm tool · ⚪ Bỏ (ghi lý do)

---

## P-001

**Drivable area: chỉ vùng ego có thể chạy trực tiếp hay toàn bộ mặt đường quan sát được**

- **Loại:** Guideline mơ hồ (`UNCERTAIN_BOUNDARY`)
- **Mục guideline:** §4.1 — Polygon / Drivable Area
- **Người phát hiện:** @toilatrung · 17/09/2026; xác nhận lặp lại bởi @DucHa180104 và @Vietanhhhhhh2003 · 19/09/2026
- **Link CVAT:**
  - https://cvat.note.transformerlabs.ai/tasks/130/jobs/1370
  - https://cvat.note.transformerlabs.ai/tasks/184/jobs/1589?frame=50
  - https://cvat.note.transformerlabs.ai/tasks/184/jobs/1587
- **Mô tả:** Chưa rõ `area/drivable` chỉ lấy phần đường theo hướng/lane ego đang di chuyển hay bao gồm cả phần đường và làn đối diện vẫn thuộc mặt đường có thể lưu thông.
- **Các cách hiểu:**
  1. Chỉ vùng đường thuộc hướng/lane ego đang di chuyển.
  2. Toàn bộ vùng mặt đường có thể chạy quan sát được, kể cả làn đối diện.
- **Xử lý tạm trong lúc chờ:** Chỉ bám theo vùng có evidence trên ảnh, không mở rộng theo suy đoán; đưa case chưa rõ cho reviewer/mentor chốt. Trong thực tế, @DucHa180104 và @Vietanhhhhhh2003 đang tạm chọn PA2 (toàn bộ phần đường có thể chạy) cho tới khi có rule chung — cần chốt sớm vì đây không phải là hướng xử lý bảo thủ ban đầu.
- **Kết quả:** 🗣️ Đang bàn. Cần chốt rule chung, không để từng annotator tự chọn phương án.

## P-002

**Crosswalk/lane marking: annotate từng vạch hay dùng một polyline đại diện**

- **Loại:** Guideline mơ hồ (`UNCERTAIN_SCOPE`)
- **Mục guideline:** §4.2 — Polyline / Lane Marking
- **Người phát hiện:** @toilatrung · 17/09/2026
- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/130/jobs/1370
- **Mô tả:** Chưa rõ lane/crosswalk cần biểu diễn từng vạch trắng riêng hay một polyline đại diện cho toàn bộ vùng qua đường; đồng thời chưa rõ có nối qua khoảng trống giữa các vạch hay không.
- **Các cách hiểu:**
  1. Annotate từng phần marking nhìn thấy, không nối qua vùng không có vạch.
  2. Dùng một đường đại diện xuyên suốt toàn bộ crosswalk.
- **Xử lý tạm trong lúc chờ:** Không nối tắt qua vùng không có evidence; chờ team thống nhất rule chung.
- **Kết quả:** 🗣️ Đang bàn. Cần bổ sung link tới frame đại diện khi xác định được.

## P-003

**Polyline lane marking dài tốn nhiều thao tác thủ công**

- **Loại:** Pain point công cụ
- **Mục guideline:** §4.2 — Polyline / Lane Marking
- **Người phát hiện:** @Vietanhhhhhh2003, @duy12345-6789 · 17/09/2026
- **Link CVAT:**
  - https://cvat.note.transformerlabs.ai/tasks/130/jobs/1372
  - https://cvat.note.transformerlabs.ai/tasks/130/jobs/1376
- **Mô tả:** Lane marking dài cần nhiều điểm và nhiều thao tác lặp, làm tăng thời gian annotate.
- **Hướng đang cân nhắc:**
  1. Tiếp tục annotate thủ công trong tuần 01 để không làm chậm tiến độ.
  2. Nghiên cứu auto-annotation hoặc công cụ hỗ trợ sau khi rule lane/crosswalk được chốt.
- **Xử lý tạm trong lúc chờ:** Chưa làm tool; ghi nhận thời gian và dạng ảnh gây tốn thao tác để đánh giá ưu tiên.
- **Kết quả:** 🔴 Mở.

## P-004

**Tên class `traffic sign` và `traffic_sign` không nhất quán trong export**

- **Loại:** Guideline / taxonomy mâu thuẫn
- **Mục guideline:** —
- **Người phát hiện:** @toilatrung · 17/09/2026
- **Link CVAT:** Chưa có frame cụ thể; phát hiện trong file export.
- **Mô tả:** Export hiện có cả naming `traffic sign` và `traffic_sign`. Nếu không chuẩn hoá trước bước sau, cùng một class có thể bị tách thành hai nhãn.
- **Các cách hiểu:**
  1. Hai tên cùng chỉ một class và cần map về một tên chuẩn.
  2. Hai tên là hai class khác nhau — cần taxonomy xác nhận trước khi gộp.
- **Xử lý tạm trong lúc chờ:** Không tự động gộp hoặc dùng export downstream cho tới khi Lead/mentor xác nhận taxonomy chuẩn.
- **Kết quả:** 🔴 Mở.

## P-005

**Automatic Annotation trong CVAT chưa có model khả dụng**

- **Loại:** Pain point công cụ
- **Mục guideline:** —
- **Người phát hiện:** @toilatrung · 17/09/2026
- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/130/jobs/1370
- **Mô tả:** CVAT chưa cung cấp model Automatic Annotation khả dụng cho task, nên phần lớn annotation phải thao tác thủ công.
- **Hướng đang cân nhắc:**
  1. Hoàn thành tuần 01 bằng thao tác thủ công.
  2. Sau khi ổn định guideline và taxonomy, đánh giá model hoặc tool hỗ trợ phù hợp.
  3. Đề xuất (Team Lead, 19/09/2026): LLM/CV assistant đọc taxonomy + loại dataset + cấu hình máy (GPU/RAM) của annotator để recommend model pre-label và hỗ trợ sinh/chỉnh CVAT label configuration.
- **Xử lý tạm trong lúc chờ:** Chưa làm tool; ưu tiên chất lượng nhãn và decision log.
- **Kết quả:** 🔴 Mở.

## P-006

**Night/low-light: khó xác định boundary của xe ở xa hoặc xe tối màu**

- **Loại:** Guideline mơ hồ (`UNCERTAIN_CLASS` / `ATTRIBUTE_CHECK`)
- **Mục guideline:** §3.1
- **Người phát hiện:** @DucHa180104, @Vietanhhhhhh2003 · 19/09/2026
- **Link CVAT:**
  - https://cvat.note.transformerlabs.ai/tasks/184/jobs/1589?frame=50
  - https://cvat.note.transformerlabs.ai/tasks/130/jobs/1374?frame=50
  - https://cvat.note.transformerlabs.ai/tasks/184/jobs/1587
  - https://cvat.note.transformerlabs.ai/tasks/130/jobs/1372
- **Mô tả:** Trong điều kiện ban đêm/thiếu sáng, khó xác định chính xác boundary của xe ở xa hoặc xe màu tối; nhiều trường hợp chỉ nhìn rõ đèn và một phần thân xe.
- **Các cách hiểu:**
  1. Chỉ vẽ BBox cho phần object còn đủ visual evidence (đèn/thân xe nhìn rõ), bỏ qua phần suy đoán.
  2. Ước lượng toàn bộ boundary xe kể cả phần khuất/tối dựa trên hình dạng suy đoán được.
- **Xử lý tạm trong lúc chờ:** Vẽ BBox bám sát phần đèn/thân xe còn đủ visual evidence, không suy đoán phần khuất.
- **Kết quả:** 🗣️ Đang bàn. Cần bổ sung ví dụ minh hoạ (night, low-light, vehicle far away, dark vehicle) vào Guideline v2.

## P-007

**CVAT/server mất kết nối, nguy cơ mất annotation chưa persist**

- **Loại:** Pain point công cụ
- **Mục guideline:** —
- **Người phát hiện:** @toilatrung · 19/09/2026
- **Link CVAT:** Không gắn với job cụ thể; xảy ra ở mức server/kết nối trong quá trình labeling.
- **Mô tả:** CVAT/server từng mất kết nối trong lúc annotate. Annotation thực hiện trong khoảng thời gian mất kết nối có thể bị mất hoàn toàn, và không xác định rõ phần nào đã persist, phần nào chưa được lưu — annotator phải làm lại mà không chắc làm lại đúng phần đã mất.
- **Hướng đang cân nhắc:**
  1. Annotator tự lưu ý chủ động save thường xuyên trong lúc chờ giải pháp công cụ.
  2. Xây dựng autosave/checkpoint theo frame, lưu annotation tạm theo version, và merge incremental annotation vào dataset chính khi kết nối ổn định trở lại.
- **Xử lý tạm trong lúc chờ:** Chưa có cơ chế autosave; annotator chủ động save/kiểm tra lại annotation sau khi mất kết nối trước khi tiếp tục.
- **Kết quả:** 🔴 Mở.

---

## Mẫu để copy

```markdown
## P-NNN

**Tóm tắt một dòng**

- **Loại:** Guideline chưa nói tới | Guideline mơ hồ | Guideline mâu thuẫn | Pain point công cụ
- **Mục guideline:** §
- **Người phát hiện:** @ · dd/mm/yyyy
- **Link CVAT:**
  - https://…/tasks/<id>/jobs/<id>?frame=<n> — mô tả frame
- **Mô tả:**
- **Các cách hiểu:** (với pain point công cụ thì ghi **Hướng đang cân nhắc:**)
  1.
  2.
- **Xử lý tạm trong lúc chờ:**
- **Kết quả:** 🔴 Mở
```

Nhớ thêm một dòng vào bảng **Danh sách** ở đầu file.
