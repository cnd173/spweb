# spweb — trang web Singularity Pencil

Trang tĩnh, **GitHub Pages tự build bằng Jekyll**. Không cần cài gì ở máy để đăng bài.

- Địa chỉ: <https://cnd173.github.io/spweb/>
- Nguồn thương hiệu (màu, chữ, câu chữ đã duyệt): repo `sp`, thư mục `docs/brand/`.

## Trạng thái: CHẶN ĐÁNH CHỈ MỤC

Repo public, trang xem được, nhưng **cố ý không cho công cụ tìm kiếm đánh chỉ mục** — phần mềm chưa
phát hành và tên gọi còn ở trạng thái tạm. Chặn nằm ở **hai** chỗ, phải gỡ **cả hai** cùng lúc:

1. `robots.txt` → xoá dòng `Disallow: /` (để lại `User-agent: *`).
2. `_config.yml` → `noindex: true` → đổi thành `false` hoặc xoá hẳn.

Chỉ gỡ một chỗ là hớ: `robots.txt` xin bot đừng bò vào, còn thẻ `noindex` mới thật sự chặn trang đã
bị người khác dẫn link.

## Đăng bài

Thả **đúng một file** vào `_posts/` là xong — trang chủ, trang `/writing/` và `/feed.xml` tự cập nhật.
Không phải sửa index bằng tay.

Tên file bắt buộc: `_posts/YYYY-MM-DD-ten-khong-dau.md`

```markdown
---
layout: post
title: Tiêu đề bài
description: Một câu tóm tắt, hiện ở danh sách bài.
date: 2026-08-25 09:00:00 +0700
tags: [ghi-chép]
---

Nội dung markdown.
```

- `date` phải khớp ngày trong tên file. Bài có ngày **tương lai** sẽ không hiện (Jekyll ẩn cho tới ngày đó).
- Đường dẫn bài: `/writing/ten-khong-dau/` (đặt ở `permalink` trong `_config.yml`).

## Nối tên miền riêng (sau này)

1. Thêm file `CNAME` ở gốc repo, nội dung là tên miền (một dòng, ví dụ `singularitypencil.com`).
2. `_config.yml`: `baseurl: ""` và `url: https://ten-mien-cua-ban`.
3. Trỏ DNS theo hướng dẫn GitHub Pages, bật *Enforce HTTPS* trong Settings → Pages.

Bước 2 là bước dễ quên nhất — bỏ qua thì CSS và mọi liên kết nội bộ vẫn trỏ về `/spweb/` và trang sẽ
trơ ra không có style.

## Cấu trúc

```
_config.yml          cấu hình + bộ chuỗi thương hiệu đã duyệt
_layouts/            default (khung trang) · post (bài viết)
_posts/              bài viết — chỗ duy nhất đường tự động ghi vào
assets/css/style.css toàn bộ CSS, màu chép từ sp/docs/brand/tokens.json
index.html           trang chủ
writing/             danh sách bài
about/               giới thiệu
robots.txt           chặn đánh chỉ mục (xem trên)
```

## Danh sách chờ (nút "Đăng ký dùng thử sớm")

Trang tĩnh không có backend, nên form gửi thẳng sang **Google Forms** — dữ liệu đổ vào Sheet của chủ
sở hữu, không qua bên thứ ba nào. Người điền không thấy Google Form: giao diện là của trang này.

**Cố ý không gọi là "Dùng thử".** Chưa có gì để thử. Một cái nút hứa bản dùng thử rồi mở ra form
"sẽ liên hệ sau" là danh sách chờ đội lốt, và nó đốt đúng thứ duy nhất một sản phẩm chưa ra mắt đang
có. Cùng cái form ấy, gọi đúng tên, vẫn có người điền.

### Bật lên

1. Tạo Google Form với **đúng hai câu hỏi**, cả hai để kiểu **Trả lời ngắn** (short answer):
   - `Email`
   - `Bạn đang làm gì`

   Phải là *Trả lời ngắn*, đừng dùng trắc nghiệm: trắc nghiệm chỉ nhận đúng các phương án đã khai,
   lệch một chữ là Google **lặng lẽ vứt** câu trả lời đi.

2. Lấy ba giá trị:
   - **action** — mở form ở chế độ xem trước, xem mã nguồn trang, tìm `action="…/formResponse"`.
     Chú ý đuôi là `formResponse`, **không phải** `viewform`.
   - **entry_email**, **entry_role** — trong cùng mã nguồn đó, mỗi câu hỏi có một `entry.NNNNNNNNN`.

3. Điền vào `_config.yml` mục `waitlist`, đổi `enabled` thành `true`, commit và đẩy lên.

`enabled: false` thì nút ở trang chủ **không hiện** và `/try/` báo "chưa mở đăng ký" — cố ý: thà
không có nút còn hơn có một cái nút dẫn tới form gửi vào hư không.

### Một điều phải biết về thông báo "Đã ghi nhận"

Google Forms không cho trang khác đọc phản hồi (CORS), nên trình duyệt gửi ở chế độ `no-cors`:
`fetch` chỉ ngã khi **đứt mạng thật**, còn Google có nhận hay không thì trang này không biết được.
Nghĩa là dòng "Đã ghi nhận" là **lạc quan**, không phải xác nhận.

Không có cách nào vòng qua chuyện này với trang tĩnh. Cách sống chung: **đối chiếu Sheet** sau vài
lượt đăng ký đầu tiên. Sai `entry.NNN` là hỏng đúng kiểu này — người dùng thấy "đã ghi nhận", Sheet
trống trơn, không ai báo cho ai cả.
