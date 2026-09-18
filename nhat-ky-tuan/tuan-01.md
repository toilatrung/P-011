# Nhật ký tuần 01 · 15/09 – 21/09/2026

**Lead chính:** Trịnh Quang Trung ([@toilatrung](https://github.com/toilatrung)) — phụ trách phân công task SEGMENTATION

**Lead phụ:** Trần Đức Thọ (GitHub chưa cung cấp) — phụ trách phân công các task BBOX

**Dữ liệu / task CVAT:** [Task 130 — W1-BBOX-G2-T1](https://cvat.note.transformerlabs.ai/tasks/130) · [Task 184 — W1-SEG-G2-T1](https://cvat.note.transformerlabs.ai/tasks/184)

## Thành viên và phân công

| Thành viên | Vị trí | Phân công tuần này |
|---|---|---|
| Trịnh Quang Trung (2A202602096, @toilatrung) | Lead chính · Annotator · Reviewer | Phân công task SEGMENTATION; annotate và rework job 1370; review job 1586, 1587, 1589, 1591 |
| Trần Đức Thọ (2A202602324) | Lead phụ · Annotator · Reviewer | Phân công các task BBOX; annotate job 1586; review job 1370, 1376 |
| Nguyễn Xuân Việt Anh (2A202602102, @Vietanhhhhhh2003) | Annotator · Reviewer | Annotate job 1372, 1587; review job 1374 |
| Nguyễn Đức Hà (2A202602105) | Annotator · Reviewer | Annotate job 1374, 1589; review job 1372 |
| Lê Ngọc Nam (2A202602060, @duy12345-6789) | Annotator · Reviewer | Annotate job 1376, 1591; review job 1374 |

## Công việc

| # | Nội dung công việc | Annotator | Reviewer / điều phối | Hoàn thành | Ghi chú |
|---|---|---|---|---|---|
| 1 | [Job 1370](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1370) — W1-BBOX-G2-T1, G02_B001–G02_B025 | @toilatrung | Trần Đức Thọ | 🟡 Đang làm | Đang annotate; vướng [P-001](../problem-backlog.md#p-001), [P-002](../problem-backlog.md#p-002) |
| 2 | [Job 1372](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1372) — W1-BBOX-G2-T1 | @Vietanhhhhhh2003 | Nguyễn Đức Hà | 🟡 Đang làm | Chưa cập nhật tổng frame và số frame đã annotate |
| 3 | [Job 1374](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1374) — W1-BBOX-G2-T1 | Nguyễn Đức Hà | Lê Ngọc Nam | ⬜ Chưa làm | Chưa cập nhật tổng frame và số frame đã annotate |
| 4 | [Job 1376](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1376) — W1-BBOX-G2-T1 | @duy12345-6789 | Trần Đức Thọ | ⬜ Chưa làm | Chưa cập nhật tổng frame và số frame đã annotate |
| 5 | [Job 1586](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1586) — W1-SEG-G2-T1 | Trần Đức Thọ | @toilatrung | 🟡 Đang rework | Bị trả lại ở bước validation; đang sửa theo feedback |
| 6 | [Job 1587](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1587) — W1-SEG-G2-T1 | @Vietanhhhhhh2003 | @toilatrung | 🟡 Đang làm | Chưa cập nhật tổng frame và số frame đã annotate |
| 7 | [Job 1589](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1589) — W1-SEG-G2-T1 | Nguyễn Đức Hà | @toilatrung | ✅ Đã accept | acceptance completed trên CVAT |
| 8 | [Job 1591](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1591) — W1-SEG-G2-T1 | @duy12345-6789 | @toilatrung | 🟡 Đang rework | Bị trả lại ở bước validation; đang sửa theo feedback |

Mức hoàn thành: ✅ xong **và đã qua review** · 🟡 đã/đang annotate nhưng chưa xác nhận review · ⛔ bị chặn · ⬜ chưa bắt đầu hoặc chưa có cập nhật

## Tổng kết tạm thời

- Job 1589 (SEG) đã được accept.
- Jobs 1370, 1372, 1587 đang được annotate.
- Jobs 1586 và 1591 (SEG) bị trả lại ở bước validation, đang rework.
- Jobs 1374 và 1376 chưa bắt đầu.
- Chưa có số liệu thống nhất về tổng frame và số frame đã annotate để tính tỷ lệ hoàn thành chung.
- Edge case mở: [P-001](../problem-backlog.md#p-001) và [P-002](../problem-backlog.md#p-002).
- Pain point / chất lượng dữ liệu: [P-003](../problem-backlog.md#p-003), [P-004](../problem-backlog.md#p-004), [P-005](../problem-backlog.md#p-005).

## Vướng mắc

- Boundary của drivable area tại giao lộ hoặc ảnh nhiều làn còn có hai cách hiểu.
- Chưa rõ crosswalk/lane marking cần tách từng vạch hay dùng một polyline đại diện, và có được nối qua khoảng trống hay không.
- Polyline cho lane marking dài tốn nhiều thao tác thủ công.
- Export có cả `traffic sign` và `traffic_sign`; cần kiểm tra taxonomy trước khi dùng dataset cho bước sau.
- Automatic Annotation trong CVAT chưa có model khả dụng.

## Kế hoạch tiếp theo

- Trần Đức Thọ review job 1370 khi annotate xong.
- Nguyễn Đức Hà tiếp tục job 1374 và review job 1372.
- Lê Ngọc Nam bắt đầu job 1376 và review job 1374.
- Trần Đức Thọ tiếp tục job 1586 (rework) và review job 1370, 1376.
- Nguyễn Xuân Việt Anh tiếp tục job 1587.
- Lê Ngọc Nam rework job 1591 theo feedback validation.
- Trịnh Quang Trung điều phối task SEGMENTATION và review job 1586, 1587, 1589, 1591.
- Trần Đức Thọ điều phối các task BBOX.
- Chốt rule chung cho drivable area và crosswalk/lane marking, rồi ghi vào `so-quyet-dinh.md`.
- Chuẩn hoá taxonomy `traffic sign` / `traffic_sign` trước khi dùng export downstream.
- Nghiên cứu auto-annotation sau khi rule và taxonomy đã ổn định.
