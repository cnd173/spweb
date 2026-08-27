---
layout: post
title: "AI trong Singularity Pencil: bạn mang khoá của mình"
date: 2026-08-26 19:50:55 +0700
description: "Vì sao các tính năng AI chạy bằng khoá API của chính bạn, và điều đó đổi gì về việc kịch bản của bạn đi tới đâu."
tags: ["ai", "byok", "quyền riêng tư"]
---
Bạn mở Rewrite, chọn một cảnh, bấm AI Rewrite. Câu hỏi trước khi bấm thường không phải "kết quả có tốt không" mà là: nội dung cảnh này đi đâu, và ai đứng giữa tôi và mô hình.

Singularity Pencil trả lời câu hỏi đó bằng một lựa chọn kiến trúc: BYOK — bring your own key. Bạn tự tạo khoá API ở OpenAI hoặc Anthropic, dán khoá đó vào sản phẩm, và các tính năng AI dùng khoá của bạn để gọi thẳng tới nhà cung cấp đó. Riêng phần sinh ảnh cho storyboard hiện chỉ chạy được với khoá OpenAI. Sản phẩm không bán token, không gộp chi phí AI vào giá.

Vì sao không phải mô hình quen thuộc hơn — nơi sản phẩm tự lo phần AI, người dùng chỉ trả một mức phí gộp?

Lý do đơn giản nhất, và cũng là lý do đáng nói nhất: kịch bản là tài sản riêng của người viết. Một bản draft chưa xong, một plot twist chưa ai biết, một câu thoại đang thử rồi xoá — đó là tài sản, đôi khi là sinh kế. Mô hình BYOK giữ khoá AI trong tay bạn, không phải trong tay Singularity Pencil. Chúng tôi không giữ một khoá dùng chung để thay bạn gửi nội dung kịch bản đi bất cứ đâu.

Hai câu hỏi mà người viết kịch bản thường hỏi trước tiên:

**Kịch bản của tôi có bị dùng để huấn luyện mô hình không?** Với BYOK, câu trả lời không nằm ở Singularity Pencil — chúng tôi không sở hữu mô hình, không giữ bản sao nội dung để huấn luyện bất cứ thứ gì.

**Ai trả tiền cho AI?** Bạn. Khoá là của bạn, hoá đơn là của bạn, trực tiếp với nhà cung cấp bạn chọn.

Những chỗ AI hiện diện trong sản phẩm: viết lại cảnh ở giai đoạn Rewrite, gợi ý breakdown, tóm tắt cảnh trong Node Editor, và sinh ảnh cho storyboard. Tất cả đều dùng khoá do bạn cắm vào. Consistency Check và Scene Variations thì không dùng AI — một cái là bộ luật kiểm tra viết sẵn, một cái là các bản thử do chính bạn viết ra.

Mã nguồn của Singularity Pencil là MIT. Điều này không trực tiếp trả lời câu hỏi về AI, nhưng cùng một logic: sản phẩm không giữ bạn lại bằng cách khoá bạn vào hạ tầng của mình — ở phần mã nguồn, và ở phần AI.

Bài này không nói AI trong Singularity Pencil tốt hơn công cụ nào khác, cũng không so sánh mô hình nào với mô hình nào. Điều kiểm soát được, và đáng nói, là: bạn biết khoá đi đâu, biết ai đứng giữa bạn và mô hình, và không phải trả tiền cho ai ngoài nhà cung cấp bạn tự chọn.

Singularity Pencil chưa phát hành công khai. Những gì mô tả ở đây là cách các tính năng AI được thiết kế để hoạt động trong sản phẩm đang phát triển, không phải lời mời dùng thử ngay hôm nay.

Nội dung có sự hỗ trợ của AI, được con người duyệt.
