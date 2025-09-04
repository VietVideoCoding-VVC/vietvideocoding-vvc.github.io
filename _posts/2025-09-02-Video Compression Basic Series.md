---
layout: post
title: "Tài Liệu Cơ Bản về Nén Video?"
categories: [nen-video-co-ban]
tags: [video coding, overview]
series: "Mã hóa video cơ bản"
series_order: 1
author: thuongnguyencanh
---
## Video - Ông Hoàng của Internet
Video hiện nay là nội dung thống trị mạng Internet. Theo thống kê mới nhất, video đang chiếm tới **82%** lưu lượng toàn Internet và **75%** lưu lượng di động toàn cầu - và con số này vẫn không ngừng tăng lên. Nói theo cách khác, bạn có thể coi 3/4 những gì đang chạy lung tung trên mạng có dây (cáp quang) lẫn không dây (4G/5G) là để phục vụ cho việc ... xem clip mòe, các bạn nhảy nhót trên TikTok, phim Netflix,(hay review film trên Youtube), live stream game hay bán hàng online, và gọi video của ai đó. 

![Lưu lượng Video trên Internet](/assets/images/20250903_videoTrafficInternet.jpeg){: .img-80 }
<p class="figure-caption">
Hình 1: Video chiếm phần lớn lưu lượng Internet toàn cầu
</p>
Không chỉ bùng nổ về mặt nội dung, mà thiết bị hiển thị cũng ngày càng "hịn" hơn. Các điện thoại đắt tiền đã bắt đầu hỗ trợ màn hình độ phân giải cao trên HD, độ tương phản cao (HDR), số lượng TV màn hình hỗ trợ 4K/HDR thì ngày càng phổ biến, thiết bị VR/AR, độ phân giải 8K bắt đầu len lỏi. Xu hướng "mọi thứ trên mây" như *Cloud gaming* khiến việc nén và truyền tải video trở thành công nghệ sống còn cho các đại gia công nghệ. 

### Ai đang nắm giữ chuẩn nén video? 
Khỏi phải nói, nén video được xem là công nghệ lõi và được đầu tư rất mạnh bởi các tập đoàn và quốc gia hàng đầu công nghệ về thiết bị cũng như nền tảng số như
- Mỹ: Google, Apple, Qualcomm, Netflix, Amazon, InterDigital, Dolby Laboratories, .v.v.
- Trung Quốc: Alibaba, ByteDance/Tiktok, Tencent, Huawei, Xiaomi, Oppo, TCL, .v.v., 
- Nhật: KDDI, Sony, Canon, Sharp, Panasonic, Fujitsu, .v.v.
- Hàn Quốc: Samsung, LG, Hyundai, ETRI, .v.v., 
- Châu Âu: Đức (HHI), Pháp (Orange), Phần Lan (Nokia), Thụy Điển (Erricson), .v.v. 

Để hình dung rõ hơn, dưới đây là bản đồ các đại gia nắm giữ bằng sáng chế (licensor) của từng chuẩn nén:

![Các công ty tham gia cấp phép HEVC](/assets/images/20250903_HEVC_Licensor.jpg)

<p style="figure-caption">
Hình 2: Các công ty đóng góp bằng sáng chế trong chuẩn H.265/HEVC
</p>

![Các công ty tham gia cấp phép VVC](/assets/images/20250903_VVC_Licensor.jpg){: .img-80 }

<p style="figure-caption">
Hình 3: Các công ty đóng góp bằng sáng chế trong chuẩn H.266/VVC
</p>

![Các thành viên của AOM/AV1](/assets/images/20250903_AOM_Members.webp){: .img-80 }

<p style="figure-caption">
Hình 4: Các công ty tham gia AOM và phát triển AV1.
</p>

### Khoảng trống trong công nghệ Video ở Việt Nam
Theo mình biết thì chưa có công ty Việt Nam nào thực sự nghiên cứu và phát triển CODEC mới, thiết kế CHIP hay xây dựng API nén video của riêng mình. Phần lớn chỉ dừng lại ở việc *tích hợp SoC/Chip CODEC* có sẵn của nước ngoài để sử dụng. Nói đi cũng phải nói lại, nén video là lĩnh vực cực kỳ phức tạp: nó đòi hỏi kiến thức từ xử lý tín hiệu số, xử lý ảnh/video, kỹ năng lập trình C/C++, kỹ năng đọc hiểu tài liệu khô khan với tốn nhiều thời gian mô phỏng/đánh giá -- cà tất cả đã có hơn 30+ năm lịch sử phát triển. 

Trong khi đó ở Việt Nam mình thì tài liệu về mảng này thực sự *đếm trên đầu ngón tay*. Phần lớn xoay quanh các giáo trình cũ, các bài luận văn đơn giản hoặc bản dịch sơ sài. Nhiều tài liệu vẫn dừng ở chuẩn nén H.264/AVC (2004), và phần nhiều dừng lại ở H.265/HEVC (2012) và phải tìm mỏi mắt mới thầy một vài tài liệu H.266/VVC (2020), còn AOM AV1 (2018) thì thôi khỏi.

Tài liệu mang tính chất nền tảng, tổng quát hay chi tiết về các công cụ nén gần như vắng bóng. Số lượng chuyên gia người Việt tham gia trực tiếp phá triển thuật toán mới hay góp mặt trong hiệp hội chuẩn hóa MPEG/AOM cũng chỉ đếm trên đầu ngón tay, và đều ở các công ty nước ngoài.

### Vì sao mình viết loạt bài này?
Chính vì vậy, mình muốn viết loạt bài *giới thiệu cơ bản về nén video*, kế đó là loạt bài chi tiết hơn về H.265/HEVC (vì bây giờ đang là thời của HEVC), rồi H.265/VVC hay AV1 ... với mục đích để chia sẻ lại phần kiến thức mình hiểu. Kiểu gì cũng có thiếu sót, nhưng cũng hy vọng phần nào giúp các bạn đọc có cái nhìn rõ hơn về mảng công nghệ **căn bản** (là rất khoai) này. Và biết đâu đấy, qua đó mình sẽ có thêm một đồng nghiệp một ngày không xa 🙂. 

<!-- Đáp ứng lại, ta cũng có các chuẩn nén thế hệ mới như **AV1(2018), H.266/VVC(2020), AV2 (2025), và sắp tới là H.267**.  
-->
