---
layout: post
title: "Chúng tôi đang ở đâu, và còn thiếu gì"
date: 2026-08-26 19:50:51 +0700
description: "Bản nội bộ 0.1.0-rc1: những gì đã chạy được, những gì đang cố tình khóa lại, và vì sao chưa hứa ngày ra mắt nào."
tags: ["trạng thái", "phát hành", "tính năng"]
---
Bản đang chạy nội bộ vẫn mang số hiệu 0.1.0-rc1; bản đóng gói macOS mới nhất được dựng ngày 24/08/2026. Đây vẫn là một bản dựng thử nghiệm. Singularity Pencil chưa phát hành công khai, chưa có bản tải về cho người ngoài công ty, và chưa có bảng giá. Không có ngày ra mắt nào được chốt — nên bài này sẽ không hứa ngày nào cả.

Phần đã chạy được, ngay trong bản rc1:

Trình soạn kịch bản dựng trên Tiptap/ProseMirror, nhận đủ các loại dòng của một kịch bản phim — action, dialogue, character, parenthetical, transition — và chuyển loại dòng bằng Tab hoặc Enter thay vì phải chọn menu. Gõ tiếng Việt bằng bộ gõ (IME) hoạt động trong khung soạn thảo; bộ kiểm tự động có phủ ca gõ tiếng Việt dạng precomposed.

Nhập và xuất định dạng Fountain và FDX, để không khóa người dùng vào một định dạng riêng ngay từ đầu. Xuất PDF và DOCX cho khâu in ấn hoặc gửi đọc. Beat Board, Outline, và Character Tracker để theo cấu trúc và nhân vật song song với bản thảo.

File dự án lưu ở định dạng `.sp`, là một file ZIP chứa dữ liệu dự án — không nhúng font của bên thứ ba, chỉ lưu profile/hash/tham chiếu tới font mà máy người dùng đang có sẵn. Autosave chạy trên IndexedDB, và việc lưu là local-first bằng Yjs — nghĩa là dữ liệu ưu tiên nằm trên máy trước, không phụ thuộc một máy chủ đang chạy.

Bản desktop dựng bằng Electron, có hộp thoại mở/lưu file gốc của hệ điều hành và tự gắn đuôi `.sp`. Storyboard theo từng cảnh là một image board: mỗi cảnh có các shot card kèm title/prompt/notes/status, sắp xếp lại được, nhận ảnh import/kéo-thả/dán, và import shot thẳng từ Visualize. Giai đoạn Rewrite gồm Draft Compare (so bản thảo), Notes & Feedback, Scene Variations, AI Rewrite, và Consistency Check. Breakdown chia 15 hạng mục sản xuất và xuất được ra CSV. Node Editor trình bày cấu trúc truyện dưới dạng đồ thị.

Phần chưa xong, hoặc đang cố tình khóa lại:

Cộng tác trực tuyến — nhiều người cùng sửa một kịch bản qua mạng — đang bị khóa mặc định. Lý do đơn giản: chưa có máy chủ production để chạy nó, không phải vì tính năng chưa viết xong ở phía client. Cách chia sẻ bây giờ là lưu file `.sp` rồi gửi cho người kia.

Tên gọi "Singularity Pencil" hiện là tên tạm. Nó chưa qua thẩm định nhãn hiệu, và có thể sẽ đổi trước khi phát hành. Chúng tôi không coi đây là tên chính thức cho tới khi việc thẩm định xong.

Bản ký số/notarize cho bản desktop — bước cần để hệ điều hành không cảnh báo "ứng dụng không rõ nguồn gốc" khi mở lần đầu — chưa hoàn tất. Smoke test cho bản web hosted cũng chưa chạy. Bản iOS chưa bắt đầu — trong repo mới chỉ có tài liệu phạm vi cho Phase 3, chưa có dòng mã nào để dùng thử.

Về giấy phép: mã nguồn theo MIT. Phần AI trong sản phẩm theo mô hình BYOK (bring your own key) — người dùng tự cắm khóa API của họ, chúng tôi không cung cấp AI miễn phí hay không giới hạn kèm sản phẩm.

Chúng tôi viết bài này không phải để xin lỗi vì chưa xong, mà để ghi lại đúng một mốc: đây là những gì chạy được hôm nay, đây là những gì đang khóa và vì sao. Danh sách này sẽ còn thay đổi.

Nội dung có sự hỗ trợ của AI, được con người duyệt.
