@All
Tên: Nguyễn Đức Hà
GitHub: @DucHa180104
Role: Annotator

CVAT:

* Task: (Điền số Task của bạn vào đây)
* Job: 1374
* Link: https://.../jobs/1374
* Phạm vi: frame 0–24 (tổng 25 frames)

Tiến độ:

* Done: 25/25 frames (Đã hoàn thành phần Bounding Box)
* Status: Completed (phần Bounding Box) / Pending semantic layers
* Blocker:
* Chưa tiến hành annotate vạch đường (lane markings) và bầu trời (sky) theo yêu cầu do phạm vi công việc đợt này đang ưu tiên hoàn thiện Bounding Box trước hoặc cần đồng bộ lại guideline chi tiết cho các lớp semantic này.
* Tầm nhìn ban đêm (night scene) ở một số frame hạn chế, ranh giới vật cản bị nhòe bởi ánh đèn pha hắt ngược.



Edge case:

1. Frame ban đêm / Thiếu sáng (Night scene)
* Loại: LOW_VISIBILITY_OBJECTS
* Mô tả: Xe ở xa trong điều kiện đêm tối, ánh sáng đèn pha gây lóa khiến việc định hình chính xác biên độ gặp khó khăn.
* Xử lý tạm: Bounding box bám sát vùng sáng rõ nhất có thể, ghi chú lại trạng thái cần review.



Pain point:

* Việc kéo thả box thủ công với các xe ở xa trong điều kiện thiếu sáng mất nhiều thời gian căn chỉnh.
* Chưa cần tool / đề xuất nghiên cứu auto-annotation tạm thời.

---

*(Repo liên kết dự án của bạn: [https://github.com/AI20K-Build-Phase-Cohort-4A/P-011.git](https://github.com/AI20K-Build-Phase-Cohort-4A/P-011.git))*