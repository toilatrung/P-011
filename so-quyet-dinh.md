# Sổ quyết định

Ghi lại những gì đội đã chốt và lý do. Không ghi xử lý tạm trong backlog thành quyết định chính thức.

**Quyết định đã ghi thì không sửa nội dung.** Nếu đổi ý, tạo quyết định mới và chuyển trạng thái quyết định cũ thành *Bị thay bởi QĐ-xxx*.

## Danh sách

| Mã | Quyết định | Ngày | Xuất phát từ | Trạng thái |
|---|---|---|---|---|
| [QĐ-001](#qđ-001) | Shape type cố định theo loại annotation; tách task theo loại shape | 20/09/2026 | Họp tuần 01 | Hiệu lực |
| [QĐ-002](#qđ-002) | Quy tắc `area/drivable` / `area/alternative` theo hướng ego | 20/09/2026 | [P-001](problem-backlog.md#p-001) | Hiệu lực |
| [QĐ-003](#qđ-003) | Lane marking dạng vạch đứt: mỗi đoạn nhìn thấy là một polyline riêng | 20/09/2026 | [P-002](problem-backlog.md#p-002) | Hiệu lực |
| [QĐ-004](#qđ-004) | Crosswalk: hai polyline theo hai mép dọc mỗi vạch | 20/09/2026 | [P-002](problem-backlog.md#p-002) | Hiệu lực |
| [QĐ-005](#qđ-005) | Attribute chỉ dùng theo cấu hình task/batch chính thức | 20/09/2026 | Họp tuần 01 | Hiệu lực |
| [QĐ-006](#qđ-006) | Quy trình QC: self-check → lead review → cross-review → rework | 20/09/2026 | Họp tuần 01 | Hiệu lực |
| [QĐ-007](#qđ-007) | Issue phân loại tối thiểu: Annotator Error / Guideline Gap | 20/09/2026 | Họp tuần 01 | Hiệu lực |

**Trạng thái:** Hiệu lực · Bị thay bởi QĐ-xxx · Huỷ (ghi lý do)

## Việc cần chốt

- [x] Phạm vi polygon drivable area — [P-001](problem-backlog.md#p-001) → chốt tại [QĐ-002](#qđ-002).
- [x] Cách biểu diễn crosswalk/lane marking và quy tắc nối qua khoảng trống — [P-002](problem-backlog.md#p-002) → chốt tại [QĐ-003](#qđ-003), [QĐ-004](#qđ-004).
- [ ] Tên class chuẩn cho `traffic sign` / `traffic_sign` — [P-004](problem-backlog.md#p-004).

---

## QĐ-001

**Shape type cố định theo loại annotation; tách task theo loại shape**

- **Ngày:** 20/09/2026
- **Người tham gia:** @toilatrung (chốt), Trần Đức Thọ, @Vietanhhhhhh2003
- **Xuất phát từ:** Họp tuần 01
- **Bối cảnh:** Annotator từng có thể tự chọn Polygon hoặc Polyline tuỳ ý khi annotate area/lane, gây rủi ro không nhất quán khi review; đồng thời shape của Task 130 (BBox + Polygon + Polyline) và Task 184 (Semantic Segmentation) cần tách biệt rõ theo loại task.
- **Các phương án đã cân nhắc:**
  1. *Annotator tự chọn shape thuận tiện* — nhanh hơn nhưng mất consistency. Loại.
  2. *Cố định shape theo semantic type* — dễ review/evaluate. **Chọn.**
- **Quyết định:** Object instance → Bounding Box. `area/drivable`, `area/alternative` → Polygon. Lane marking / crosswalk → Polyline. Không dùng Polygon và Polyline thay thế lẫn nhau. Task BBox + Polygon + Polyline (hiện tại: Task 130) và task Semantic Segmentation (hiện tại: Task 184) là hai loại task tách biệt, không trộn shape type giữa hai loại.
- **Việc phải làm theo:**
  - [ ] Rà lại job cũ (nếu có) đang dùng sai shape type và điều chỉnh (@TODO)
- **Trạng thái:** Hiệu lực

## QĐ-002

**Quy tắc `area/drivable` / `area/alternative` theo hướng ego**

- **Ngày:** 20/09/2026
- **Người tham gia:** @toilatrung (chốt), Trần Đức Thọ, Nguyễn Đức Hà, @duy12345-6789
- **Xuất phát từ:** [P-001](problem-backlog.md#p-001)
- **Bối cảnh:** P-001 cho thấy chưa rõ `area/drivable` chỉ tính lane ego đang di chuyển hay toàn bộ mặt đường quan sát được, dẫn tới cách annotate khác nhau giữa các thành viên ở job 1370 và task 184.
- **Các phương án đã cân nhắc:**
  1. *Chỉ lane chính giữa xe ego* — đơn giản nhưng không xử lý tốt chuyển lane. Loại.
  2. *Xác định theo khả năng di chuyển thực tế của ego và hướng traffic* — bao quát edge case tốt hơn. **Chọn.**
- **Quyết định:**
  - Nếu xác định được hướng ego: lane ego đang di chuyển → `area/drivable`; lane còn lại → `area/alternative`.
  - Nếu ego đang chuyển lane/lệch lane: vùng/lane ego thực tế đang sử dụng vẫn được tính `drivable`.
  - Nếu không xác định rõ hướng ego: các lane cùng chiều quan sát được → `area/drivable`; lane đối diện → `area/alternative`.
- **Việc phải làm theo:**
  - [ ] Cập nhật trạng thái P-001 trong `problem-backlog.md` thành ✅ Đã chốt → QĐ-002 (@toilatrung)
  - [ ] Rà lại các frame/job đã annotate trước khi có rule này để kiểm tra tính nhất quán (@annotator)
- **Trạng thái:** Hiệu lực

## QĐ-003

**Lane marking dạng vạch đứt: mỗi đoạn nhìn thấy là một polyline riêng**

- **Ngày:** 20/09/2026
- **Người tham gia:** @toilatrung (chốt), Trần Đức Thọ, @duy12345-6789
- **Xuất phát từ:** [P-002](problem-backlog.md#p-002)
- **Bối cảnh:** P-002 cho thấy chưa rõ có nên nối các đoạn vạch đứt thành một polyline liên tục hay giữ riêng từng đoạn nhìn thấy.
- **Các phương án đã cân nhắc:**
  1. *Nối tất cả đoạn đứt thành một polyline* — ít thao tác nhưng tạo geometry không tồn tại trên ảnh. Loại.
  2. *Mỗi đoạn vạch đứt là một polyline riêng* — phản ánh đúng visual evidence. **Chọn.**
- **Quyết định:** Vạch liền và vạch đứt đều annotate nếu thuộc scope. Mỗi đoạn vạch đứt nhìn thấy là một polyline riêng. Không nối qua khoảng trống không có marking. Polyline kết thúc tại nơi không còn đủ visual evidence.
- **Việc phải làm theo:**
  - [ ] Rà lại lane marking đã annotate trong Task 130 để kiểm tra có đoạn bị nối sai qua khoảng trống hay không (@annotator)
- **Trạng thái:** Hiệu lực

## QĐ-004

**Crosswalk: hai polyline theo hai mép dọc mỗi vạch**

- **Ngày:** 20/09/2026
- **Người tham gia:** @toilatrung (chốt), @Vietanhhhhhh2003, @duy12345-6789
- **Xuất phát từ:** [P-002](problem-backlog.md#p-002)
- **Bối cảnh:** P-002 cho thấy chưa rõ crosswalk cần biểu diễn bằng polygon bao toàn vùng hay polyline theo từng vạch riêng.
- **Các phương án đã cân nhắc:**
  1. *Polygon toàn vùng crosswalk* — nhanh nhưng không đúng convention đã thống nhất. Loại.
  2. *Một polyline giữa mỗi vạch* — đơn giản nhưng mất boundary hai bên. Loại.
  3. *Hai polyline theo hai mép dọc mỗi vạch* — mô tả đúng cấu trúc vạch. **Chọn.**
- **Quyết định:** Không dùng polygon bao toàn bộ zebra crossing. Crosswalk gồm nhiều vạch riêng. Mỗi vạch được annotate bằng 2 polyline theo hai mép dọc của vạch. Không nối các vạch khác nhau lại với nhau.
- **Việc phải làm theo:**
  - [ ] Cập nhật trạng thái P-002 trong `problem-backlog.md` thành ✅ Đã chốt → QĐ-003, QĐ-004 (@toilatrung)
  - [ ] Rà lại crosswalk đã annotate để kiểm tra đúng convention 2 polyline/vạch (@annotator)
- **Trạng thái:** Hiệu lực

## QĐ-005

**Attribute chỉ dùng theo cấu hình task/batch chính thức**

- **Ngày:** 20/09/2026
- **Người tham gia:** @toilatrung (chốt), Trần Đức Thọ, @duy12345-6789
- **Xuất phát từ:** Họp tuần 01
- **Bối cảnh:** Chưa rõ annotator có được tự bổ sung attribute ngoài schema cấu hình sẵn hay không, dẫn tới rủi ro schema khác nhau giữa các job/batch.
- **Các phương án đã cân nhắc:**
  1. *Annotator tự bổ sung attribute thấy cần thiết* — linh hoạt nhưng schema giữa người làm sẽ khác nhau. Loại.
  2. *Schema do admin/lead kiểm soát tập trung* — **Chọn.**
- **Quyết định:** Chỉ sử dụng attribute được cấu hình chính thức trong task/batch. Không tự thêm attribute. Nếu tài liệu chung có attribute nhưng task hiện tại không có thì không tự sửa schema.
- **Việc phải làm theo:**
  - [ ] Rà soát schema attribute hiện tại của từng task, đảm bảo khớp cấu hình chính thức (@TODO)
- **Trạng thái:** Hiệu lực

## QĐ-006

**Quy trình QC: self-check → lead review → cross-review → rework**

- **Ngày:** 20/09/2026
- **Người tham gia:** @toilatrung (chốt), Trần Đức Thọ, @Vietanhhhhhh2003, Nguyễn Đức Hà, @duy12345-6789
- **Xuất phát từ:** Họp tuần 01
- **Bối cảnh:** Cần quy trình QC rõ ràng để tránh annotator submit thẳng không qua kiểm tra, đồng thời tránh lead review trở thành bottleneck duy nhất. Quy trình này đã được áp dụng thực tế cho Semantic Segmentation trong tuần 01 (xem `nhat-ky-tuan/tuan-01.md`).
- **Các phương án đã cân nhắc:**
  1. *Annotator xong là submit luôn* — nhanh nhưng lỗi lọt nhiều. Loại.
  2. *Lead review duy nhất* — kiểm soát tốt hơn nhưng bottleneck. Loại.
  3. *Self-check + lead review + cross-review* — nhiều tầng kiểm tra và chia tải. **Chọn.**
- **Quyết định:** Workflow chính thức: `Annotation → Self-check → Lead Review → Cross-review → Issue/Rework → Review lại → Acceptance`. Annotator phải self-check. Lead review trước, sau đó review chéo. Không review job do chính mình annotate.
- **Việc phải làm theo:**
  - [ ] Áp dụng đồng bộ quy trình này cho task BBOX (Task 130) ở tuần tiếp theo nếu chưa áp dụng đầy đủ (@lead)
  - [ ] Rà soát để đảm bảo reviewer không trùng annotator — liên hệ [P-016](problem-backlog.md#p-016) (@lead)
- **Trạng thái:** Hiệu lực

## QĐ-007

**Issue phân loại tối thiểu: Annotator Error / Guideline Gap**

- **Ngày:** 20/09/2026
- **Người tham gia:** @toilatrung (chốt), Trần Đức Thọ, @Vietanhhhhhh2003, Nguyễn Đức Hà, @duy12345-6789
- **Xuất phát từ:** Họp tuần 01
- **Bối cảnh:** Issue trên CVAT chưa phân biệt rõ lỗi do annotator hay do guideline thiếu/mơ hồ, gây khó xác định hướng xử lý đúng (sửa annotation hay sửa guideline). Taxonomy Issue đầy đủ hơn vẫn đang mở tại [P-018](problem-backlog.md#p-018).
- **Các phương án đã cân nhắc:** Không có đầy đủ decision history trong repo về các phương án từng cân nhắc cho phân loại tối thiểu này; log lại phương án đã chốt.
- **Quyết định:** Mỗi Issue trên CVAT phải được gắn tối thiểu một trong hai loại: `Annotator Error` (lỗi do annotator thao tác) hoặc `Guideline Gap` (lỗi do guideline thiếu/mơ hồ). Đây là bước phân loại tối thiểu bắt buộc, độc lập với việc mở rộng taxonomy đầy đủ hơn đang bàn ở P-018.
- **Việc phải làm theo:**
  - [ ] Áp dụng gắn nhãn Annotator Error / Guideline Gap cho Issue mới trên CVAT (@reviewer)
  - [ ] Tiếp tục đánh giá taxonomy đầy đủ hơn theo đề xuất tại [P-018](problem-backlog.md#p-018) (@lead)
- **Trạng thái:** Hiệu lực

---

## Mẫu để copy

```markdown
## QĐ-NNN

**Quyết định trong một dòng**

- **Ngày:** dd/mm/yyyy
- **Người tham gia:** @ (chốt), @, @
- **Xuất phát từ:** [P-NNN](problem-backlog.md#p-nnn) | Họp tuần NN | …
- **Bối cảnh:** vì sao phải quyết định
- **Các phương án đã cân nhắc:**
  1. *Phương án* — ưu / nhược. Loại hoặc **Chọn.**
  2. *Phương án* — ưu / nhược. Loại hoặc **Chọn.**
- **Quyết định:** đủ rõ để người không dự họp vẫn làm đúng
- **Việc phải làm theo:**
  - [ ] việc (@người phụ trách)
- **Trạng thái:** Hiệu lực
```

Nhớ thêm một dòng vào bảng **Danh sách** ở đầu file và đóng mục P-xxx tương ứng trong backlog.
