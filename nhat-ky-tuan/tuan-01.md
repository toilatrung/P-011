# Nhật ký tuần 01 · 15/09 – 21/09/2026

_Cập nhật cuối tuần — 20/09/2026, tổng hợp báo cáo kết quả tuần 01: BBOX 4/4 job Accepted, Semantic Segmentation 4/4 job Accepted, tổng 8/8 job hoàn thành._

**Lead chính:** Trịnh Quang Trung ([@toilatrung](https://github.com/toilatrung)) — phụ trách phân công task SEGMENTATION

**Lead phụ:** Trần Đức Thọ (GitHub chưa cung cấp) — phụ trách phân công các task BBOX

**Dữ liệu / task CVAT:** [Task 130 — W1-BBOX-G2-T1](https://cvat.note.transformerlabs.ai/tasks/130) · [Task 184 — W1-SEG-G2-T1](https://cvat.note.transformerlabs.ai/tasks/184)

## Thành viên và phân công

| Thành viên | Vị trí | Phân công tuần này |
|---|---|---|
| Trịnh Quang Trung (2A202602096, @toilatrung) | Lead chính · Annotator · Reviewer | Phân công task SEGMENTATION; annotate job 1370 (đã xong 25/25); review Semantic Segmentation cho 4 thành viên còn lại |
| Trần Đức Thọ (2A202602324) | Lead phụ · Annotator · Reviewer | Phân công các task BBOX; annotate job 1586; review job 1370, 1376 |
| Nguyễn Xuân Việt Anh (2A202602102, @Vietanhhhhhh2003) | Annotator · Reviewer | Annotate job 1372, 1587; review job 1374 |
| Nguyễn Đức Hà (2A202602105) | Annotator · Reviewer | Annotate job 1374, 1589; review job 1372 |
| Lê Ngọc Nam (2A202602060, @duy12345-6789) | Annotator · Reviewer | Annotate job 1376, 1591; review job 1374 |

## Công việc

| # | Nội dung công việc | Annotator | Reviewer / điều phối | Hoàn thành | Ghi chú |
|---|---|---|---|---|---|
| 1 | [Job 1370](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1370) — W1-BBOX-G2-T1, G02_B001–G02_B025 | @toilatrung | Trần Đức Thọ | ✅ Accepted | Annotate + review xong, đã nghiệm thu; từng vướng [P-001](../problem-backlog.md#p-001), [P-002](../problem-backlog.md#p-002) (chưa chốt chính thức, xử lý tạm theo backlog) |
| 2 | [Job 1372](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1372) — W1-BBOX-G2-T1 | @Vietanhhhhhh2003 | Nguyễn Đức Hà | ✅ Accepted | Đã qua review và nghiệm thu; từng vướng [P-006](../problem-backlog.md#p-006) (frame ban đêm) |
| 3 | [Job 1374](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1374) — W1-BBOX-G2-T1 | Nguyễn Đức Hà | Lê Ngọc Nam | ✅ Accepted | Đã qua review và nghiệm thu; từng vướng [P-006](../problem-backlog.md#p-006) (frame ban đêm, xem `?frame=50`) |
| 4 | [Job 1376](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1376) — W1-BBOX-G2-T1 | @duy12345-6789 | Trần Đức Thọ | ✅ Accepted | Đã nhận cập nhật và nghiệm thu; BBOX Task 130 đạt 4/4 job |
| 5 | [Job 1586](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1586) — W1-SEG-G2-T1 | Trần Đức Thọ | @toilatrung | ✅ Accepted | Sau rework theo feedback Lead, review lại: PASS |
| 6 | [Job 1587](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1587) — W1-SEG-G2-T1 | @Vietanhhhhhh2003 | @toilatrung | ✅ Accepted | Sau rework theo feedback Lead, review lại: PASS |
| 7 | [Job 1589](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1589) — W1-SEG-G2-T1 | Nguyễn Đức Hà | @toilatrung | ✅ Accepted | Annotate xong 25/25; Team Lead review: PASS |
| 8 | [Job 1591](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1591) — W1-SEG-G2-T1 | @duy12345-6789 | @toilatrung | ✅ Accepted | Annotate xong 25/25; Team Lead review: PASS |

Mức hoàn thành: ✅ xong **và đã qua review** · 🟡 đã/đang annotate nhưng chưa xác nhận review · ⛔ bị chặn · ⬜ chưa bắt đầu hoặc chưa có cập nhật

## Tổng kết cuối tuần (20/09)

- BBOX (Task 130): 4/4 job (1370, 1372, 1374, 1376) đã annotate + review xong, **toàn bộ Accepted**.
- SEG (Task 184): 4/4 job **Accepted** — 1589 (Hà) và 1591 (Nam) pass ngay vòng đầu; 1586 (Thọ) và 1587 (Việt Anh) pass sau rework theo feedback Lead.
- Tổng: **8/8 job hoàn thành và nghiệm thu** trong tuần 01; Semantic Segmentation xử lý tổng cộng 100 frame (4 job × 25 frame).
- Quy trình thực tế đã áp dụng cho Semantic Segmentation: Annotation → Self-check → Lead review → Cross-review → Raise Issue → Rework → Review lại → Acceptance.
- Số liệu annotate/review/issue theo KuteAPP được ghi nhận sau nhiều lần reassignment và chuyển stage, nên không phản ánh đúng phân công ban đầu — dùng để tham khảo khối lượng review/issue, không dùng để đánh giá cá nhân.
- Phát hiện thêm 5 edge case guideline mới cho Semantic Segmentation: building vs wall, vegetation vs sky qua khe lá, fence/vật thể rỗng, boundary pole/traffic_light/traffic_sign, và attribute truncated trong segmentation — xem [P-008](../problem-backlog.md#p-008)–[P-012](../problem-backlog.md#p-012).
- Phát hiện 2 vấn đề quy trình QC trong lúc labeling: có thời điểm reviewer trùng chính annotator, và job được chuyển Validation khi annotation chưa Completed — cả hai đã được xử lý bằng reassignment trong tuần, xem [P-016](../problem-backlog.md#p-016), [P-017](../problem-backlog.md#p-017).
- Edge case mở (chưa chốt chính thức): [P-001](../problem-backlog.md#p-001), [P-002](../problem-backlog.md#p-002), [P-006](../problem-backlog.md#p-006), [P-008](../problem-backlog.md#p-008)–[P-012](../problem-backlog.md#p-012).
- Pain point / rủi ro công cụ: [P-003](../problem-backlog.md#p-003), [P-004](../problem-backlog.md#p-004), [P-005](../problem-backlog.md#p-005), [P-007](../problem-backlog.md#p-007), [P-013](../problem-backlog.md#p-013)–[P-015](../problem-backlog.md#p-015) (mới).
- Vấn đề quy trình / QC: [P-016](../problem-backlog.md#p-016)–[P-018](../problem-backlog.md#p-018) (mới).

## Vướng mắc

- Boundary của drivable area tại giao lộ hoặc ảnh nhiều làn còn có hai cách hiểu ([P-001](../problem-backlog.md#p-001)).
- Chưa rõ crosswalk/lane marking cần tách từng vạch hay dùng một polyline đại diện, và có được nối qua khoảng trống hay không ([P-002](../problem-backlog.md#p-002)).
- Polyline cho lane marking và polygon mặt đường dài tốn nhiều thao tác thủ công, kể cả căn boundary giữa polygon và polyline lane marking ([P-003](../problem-backlog.md#p-003)).
- Export có cả `traffic sign` và `traffic_sign`; cần kiểm tra taxonomy trước khi dùng dataset cho bước sau ([P-004](../problem-backlog.md#p-004)).
- Automatic Annotation trong CVAT chưa có model khả dụng ([P-005](../problem-backlog.md#p-005)).
- Frame ban đêm/thiếu sáng khó xác định boundary của xe ở xa hoặc xe tối màu, ảnh hưởng consistency của BBOX ([P-006](../problem-backlog.md#p-006)).
- CVAT/server từng mất kết nối trong lúc labeling, có nguy cơ mất annotation chưa persist mà không xác định được rõ phần nào đã lưu ([P-007](../problem-backlog.md#p-007)).
- **Mới:** khó phân biệt building vs wall khi tường gắn liền công trình ([P-008](../problem-backlog.md#p-008)).
- **Mới:** tán cây có khe hở lộ sky phía sau, chưa rõ có giữ pixel sky tại khe hay tô liên tục theo silhouette ([P-009](../problem-backlog.md#p-009)).
- **Mới:** fence và vật thể dạng lưới/khe cho thấy semantic class phía sau, chưa rõ cách xử lý pixel trong khe ([P-010](../problem-backlog.md#p-010)).
- **Mới:** boundary giữa pole/traffic_light/traffic_sign trên cùng một cấu trúc vật lý chưa rõ, và label `pole` đang gộp nhiều loại cột khác nhau ([P-011](../problem-backlog.md#p-011)).
- **Mới:** chưa rõ attribute `truncated` áp dụng thế nào cho Semantic Segmentation ([P-012](../problem-backlog.md#p-012)).
- **Mới:** brush chưa hỗ trợ Closed Boundary Fill / Smart Fill cho vùng khép kín ([P-013](../problem-backlog.md#p-013)).
- **Mới:** thiếu công cụ hỗ trợ geometry (ruler, straight-line alignment, boundary snapping) khiến pixel-level annotation cho vegetation/fence/pole/traffic sign/traffic light tốn nhiều thời gian ([P-014](../problem-backlog.md#p-014)).
- **Mới:** một số shortcut có thể xoá/thay đổi annotation nhanh mà chưa có confirmation cho thao tác rủi ro ([P-015](../problem-backlog.md#p-015)).
- **Mới:** có thời điểm reviewer trùng chính annotator của job, vi phạm nguyên tắc review độc lập ([P-016](../problem-backlog.md#p-016)).
- **Mới:** một số job được chuyển sang Validation khi state annotation chưa Completed ([P-017](../problem-backlog.md#p-017)).
- **Mới:** Issue trên CVAT chưa được phân loại theo taxonomy thống nhất ([P-018](../problem-backlog.md#p-018)).

## Kế hoạch tiếp theo (tuần 02)

- Chốt chính thức các edge case đang áp dụng xử lý tạm và ghi vào `so-quyet-dinh.md`: drivable area ([P-001](../problem-backlog.md#p-001)), crosswalk/lane marking ([P-002](../problem-backlog.md#p-002)), night/low-light BBOX ([P-006](../problem-backlog.md#p-006)), vegetation vs sky ([P-009](../problem-backlog.md#p-009)), fence/vật thể rỗng ([P-010](../problem-backlog.md#p-010)).
- Đưa building vs wall ([P-008](../problem-backlog.md#p-008)) và boundary pole/traffic_light/traffic_sign ([P-011](../problem-backlog.md#p-011)) ra bàn để chốt, bổ sung positive/negative example vào Guideline v2.
- Làm rõ attribute `truncated` áp dụng cho BBOX so với Semantic Segmentation ([P-012](../problem-backlog.md#p-012)).
- Chuẩn hoá taxonomy `traffic sign` / `traffic_sign` trước khi dùng export downstream ([P-004](../problem-backlog.md#p-004)).
- Đưa quy trình review vào checklist thủ công cho tới khi có công cụ hỗ trợ: không để reviewer trùng annotator ([P-016](../problem-backlog.md#p-016)), không chuyển Validation khi annotation chưa Completed ([P-017](../problem-backlog.md#p-017)).
- Áp dụng taxonomy Issue thống nhất (`ANNOTATOR_ERROR`, `UNCERTAIN_CLASS`, `UNCERTAIN_BOUNDARY`, `UNCERTAIN_SCOPE`, `GUIDELINE_GAP`, `ATTRIBUTE_ERROR`, `TOOL_ERROR`, `DATA_ERROR`) khi raise Issue trên CVAT ([P-018](../problem-backlog.md#p-018)).
- Đánh giá và ưu tiên đề xuất tooling theo mức tốn thời gian/rủi ro thực tế: autosave/checkpoint + versioning ([P-007](../problem-backlog.md#p-007), [P-015](../problem-backlog.md#p-015)); Closed Boundary Fill/Smart Fill cho brush ([P-013](../problem-backlog.md#p-013)); công cụ hỗ trợ geometry ([P-014](../problem-backlog.md#p-014)); Issue management system theo taxonomy mới; LLM Guideline Assistant; Pre-label model recommendation; CVAT Configuration Assistant.
