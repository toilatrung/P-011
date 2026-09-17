# Nhật ký tuần 01 · 15/09 – 21/09/2026

**Lead tuần này:** Trần Đức Thọ (GitHub chưa cung cấp)

**Dữ liệu / task CVAT:** [Task 130 — W1-BBOX-G2-T1](https://cvat.note.transformerlabs.ai/tasks/130) · [Task 184 — W1-SEG-G2-T1](https://cvat.note.transformerlabs.ai/tasks/184)

## Thành viên và phân công

| Thành viên | Vị trí | Phân công tuần này |
|---|---|---|
| Trần Đức Thọ (02324) | Lead · Annotator · Reviewer | Điều phối task 130; annotate job 1586; kiểm tra và đổi người nếu annotator task 130 bận |
| Trịnh Quang Trung (02096, @toilatrung) | Annotator · Reviewer | Annotate job 1370; kiểm tra tiến độ jobs 1586, 1591 |
| Nguyễn Xuân Việt Anh (02102, @Vietanhhhhhh2003) | Annotator | Annotate job 1372 |
| Nguyễn Đức Hà (02105) | Annotator | Annotate job 1374 |
| Lê Ngọc Nam (02060, @duy12345-6789) | Annotator | Annotate jobs 1376, 1591 |

## Công việc

| # | Nội dung công việc | Annotator | Reviewer / điều phối | Hoàn thành | Ghi chú |
|---|---|---|---|---|---|
| 1 | [Job 1370](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1370) — W1-BBOX-G2-T1, G02_B001–G02_B025 | @toilatrung | Trần Đức Thọ | 🟡 100% annotate | 25/25 ảnh, 151 annotations; đang self-QC / chờ review; vướng [P-001](../problem-backlog.md#p-001), [P-002](../problem-backlog.md#p-002) |
| 2 | [Job 1372](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1372) — W1-BBOX-G2-T1 | @Vietanhhhhhh2003 | Trần Đức Thọ | 🟡 100% annotate | Báo cáo 25/25 frame, trạng thái Done, không blocker; chưa có xác nhận đã qua review |
| 3 | [Job 1374](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1374) — W1-BBOX-G2-T1 | Nguyễn Đức Hà | Trần Đức Thọ | ⬜ 0% được báo cáo | Nhắc lần cuối sau 24 giờ chưa bắt đầu; Lead cần kiểm tra và đổi người nếu bận |
| 4 | [Job 1376](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1376) — W1-BBOX-G2-T1 | @duy12345-6789 | Trần Đức Thọ | 🟡 60% được báo cáo | Báo 15/25 frame nhưng đồng thời ghi “Done”; link kèm báo cáo lại trỏ job 1591 — cần xác nhận số liệu |
| 5 | [Job 1586](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1586) — W1-SEG-G2-T1 | Trần Đức Thọ | @toilatrung | ⬜ 0% được báo cáo | Nhắc lần cuối sau 24 giờ chưa bắt đầu; reviewer cần kiểm tra và đổi người nếu bận |
| 6 | [Job 1591](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1591) — W1-SEG-G2-T1 | @duy12345-6789 | @toilatrung | ⬜ 0% được báo cáo | Nhắc lần cuối sau 24 giờ chưa bắt đầu; cần xác nhận liệu số liệu 15/25 có thực ra thuộc job này |

Mức hoàn thành: ✅ xong **và đã qua review** · 🟡 đã/đang annotate nhưng chưa xác nhận review · ⛔ bị chặn · ⬜ chưa bắt đầu hoặc chưa có cập nhật

## Tổng kết tạm thời

- Đã có báo cáo hoàn thành ít nhất 65 frame: job 1370 (25), job 1372 (25), và 15 frame đang cần xác nhận thuộc job 1376 hay 1591.
- Chưa có blocker kỹ thuật được báo cáo cho jobs 1372 và 1376.
- Job 1370 đã annotate đủ 25/25 ảnh, đang self-QC / chờ review.
- Edge case mở: [P-001](../problem-backlog.md#p-001) và [P-002](../problem-backlog.md#p-002).
- Pain point / chất lượng dữ liệu: [P-003](../problem-backlog.md#p-003), [P-004](../problem-backlog.md#p-004), [P-005](../problem-backlog.md#p-005).

## Vướng mắc

- Boundary của drivable area tại giao lộ hoặc ảnh nhiều làn còn có hai cách hiểu.
- Chưa rõ crosswalk/lane marking cần tách từng vạch hay dùng một polyline đại diện, và có được nối qua khoảng trống hay không.
- Polyline cho lane marking dài tốn nhiều thao tác thủ công.
- Export có cả `traffic sign` và `traffic_sign`; cần kiểm tra taxonomy trước khi dùng dataset cho bước sau.
- Automatic Annotation trong CVAT chưa có model khả dụng.
- Báo cáo của Lê Ngọc Nam có mâu thuẫn giữa job, link, số frame và trạng thái; cần xác nhận trước khi chốt tổng số.

## Kế hoạch tiếp theo

- Trần Đức Thọ kiểm tra job 1374 và điều phối lại nếu Nguyễn Đức Hà bận.
- Trịnh Quang Trung kiểm tra jobs 1586, 1591 và điều phối lại nếu annotator bận.
- Review jobs 1370, 1372 và xác nhận job tương ứng với báo cáo 15/25 của Lê Ngọc Nam.
- Chốt rule chung cho drivable area và crosswalk/lane marking, rồi ghi vào `so-quyet-dinh.md`.
- Chuẩn hoá taxonomy `traffic sign` / `traffic_sign` trước khi dùng export downstream.
- Nghiên cứu auto-annotation sau khi rule và taxonomy đã ổn định.
