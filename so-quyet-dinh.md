# Sổ quyết định

Ghi lại những gì đội đã chốt và lý do. Không ghi xử lý tạm trong backlog thành quyết định chính thức.

**Quyết định đã ghi thì không sửa nội dung.** Nếu đổi ý, tạo quyết định mới và chuyển trạng thái quyết định cũ thành *Bị thay bởi QĐ-xxx*.

## Danh sách

| Mã | Quyết định | Ngày | Xuất phát từ | Trạng thái |
|---|---|---|---|---|
| — | Chưa có quyết định chính thức | — | [P-001, P-002 đang bàn](problem-backlog.md) | — |

**Trạng thái:** Hiệu lực · Bị thay bởi QĐ-xxx · Huỷ (ghi lý do)

## Việc cần chốt

- [ ] Phạm vi polygon drivable area — [P-001](problem-backlog.md#p-001).
- [ ] Cách biểu diễn crosswalk/lane marking và quy tắc nối qua khoảng trống — [P-002](problem-backlog.md#p-002).
- [ ] Tên class chuẩn cho `traffic sign` / `traffic_sign` — [P-004](problem-backlog.md#p-004).

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
