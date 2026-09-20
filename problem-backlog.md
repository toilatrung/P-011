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
| [P-008](#p-008) | Building vs wall khi tường gắn liền công trình | Guideline mơ hồ | — | 🗣️ Đang bàn | — |
| [P-009](#p-009) | Vegetation vs sky qua khe hở tán cây | Guideline mơ hồ | — | 🗣️ Đang bàn | — |
| [P-010](#p-010) | Fence/vật thể rỗng: pixel trong khe thuộc class nào | Guideline mơ hồ | — | 🗣️ Đang bàn | — |
| [P-011](#p-011) | Boundary pole/traffic_light/traffic_sign; label `pole` quá tổng quát | Guideline mơ hồ | — | 🗣️ Đang bàn | — |
| [P-012](#p-012) | Attribute `truncated` chưa rõ áp dụng cho Semantic Segmentation | Guideline mơ hồ | — | 🔴 Mở | — |
| [P-013](#p-013) | Brush chưa hỗ trợ Closed Boundary Fill / Smart Fill | Pain point công cụ | — | 🔴 Mở | — |
| [P-014](#p-014) | Thiếu công cụ hỗ trợ geometry (ruler, snapping, alignment) | Pain point công cụ | — | 🔴 Mở | — |
| [P-015](#p-015) | Shortcut dễ thao tác nhầm, thiếu confirmation cho destructive action | Pain point công cụ | — | 🔴 Mở | — |
| [P-016](#p-016) | Reviewer trùng Annotator ở một số thời điểm | Quy trình / QC | — | 🔴 Mở | — |
| [P-017](#p-017) | Job chuyển Validation khi Annotation chưa Completed | Quy trình / QC | — | 🔴 Mở | — |
| [P-018](#p-018) | Issue trên CVAT chưa có taxonomy thống nhất | Quy trình / QC | — | 🔴 Mở | — |

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

## P-008

**Building vs wall khi tường gắn liền công trình**

- **Loại:** Guideline mơ hồ (`UNCERTAIN_CLASS`)
- **Mục guideline:** — (Semantic Segmentation, chưa có số mục)
- **Người phát hiện:** Team T011 · phát hiện trong quá trình Semantic Segmentation Task 184, tổng hợp 20/09/2026
- **Link CVAT:** Task 184 — chưa gắn frame cụ thể
- **Mô tả:** Khó phân biệt vùng `building` và `wall`, đặc biệt khi tường gắn trực tiếp với công trình.
- **Các cách hiểu:**
  1. Bề mặt thuộc cấu trúc/tòa nhà → `building`.
  2. Tường độc lập hoặc tường ranh giới → `wall`.
- **Xử lý tạm trong lúc chờ:** Bám theo guideline, không tự suy đoán khi không đủ evidence; case chưa rõ → raise Issue cho Reviewer/Lead.
- **Kết quả:** 🗣️ Đang bàn.

## P-009

**Vegetation vs sky qua khe hở tán cây**

- **Loại:** Guideline mơ hồ (`UNCERTAIN_BOUNDARY`)
- **Mục guideline:** — (Semantic Segmentation)
- **Người phát hiện:** Team T011 · Task 184, tổng hợp 20/09/2026
- **Link CVAT:** Task 184 — chưa gắn frame cụ thể
- **Mô tả:** Tán cây có nhiều khe nhỏ để lộ sky phía sau, gây khó khăn khi annotation ở mức pixel.
- **Các cách hiểu:**
  1. Tô `vegetation` liên tục theo silhouette tán cây.
  2. Giữ pixel `sky` tại các khe nhìn xuyên rõ.
- **Xử lý tạm trong lúc chờ:** Ưu tiên phương án 2 nếu nhìn thấy rõ — pixel phải phản ánh đúng semantic class thực tế đang hiển thị, không lấp vùng bằng class đoán chỉ để đơn giản hoá annotation. Đây là cách nhóm đang áp dụng thực tế trong tuần, **chưa chốt chính thức vào `so-quyet-dinh.md`**.
- **Kết quả:** 🗣️ Đang bàn.

## P-010

**Fence/vật thể rỗng: pixel trong khe thuộc class nào**

- **Loại:** Guideline mơ hồ (`UNCERTAIN_BOUNDARY` / `UNCERTAIN_SCOPE`)
- **Mục guideline:** — (Semantic Segmentation)
- **Người phát hiện:** Team T011 · Task 184, tổng hợp 20/09/2026
- **Link CVAT:** Task 184 — chưa gắn frame cụ thể
- **Mô tả:** Fence và các vật thể dạng lưới/khe cho phép nhìn thấy semantic class phía sau.
- **Các cách hiểu:**
  1. Mask liên tục theo silhouette ngoài của vật thể.
  2. Pixel trong khe thuộc class thực tế nhìn thấy phía sau.
- **Xử lý tạm trong lúc chờ:** Ưu tiên phương án 2 nếu background nhìn thấy rõ; một pixel chỉ thuộc tối đa một semantic class. Áp dụng thực tế trong tuần, **chưa chốt chính thức**.
- **Kết quả:** 🗣️ Đang bàn.

## P-011

**Boundary pole/traffic_light/traffic_sign; label `pole` quá tổng quát**

- **Loại:** Guideline mơ hồ (`SEMANTIC_BOUNDARY`)
- **Mục guideline:** — (Semantic Segmentation)
- **Người phát hiện:** Team T011 · Task 184, tổng hợp 20/09/2026
- **Link CVAT:** Task 184 — chưa gắn frame cụ thể
- **Mô tả:** Các object có thể cùng thuộc một cấu trúc vật lý nhưng phải tách thành các semantic label khác nhau — ví dụ cột đèn → `pole`, phần đèn → `traffic_light`; cột biển báo → `pole`, phần biển → `traffic_sign`. Boundary tại vùng tiếp giáp đôi khi không rõ. Ngoài ra, `pole` hiện gộp chung nhiều dạng vật thể khác hình thái (cột điện, cột đèn, cột biển báo, các dạng support khác) vào cùng một class.
- **Xử lý tạm trong lúc chờ:** Tách theo semantic meaning, không gộp toàn bộ physical structure vào một class.
- **Đề xuất:** Guideline v2 cần bổ sung positive/negative example cho `pole` và các case tiếp giáp pole/traffic_light/traffic_sign để thống nhất cách xử lý.
- **Kết quả:** 🗣️ Đang bàn.

## P-012

**Attribute `truncated` chưa rõ áp dụng cho Semantic Segmentation**

- **Loại:** Guideline mơ hồ (`GUIDELINE_AMBIGUITY`)
- **Mục guideline:** — (cần làm rõ mục nào áp dụng cho BBOX, mục nào cho Semantic Segmentation)
- **Người phát hiện:** Team T011 · Task 184, tổng hợp 20/09/2026
- **Link CVAT:** Task 184 — chưa gắn frame cụ thể
- **Mô tả:** Attribute `truncated` gây khó hiểu khi áp dụng cho Semantic Segmentation.
- **Xử lý tạm trong lúc chờ:** Trong segmentation, chỉ annotate pixel nhìn thấy; mask dừng tại biên ảnh; không suy đoán vùng ngoài frame.
- **Đề xuất:** Guideline cần làm rõ attribute nào áp dụng cho BBOX và attribute nào thực sự cần cho Semantic Segmentation.
- **Kết quả:** 🔴 Mở.

## P-013

**Brush chưa hỗ trợ Closed Boundary Fill / Smart Fill**

- **Loại:** Pain point công cụ
- **Mục guideline:** —
- **Người phát hiện:** Team T011 · Task 184, tổng hợp 20/09/2026
- **Link CVAT:** Task 184 — chưa gắn frame cụ thể
- **Mô tả:** Brush hiện tại chưa hỗ trợ tốt workflow vẽ boundary kín rồi tự động fill vùng bên trong. Với vùng lớn hoặc phức tạp, annotator phải tô thủ công nhiều lần.
- **Đề xuất:** Closed Boundary Fill, Smart Fill, Region Fill.
- **Kết quả:** 🔴 Mở.

## P-014

**Thiếu công cụ hỗ trợ geometry (ruler, snapping, alignment)**

- **Loại:** Pain point công cụ
- **Mục guideline:** —
- **Người phát hiện:** Team T011 · Task 184, tổng hợp 20/09/2026
- **Link CVAT:** Task 184 — chưa gắn frame cụ thể
- **Mô tả:** CVAT chưa có công cụ hỗ trợ ruler, straight-line alignment, curvature guidance, boundary snapping, gây khó khăn khi cần giữ boundary nhất quán. Object như vegetation, fence, pole, traffic sign, traffic light có boundary phức tạp, nhỏ hoặc chứa nhiều khe — annotate chính xác từng pixel làm tăng đáng kể thời gian thực hiện.
- **Kết quả:** 🔴 Mở.

## P-015

**Shortcut dễ thao tác nhầm, thiếu confirmation cho destructive action**

- **Loại:** Pain point công cụ
- **Mục guideline:** —
- **Người phát hiện:** Team T011 · tổng hợp 20/09/2026
- **Link CVAT:** Không gắn với job cụ thể
- **Mô tả:** Một số thao tác bằng shortcut có thể thay đổi/xóa annotation, xảy ra nhanh và thiếu confirmation trong các operation có rủi ro.
- **Đề xuất:** Undo history rõ ràng; confirmation cho destructive action; autosave/version checkpoint (liên hệ [P-007](#p-007)).
- **Kết quả:** 🔴 Mở.

## P-016

**Reviewer trùng Annotator ở một số thời điểm**

- **Loại:** Quy trình / QC
- **Mục guideline:** — (xem quy ước "không review job do chính mình gán" trong `README.md`)
- **Người phát hiện:** Team T011 · Semantic Segmentation Task 184, tổng hợp 20/09/2026
- **Link CVAT:** Task 184 — chưa gắn job/frame cụ thể
- **Mô tả:** Có thời điểm trong quá trình reassignment, reviewer trùng với chính annotator của job, vi phạm nguyên tắc review độc lập.
- **Xử lý tạm trong lúc chờ:** Team đã thực hiện reassignment để đưa workflow về đúng quy trình.
- **Đề xuất:** CVAT/workflow nên validate `reviewer_id != annotator_id`.
- **Kết quả:** 🔴 Mở.

## P-017

**Job chuyển Validation khi Annotation chưa Completed**

- **Loại:** Quy trình / QC
- **Mục guideline:** —
- **Người phát hiện:** Team T011 · Semantic Segmentation Task 184, tổng hợp 20/09/2026
- **Link CVAT:** Task 184 — chưa gắn job/frame cụ thể
- **Mô tả:** Một số job được chuyển stage sang Validation khi state annotation chưa Completed.
- **Workflow mong muốn:** Annotation / In Progress → Self-QC → Annotation / Completed → Validation → Rework hoặc Acceptance.
- **Xử lý tạm trong lúc chờ:** Team đã thực hiện reassignment để đưa job về đúng workflow.
- **Đề xuất:** Không cho phép chuyển Validation nếu state != Completed.
- **Kết quả:** 🔴 Mở.

## P-018

**Issue trên CVAT chưa có taxonomy thống nhất**

- **Loại:** Quy trình / QC
- **Mục guideline:** —
- **Người phát hiện:** Team T011 · tổng hợp 20/09/2026
- **Link CVAT:** Không gắn với job cụ thể
- **Mô tả:** Hiện tại các Issue chủ yếu thể hiện lỗi tại frame nhưng chưa có taxonomy thống nhất, gây khó khăn khi tổng hợp và cải tiến guideline.
- **Đề xuất Issue taxonomy:** `ANNOTATOR_ERROR`, `UNCERTAIN_CLASS`, `UNCERTAIN_BOUNDARY`, `UNCERTAIN_SCOPE`, `GUIDELINE_GAP`, `ATTRIBUTE_ERROR`, `TOOL_ERROR`, `DATA_ERROR`.
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
