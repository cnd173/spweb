---
layout: post
title: "Chúng tôi đang ở đâu, và còn thiếu gì"
date: 2026-08-26 19:50:51 +0700
description: "Bản nội bộ 0.1.0-rc1: những gì đã chạy được, những gì đang cố tình khóa lại, và vì sao chưa hứa ngày ra mắt nào."
tags: ["trạng thái", "phát hành", "tính năng"]
---
Bản đang chạy nội bộ vẫn mang số hiệu 0.1.0-rc1. Đây vẫn là một bản dựng thử nghiệm, chưa ký số. Singularity Pencil chưa phát hành công khai, chưa có bản tải về cho người ngoài công ty, và chưa có bảng giá. Không có ngày ra mắt nào được chốt — nên bài này sẽ không hứa ngày nào cả.

Phần đã chạy được, ngay trong bản rc1:

Trình soạn kịch bản dựng trên Tiptap/ProseMirror, nhận đủ các loại dòng của một kịch bản phim — action, dialogue, character, parenthetical, transition — và chuyển loại dòng bằng Tab hoặc Enter thay vì phải chọn menu. Gõ tiếng Việt bằng bộ gõ (IME) hoạt động trong khung soạn thảo; bộ kiểm tự động có phủ ca gõ tiếng Việt dạng precomposed.

Nhập và xuất định dạng Fountain và FDX, để không khóa người dùng vào một định dạng riêng ngay từ đầu. Xuất PDF và DOCX cho khâu in ấn hoặc gửi đọc. Beat Board, Outline, và Characters để theo cấu trúc và nhân vật song song với bản thảo.

File dự án lưu ở định dạng `.sp`, là một file ZIP chứa dữ liệu dự án — không nhúng font của bên thứ ba, chỉ lưu profile/hash/tham chiếu tới font mà máy người dùng đang có sẵn. Autosave chạy trên IndexedDB, và việc lưu là local-first bằng Yjs — nghĩa là dữ liệu ưu tiên nằm trên máy trước, không phụ thuộc một máy chủ đang chạy.

Bản desktop dựng bằng Electron, có hộp thoại mở/lưu file gốc của hệ điều hành và tự gắn đuôi `.sp`. Storyboard theo từng cảnh là một image board: mỗi cảnh có các shot card kèm title/prompt/notes/status, sắp xếp lại được, nhận ảnh import/kéo-thả/dán, và import shot thẳng từ Visualize. Rewrite là một workspace soạn thảo riêng: bản gốc giữ nguyên không sửa được, bản viết lại nằm cạnh nó trong cùng editor, mỗi lần lưu là một mốc không ghi đè. Ba tác vụ chính là Workspace, Compare và Notes; Scene Variations, AI Rewrite và Consistency Check nằm trong nhóm công cụ mở rộng. Đưa bản viết lại về bản chính là một thao tác riêng, có tạo mốc phục hồi trước. Breakdown chia 15 hạng mục sản xuất và xuất được ra CSV. Story Graph trình bày cấu trúc truyện dưới dạng đồ thị.

Series là một workspace riêng cho phim nhiều tập: một Series Bible có giới hạn dung lượng, các tab Mùa, bản đồ tập, mỗi tập mang trạng thái, logline và thời lượng riêng và trỏ tới một tài liệu kịch bản độc lập chứ không phải một chương trong cùng một file. Trần hiện tại là 100 mùa và 500 tập mỗi mùa. Story Guide là lộ trình chín chặng có checkpoint, đi từ ý tưởng lõi, chủ đề và xung đột, nhân vật, logline, cấu trúc, synopsis, outline, tới bản thảo đầu và bản viết lại.

Xuất bản có workspace riêng chứ không phải một hộp thoại. Chọn được phần nào của dự án đi ra, theo preset — kịch bản PDF, hồ sơ dự án, sổ sản xuất, gói chia sẻ, hoặc tự đặt — và xuất được ra HTML, Markdown, PDF, DOCX, XLSX, CSV, Fountain, FDX, cùng một bản HTML chỉ đọc.

Giao diện có tiếng Việt và tiếng Anh, đổi ngay trong ứng dụng. Ngôn ngữ giao diện tách khỏi ngôn ngữ kịch bản: cái sau đặt riêng theo từng dự án. Bố cục trang kịch bản có bốn hồ sơ theo khu vực — US/Hollywood là mặc định, cùng Japan (Kido 2026), Mainland China (Xia Yan Cup 2026) và Korea (KOFIC 2026). Chỗ nào giải thưởng không công bố số đo trang cụ thể thì sản phẩm ghi thẳng đó là mốc dựng của mình, không trình bày như yêu cầu chính thức của ban tổ chức.

Phần chưa xong, hoặc đang cố tình khóa lại:

Cộng tác trực tuyến — nhiều người cùng sửa một kịch bản qua mạng — đang bị khóa mặc định. Lý do đơn giản: chưa có máy chủ production để chạy nó, không phải vì tính năng chưa viết xong ở phía client. Cách chia sẻ bây giờ là lưu file `.sp` rồi gửi cho người kia.

Bản web hosted thì đang chạy thật, nhưng cần nói rõ nó là gì: một bản thí điểm kín ở `sp.cdsfilms.com` cho vài người được mời, khoá bằng mật khẩu từ 30/08/2026. Đó không phải bản phát hành công khai, và nó không rút ngắn bất cứ mục nào trong danh sách còn thiếu ở phần này. Đăng nhập Google trên tên miền thật cũng chưa qua thẩm định, nên cộng tác trực tuyến vẫn tắt mặc định ngay cả ở đó.

Tên gọi "Singularity Pencil" hiện là tên tạm. Nó chưa qua thẩm định nhãn hiệu, và có thể sẽ đổi trước khi phát hành. Chúng tôi không coi đây là tên chính thức cho tới khi việc thẩm định xong.

Bản ký số/notarize cho bản desktop — bước cần để hệ điều hành không cảnh báo "ứng dụng không rõ nguồn gốc" khi mở lần đầu — chưa hoàn tất. Smoke chức năng cho bản web hosted — onboarding, nhập/xuất, round-trip `.sp`, hành vi ngoại tuyến — cũng chưa chạy; lượt smoke đã làm chỉ phủ khả năng truy cập, độ mới của bundle và các header. Bản iOS chưa bắt đầu — trong repo mới chỉ có tài liệu phạm vi cho Phase 3, chưa có dòng mã nào để dùng thử.

Về giấy phép: mã nguồn theo MIT. Phần AI trong sản phẩm theo mô hình BYOK (bring your own key) — người dùng tự cắm khóa API của họ, chúng tôi không cung cấp AI miễn phí hay không giới hạn kèm sản phẩm.

Về chuyện bán cái gì: chưa có mức giá nào, nhưng ranh giới thì đã chốt ngày 29/08/2026. Bản cài đã ký số và notarize là thứ miễn phí, không bán. Bán nó nghĩa là bắt người không trả tiền chọn giữa một cảnh báo "ứng dụng không rõ nguồn gốc" và tự dựng từ mã nguồn — mà người viết kịch bản thì không tự dựng từ mã nguồn. Thứ được bán là kênh cập nhật có quản lý và quản lý phiên bản theo đội, thứ chỉ nơi có bộ phận IT mới cần. Kèm theo đó là một cam kết không được phép lùi: nếu dự án ngừng bảo trì, không bản thảo nào bị mắc kẹt — mã nguồn MIT, file `.sp` nằm trên máy người dùng, và xuất được ra những định dạng công cụ khác đọc được.

Chúng tôi viết bài này không phải để xin lỗi vì chưa xong, mà để ghi lại đúng một mốc: đây là những gì chạy được hôm nay, đây là những gì đang khóa và vì sao. Danh sách này sẽ còn thay đổi.

Nội dung có sự hỗ trợ của AI, được con người duyệt.
