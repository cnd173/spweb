---
layout: post
title: "Vì sao file .sp mở được bằng thứ khác"
date: 2026-08-26 20:46:38 +0700
description: "File .sp thực chất là một file ZIP mở được bằng công cụ khác — đây là lựa chọn có chủ đích, không phải sơ suất."
tags: ["định dạng file", "local-first", "tương thích ngược", "giấy phép mở"]
---
Một ngày nào đó, bạn mở lại file kịch bản cũ để tìm một cảnh từng viết ba năm trước. Phần mềm bạn dùng hồi đó không còn được cập nhật nữa. File vẫn nằm đó, nhưng công cụ đọc nó thì không. Bất cứ ai từng đổi máy tính, đổi hãng phần mềm viết kịch bản, hay chỉ đơn giản là chờ một bản cập nhật không bao giờ tới, đều biết cảm giác này.

`.sp` được thiết kế để tránh đúng tình huống đó.

Về bản chất, một file `.sp` là một file ZIP chứa dữ liệu dự án. Không cần công cụ chuyên dụng để nhìn vào bên trong — một trình giải nén bình thường cũng mở được. Đây không phải là lối tắt kỹ thuật. Đây là lựa chọn để dữ liệu dự án của bạn không bị khoá sau một định dạng đóng mà chỉ một phần mềm duy nhất đọc được.

Font cũng theo nguyên tắc tương tự, nhưng theo hướng ngược lại: `.sp` không nhúng font của bên thứ ba vào file. Nó chỉ lưu profile, hash và tham chiếu tới font đang có sẵn trên máy bạn. Nghĩa là gửi file cho người khác không đồng nghĩa với việc phát tán bản sao font mà bạn đã mua giấy phép — và cũng có nghĩa là quyền sử dụng font vẫn thuộc về đúng người sở hữu nó, không phải công ty làm phần mềm.

File cũng mang một document id ổn định xuyên suốt vòng đời dự án, cộng với các trường tuỳ chọn tương thích ngược. Khi công cụ thêm tính năng mới, bản file cũ của bạn — viết từ trước khi tính năng đó tồn tại — vẫn mở được bình thường. Không có tính năng mới nào có quyền làm file cũ của bạn thành file mồ côi.

Đi ra ngoài cũng dễ như đi vào. `.sp` nhập và xuất được Fountain và FDX, hai định dạng đã quen thuộc với người viết kịch bản từ trước khi công cụ này tồn tại. Xuất PDF khi cần bản in chỉnh phân trang cho buổi đọc, xuất DOCX khi biên tập cần ghi chú bằng công cụ khác. Không ai phải học lại cách làm việc chỉ vì đổi phần mềm.

Việc lưu file cũng theo cùng logic: local-first. Autosave chạy trên IndexedDB ngay trên máy bạn, và cơ chế lưu dùng Yjs — dữ liệu ưu tiên nằm ở máy bạn trước, không phụ thuộc vào việc có một máy chủ nào đó đang chạy hay không. Cộng tác trực tuyến hiện đang bị khoá mặc định, vì máy chủ production cho tính năng đó chưa sẵn sàng. Cách chia sẻ dự án lúc này đơn giản hơn: lưu file `.sp`, gửi cho người cần xem. Không có máy chủ nào đứng giữa bạn và file của mình.

Mã nguồn của công cụ này theo giấy phép MIT. Ai muốn đọc cách file được ghi ra, cách nó được phân tích, đều đọc được — không phải tin vào lời hứa.

Sản phẩm chưa phát hành công khai. Chưa có bản tải về, chưa có bảng giá, chưa có ngày ra mắt cụ thể. Tên gọi "Singularity Pencil" hiện là tên tạm, chưa qua thẩm định nhãn hiệu. Những gì viết ở trên là về cách file được thiết kế — không phải lời hứa về khi nào bạn cầm được nó trên tay.

Nội dung có sự hỗ trợ của AI, được con người duyệt.
