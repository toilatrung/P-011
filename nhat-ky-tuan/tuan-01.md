# Nhật ký tuần 01 · 15/09 – 21/09/2026

_Cập nhật lần 2 trong tuần — 19/09/2026, tổng hợp từ báo cáo tiến độ team._

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
| 1 | [Job 1370](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1370) — W1-BBOX-G2-T1, G02_B001–G02_B025 | @toilatrung | Trần Đức Thọ | 🟡 Annotate xong 25/25 | Annotate xong, CVAT hiện `Annotation / In Progress`; chờ review BBOX; vướng [P-001](../problem-backlog.md#p-001), [P-002](../problem-backlog.md#p-002) |
| 2 | [Job 1372](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1372) — W1-BBOX-G2-T1 | @Vietanhhhhhh2003 | Nguyễn Đức Hà | 🟡 Annotate xong 25/25 | Chờ review BBOX; vướng [P-006](../problem-backlog.md#p-006) (frame ban đêm) |
| 3 | [Job 1374](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1374) — W1-BBOX-G2-T1 | Nguyễn Đức Hà | Lê Ngọc Nam | 🟡 Annotate xong 25/25 | Chờ review BBOX; vướng [P-006](../problem-backlog.md#p-006) (frame ban đêm, xem `?frame=50`) |
| 4 | [Job 1376](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1376) — W1-BBOX-G2-T1 | @duy12345-6789 | Trần Đức Thọ | ⬜ Chưa có cập nhật | Chưa nhận được báo cáo tiến độ từ Lê Ngọc Nam cho job này |
| 5 | [Job 1586](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1586) — W1-SEG-G2-T1 | Trần Đức Thọ | @toilatrung | 🟡 Rework | Team Lead review: REWORK, còn nhiều lỗi cần khắc phục; chưa có kết quả review cuối |
| 6 | [Job 1587](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1587) — W1-SEG-G2-T1 | @Vietanhhhhhh2003 | @toilatrung | 🟡 Rework | Annotate xong 25/25; Team Lead review: REWORK, đang sửa, chưa có kết quả review cuối |
| 7 | [Job 1589](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1589) — W1-SEG-G2-T1 | Nguyễn Đức Hà | @toilatrung | ✅ PASS | Annotate xong 25/25, acceptance completed; Team Lead review: PASS |
| 8 | [Job 1591](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1591) — W1-SEG-G2-T1 | @duy12345-6789 | @toilatrung | ✅ PASS | Annotate xong 25/25; Team Lead đã validate trực tiếp trên CVAT do chưa liên hệ được Lê Ngọc Nam; Team Lead review: PASS |

Mức hoàn thành: ✅ xong **và đã qua review** · 🟡 đã/đang annotate nhưng chưa xác nhận review · ⛔ bị chặn · ⬜ chưa bắt đầu hoặc chưa có cập nhật

## Tổng kết tạm thời (cập nhật lần 2 — 19/09)

- BBOX (Task 130): job 1370, 1372, 1374 đã annotate xong 25/25 frame, đang chờ review BBOX; job 1376 chưa có cập nhật.
- SEG (Task 184): 4/4 job đã annotate xong 25/25 frame và đã qua review của Team Lead — job 1589 (Hà) và 1591 (Nam) **PASS**; job 1586 (Thọ) và 1587 (Việt Anh) **REWORK**, đang chờ resubmit để review vòng cuối.
- Tổng theo Semantic Segmentation review: PASS 2/4, REWORK/Pending 2/4.
- Chưa có số liệu thống nhất về tổng frame và số frame đã annotate cho job 1376 để tính tỷ lệ hoàn thành chung của cả task BBOX.
- Edge case mở: [P-001](../problem-backlog.md#p-001), [P-002](../problem-backlog.md#p-002), [P-006](../problem-backlog.md#p-006) (mới).
- Pain point / rủi ro công cụ: [P-003](../problem-backlog.md#p-003), [P-004](../problem-backlog.md#p-004), [P-005](../problem-backlog.md#p-005), [P-007](../problem-backlog.md#p-007) (mới).

## Vướng mắc

- Boundary của drivable area tại giao lộ hoặc ảnh nhiều làn còn có hai cách hiểu ([P-001](../problem-backlog.md#p-001)).
- Chưa rõ crosswalk/lane marking cần tách từng vạch hay dùng một polyline đại diện, và có được nối qua khoảng trống hay không ([P-002](../problem-backlog.md#p-002)).
- Polyline cho lane marking và polygon mặt đường dài tốn nhiều thao tác thủ công, kể cả căn boundary giữa polygon và polyline lane marking ([P-003](../problem-backlog.md#p-003)).
- Export có cả `traffic sign` và `traffic_sign`; cần kiểm tra taxonomy trước khi dùng dataset cho bước sau ([P-004](../problem-backlog.md#p-004)).
- Automatic Annotation trong CVAT chưa có model khả dụng ([P-005](../problem-backlog.md#p-005)).
- **Mới:** frame ban đêm/thiếu sáng khó xác định boundary của xe ở xa hoặc xe tối màu, ảnh hưởng consistency của BBOX ([P-006](../problem-backlog.md#p-006)).
- **Mới:** CVAT/server từng mất kết nối trong lúc labeling, có nguy cơ mất annotation chưa persist mà không xác định được rõ phần nào đã lưu ([P-007](../problem-backlog.md#p-007)).

## Kế hoạch tiếp theo

- Nguyễn Xuân Việt Anh tiếp tục rework Semantic Segmentation job 1587 theo feedback.
- Trần Đức Thọ tiếp tục rework Semantic Segmentation job 1586 theo feedback.
- Trịnh Quang Trung chờ resubmit job 1586, 1587 để review vòng cuối; review BBOX job 1370, 1372, 1374 khi có xác nhận.
- Trần Đức Thọ điều phối và review các job BBOX còn lại (1370, 1376); cập nhật tiến độ job 1376 (Lê Ngọc Nam).
- Chốt rule chung cho drivable area và crosswalk/lane marking, rồi ghi vào `so-quyet-dinh.md`.
- Chuẩn hoá taxonomy `traffic sign` / `traffic_sign` trước khi dùng export downstream.
- Tiếp tục hoàn thiện Guideline v2: bổ sung rule cho night/low-light BBOX kèm ví dụ minh hoạ, và các lỗi lặp lại phát hiện qua review (boundary, semantic class, scope).
- Đánh giá đề xuất tooling: autosave/checkpoint theo frame và versioning cho annotation trong trạng thái In Progress ([P-007](../problem-backlog.md#p-007)); Issue management/knowledge base cho guideline; nghiên cứu pre-label/semi-auto annotation sau khi rule và taxonomy ổn định ([P-003](../problem-backlog.md#p-003), [P-005](../problem-backlog.md#p-005)).
