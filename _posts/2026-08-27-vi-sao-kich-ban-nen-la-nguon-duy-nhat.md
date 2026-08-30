---
layout: post
title: "Vì sao kịch bản nên là nguồn duy nhất"
date: 2026-08-27 13:47:24 +0700
description: "Kịch bản, breakdown, lịch quay lệch nhau vì nằm ba file riêng — xem cách một scene id ổn định giữ chúng khớp và báo khi lệch."
tags: ["kịch bản", "breakdown", "lịch quay", "quy trình sản xuất"]
---
Buổi tối bạn sửa cảnh 42. Đổi một câu thoại, đổi luôn đạo cụ nhân vật cầm ở đầu cảnh — từ bật lửa sang một hộp diêm cũ, hợp với thời điểm phim hơn. Lưu file, tắt máy, đi ngủ. Ba tuần sau ở hiện trường, tổ đạo cụ vẫn mang theo bật lửa, vì bảng breakdown họ cầm là bản xuất từ trước khi bạn sửa cảnh đó.

Không ai sai cả. Kịch bản nằm một file, breakdown nằm một bảng tính khác, lịch quay lại một file khác nữa. Mỗi lần sửa kịch bản là một lần phải nhớ đi sửa lại từng chỗ còn lại — hoặc quên, và không ai biết mình quên cho tới khi đứng giữa hiện trường.

Singularity Pencil gom bảy giai đoạn — Write, Rewrite, Visualize, Storyboard, Breakdown, Plan, Shoot — vào chung một file `.sp`. Không phải bảy phần mềm rời rồi export qua lại, mà một file, một chỗ mở ra là thấy hết.

Cái giữ cho các giai đoạn đó nói chung một chuyện là scene identity: mỗi cảnh có một id ổn định, gắn từ Breakdown, không đổi khi bạn chèn thêm cảnh hay xoá cảnh phía trước nó. Plan dùng đúng id đó khi xếp lịch quay. Đến Shoot, dữ liệu không phải nhập lại lần nữa — Shoot lấy thẳng từ Breakdown và Plan.

Cái đáng nói không phải là "tự động cập nhật" — không có phép màu nào ở đây, và Singularity Pencil không tự viết lại lịch quay giùm bạn mỗi khi bạn sửa kịch bản. Việc đó vẫn của bạn. Cái nó làm là: khi có lệch, nó nói ra thay vì im lặng. Nếu bạn sửa Breakdown sau khi Plan đã lên lịch cho cảnh đó — đổi cảnh, xoá cảnh — Shoot báo cụ thể là id lịch quay đã cũ. Bạn biết ngay chỗ cần xem lại, thay vì mang ra hiện trường một bảng đã lệch từ ba tuần trước mà không ai hay.

Đó là khác biệt giữa đồng bộ và báo lệch. Một cái tự sửa cho bạn, cái kia chỉ đảm bảo id của một cảnh cầm nguyên từ lúc bạn gõ scene heading ở Write cho tới lúc AD cầm tờ lịch quay ở Shoot, và lên tiếng khi hai đầu không còn khớp nhau.

Nói rõ để không ai hiểu nhầm: Singularity Pencil hiện chưa phát hành công khai, chưa có bản để tải về. Những gì mô tả ở đây là thứ đang chạy trong bản dựng hiện tại, không phải lời hứa cho một bản ra mắt nào đó.

Cần đưa file cho AD hay tổ đạo cụ xem trước khi ra hiện trường, cách làm hôm nay là lưu `.sp` và gửi file đó đi — không phải mở cùng lúc trên một phiên bản đang chạy.

Một cảnh viết ra ở Write vẫn là chính cảnh đó khi nó hiện lên trên bảng breakdown, trên shot list, và trên tờ lịch quay AD cầm ở hiện trường — không phải một bản chép tay lại của nó, dễ lệch mỗi lần ai đó gõ lại số.

Nội dung có sự hỗ trợ của AI, được soát tự động trước khi đăng.
