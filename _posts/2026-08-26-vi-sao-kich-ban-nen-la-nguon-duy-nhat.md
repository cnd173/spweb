---
layout: post
title: "Vì sao kịch bản nên là nguồn duy nhất"
date: 2026-08-26 19:30:03 +0700
description: "Đoàn phim dựng đèn ngoài trời cho một cảnh đã đổi thành nội cảnh — chuyện xảy ra khi mỗi khâu sống trong một file riêng."
tags: ["kịch bản", "quy trình", "breakdown"]
---
Buổi sáng quay ở hiện trường, đạo diễn cầm bản kịch bản in tuần trước, trợ lý đạo diễn cầm lịch quay in đầu tuần, còn bảng phân cảnh nằm trong file Excel người quản lý sản xuất sửa tối qua. Ba bản, ba thời điểm. Cảnh 14 đã đổi bối cảnh từ ngoại cảnh sang nội cảnh hai ngày trước, biên kịch sửa trực tiếp trong file kịch bản rồi gửi qua nhóm chat. Bảng phân cảnh không tự cập nhật. Lịch quay không tự cập nhật. Đoàn phim dựng đèn ngoài trời cho một cảnh giờ quay trong nhà.

Đó không phải lỗi của ai cụ thể. Đó là hệ quả của việc để mỗi khâu sống trong một file riêng — kịch bản một nơi, breakdown một nơi, lịch quay một nơi — rồi tin rằng ai đó sẽ nhớ đồng bộ tay. Không ai nhớ hết được, kể cả người cẩn thận nhất.

Vấn đề nằm ở chỗ mọi thứ trong sản xuất phim đều bắt nguồn từ kịch bản. Bảng phân cảnh là kịch bản được đọc theo một cách khác — từng cảnh, từng hạng mục. Lịch quay là bảng phân cảnh được sắp theo ngày. Storyboard là kịch bản được vẽ ra. Nếu kịch bản đổi mà những thứ đó không đổi theo, chúng không còn là "một cách đọc khác của kịch bản" nữa — chúng là những bản sao đang lệch dần.

Singularity Pencil đang được xây dựng theo hướng ngược lại: giữ một bản kịch bản làm gốc, để mọi giai đoạn sau đi ra từ đó thay vì sống tách rời. Đường đi trong công cụ là Write → Rewrite → Breakdown → Visualize → Node Editor → Plan/Shoot — viết, sửa, phân tích cảnh, dựng hình, sắp xếp trên node, rồi lên kế hoạch quay. Mỗi bước đọc từ cùng một tài liệu gốc, không phải từ một bản xuất ra rồi để đó tự sống.

Breakdown, cụ thể, là một bảng phân tích cảnh theo 15 hạng mục, xuất được ra CSV để đưa sang công cụ khác nếu đoàn phim cần. Nhưng CSV đó xuất phát từ kịch bản đang mở, không phải từ một bản chụp cũ đã lỗi thời từ tuần trước.

Để giữ được điều này lâu dài, định dạng lưu file cũng phải được nghĩ kỹ, không chỉ giao diện. File `.sp` là một file ZIP, mang một document id ổn định xuyên suốt vòng đời dự án, và có các trường tuỳ chọn tương thích ngược — để khi công cụ thêm tính năng mới, file cũ vẫn mở được, và kịch bản vẫn là kịch bản đó, không phải một bản mới đội lốt bản cũ.

Chuyện gõ tiếng Việt bằng IME nghe nhỏ nhưng lại là nơi nhiều người viết kịch bản gặp trục trặc đầu tiên — bộ gõ ngắt giữa chừng, dấu rớt sai chỗ. Trình soạn thảo hỗ trợ gõ IME trực tiếp trong lúc viết, và chuyển loại dòng — hành động, thoại, tên nhân vật — bằng Tab hoặc Enter, không cần rời tay khỏi bàn phím để chọn menu.

Kịch bản viết ra không bị khoá trong một định dạng. Có thể nhập và xuất Fountain, nhập và xuất FDX, xuất PDF, xuất DOCX — để làm việc với người khác dùng công cụ khác, hoặc gửi bản đọc cuối cùng đi đâu đó. Nhưng bản gốc, bản mà breakdown và các bước sau dựa vào, vẫn chỉ là một, nằm trong `.sp`.

Singularity Pencil hiện chưa phát hành công khai. Những phần kể trên là những gì đang được xây dựng theo hướng lấy kịch bản làm nguồn duy nhất. Nhưng lý do để xây theo hướng đó thì đã rõ từ lâu — từ chính cảnh dựng đèn sai chỗ ở đầu bài này.

Nội dung có sự hỗ trợ của AI, được con người duyệt.
