# Bài 2 — Interactive Rebase và làm sạch lịch sử

**Sinh viên:** NguyễnDăngDương
**Lớp:** CNTT2 — IT209 — Session 05

## Lịch sử trước rebase

Tạo module `auth.js` qua ba commit (khởi tạo, sửa typo, thêm tiện ích), sau đó tạo commit riêng chứa `temp.txt`. Rebase bốn commit gần nhất:

```bash
git log --oneline
git rebase -i HEAD~4
```

Trong danh sách tương tác, giữ commit đầu ở `pick`, đổi hai commit tiếp theo thành `squash`, và đổi commit cuối thành `drop`. Khi Git mở trình soạn thông điệp, đặt nội dung cuối là:

```text
feat: hoan thien module authentication
```

## Kiểm tra

```bash
git log --oneline
git status
```

Kết quả giữ lại commit tính năng đã gộp; `temp.txt` không còn trong working tree và các thông điệp thử nghiệm không còn xuất hiện ở lịch sử nhánh. Interactive rebase viết lại hash các commit cục bộ; không chạy trên commit đã chia sẻ với người khác nếu chưa phối hợp.
