# Đội P-011 — Cohort 4A

Repo làm việc của đội P-011 cho các bài gán nhãn CVAT. Repo lưu phân công và tiến độ theo tuần,
edge case chưa rõ guideline, các quyết định đã chốt, và source code công cụ hỗ trợ nếu đội phát
triển tool.

## Thành viên

| Thành viên | Mã học viên | GitHub | Vị trí hiện tại |
|---|---|---|---|
| Trần Đức Thọ | 02324 | Chưa cung cấp | Lead · Annotator · Reviewer |
| Trịnh Quang Trung | 02096 | [@toilatrung](https://github.com/toilatrung) | Annotator · Reviewer |
| Nguyễn Xuân Việt Anh | 02102 | [@Vietanhhhhhh2003](https://github.com/Vietanhhhhhh2003) | Annotator · Reviewer |
| Nguyễn Đức Hà | 02105 | Chưa cung cấp | Annotator · Reviewer |
| Lê Ngọc Nam | 02060 | [@duy12345-6789](https://github.com/duy12345-6789) | Annotator · Reviewer |

> Reviewer không review job do chính mình gán.

## Dữ liệu đang thực hiện

- [Task 130 — W1-BBOX-G2-T1](https://cvat.note.transformerlabs.ai/tasks/130): jobs 1370, 1372, 1374, 1376.
- [Task 184 — W1-SEG-G2-T1](https://cvat.note.transformerlabs.ai/tasks/184): job 1586.
- Chi tiết tiến độ: [`nhat-ky-tuan/tuan-01.md`](nhat-ky-tuan/tuan-01.md).
- Các trường hợp chưa rõ và pain point: [`problem-backlog.md`](problem-backlog.md).
- Quyết định đã thống nhất: [`so-quyet-dinh.md`](so-quyet-dinh.md).

## Phân công annotate và review

| Tuần bắt đầu | Người annotate | GitHub handle | CVAT Task | CVAT Job | Link Job | Phạm vi annotate | Trạng thái annotate | Reviewer |
|---|---|---|---:|---:|---|---|---|---|
| 14/09/2026 | Trịnh Quang Trung | [@toilatrung](https://github.com/toilatrung) | 130 | 1370 | [Mở job](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1370) | W1-BBOX-G2-T1 | **Đang rework** | Nguyễn Xuân Việt Anh |
| 14/09/2026 | Nguyễn Xuân Việt Anh | [@Vietanhhhhhh2003](https://github.com/Vietanhhhhhh2003) | 130 | 1372 | [Mở job](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1372) | W1-BBOX-G2-T1 | Đang làm | Nguyễn Đức Hà |
| 14/09/2026 | Nguyễn Đức Hà | Chưa cung cấp | 130 | 1374 | [Mở job](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1374) | W1-BBOX-G2-T1 | Chưa làm | Lê Ngọc Nam |
| 14/09/2026 | Lê Ngọc Nam | [@duy12345-6789](https://github.com/duy12345-6789) | 130 | 1376 | [Mở job](https://cvat.note.transformerlabs.ai/tasks/130/jobs/1376) | W1-BBOX-G2-T1 | Chưa làm | Trần Đức Thọ |
| 14/09/2026 | Trần Đức Thọ | Chưa cung cấp | 184 | 1586 | [Mở job](https://cvat.note.transformerlabs.ai/tasks/184/jobs/1586) | W1-SEG-G2-T1 | Đang làm | Trịnh Quang Trung |

## Cấu trúc repo

| Đường dẫn | Dùng để | Cập nhật khi nào |
|---|---|---|
| [`nhat-ky-tuan/`](nhat-ky-tuan/) | Thành viên, phân công và tiến độ | Đầu tuần phân công, cuối tuần chốt |
| [`problem-backlog.md`](problem-backlog.md) | Edge case và pain point, kèm link CVAT | Ngay khi gặp |
| [`so-quyet-dinh.md`](so-quyet-dinh.md) | Quyết định của đội và lý do | Mỗi lần chốt một vấn đề |
| [`source-tool/`](source-tool/) | Công cụ đội tự viết để giảm thao tác lặp | Khi đội quyết định làm tool |

## Quy ước

- Mã backlog và quyết định dùng dạng `P-001`, `QĐ-001`, đánh số tăng dần.
- Nhắc người bằng GitHub handle khi đã có; nếu chưa có thì ghi đầy đủ họ tên.
- Link CVAT trỏ tới đúng job và thêm `?frame=<n>` khi xác định được frame có vấn đề.
- Không tự chốt edge case khi guideline chưa rõ; ghi backlog và chờ Lead/reviewer thống nhất.
