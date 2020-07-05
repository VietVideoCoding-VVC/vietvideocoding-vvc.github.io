---
layout: post
title: Mã Hóa Hiệu Năng Cao - H.265/HEVC: Kẻ kế nhiệm rắc rối
---

(Bản dịch từ bản gốc Tiếng Anh, 2018/07, link ở cuối bài)
H.265/HEVC là chuẩn mã hóa video với mục đích giảm một nửa băng thông so với chuẩn trước đó. Để đạt tỷ lệ nén gấp đôi chuẩn tiền nhiệm H.264/AVC. Để tăng được gáp đôi tỷ lệ nén, chuẩn HEVC được thành lập với những thuật toán phức tạp cho ước lượng chuyển động, dự đoán khung, và phân tách khung.
Việc giảm bitrate lên tới 50% so với AVC mà không làm thay đổi chất lượng video, HEVC giúp tiết kiệm băng thông đông thời cho phép truyền tải video chất lượng cao hơn qua mạng Internet.
Công nghệ truyền thông đã lên tới truyền phát nội dung 4K - chứa gấp 4 lần số lượng điểm ảnh so với Full HD 1080p. Nếu không dùng HEVC, nhà đài muốn truyền nội dung 4K phải đối mặt với nhu cầu về băng thông rất cao. HEVC giúp hiện thực hóa truyền tải nội dung 4K, giúp giảm cả về chi phí lẫn thời gian truyền tải.
Trong khi công nghệ nén này được mong chờ sẽ có mặt ở tât cả các bộ xử lý video, thiết bị hiển thị trong tương lai thì quá trình ứng dụng công nghệ này lại tiến triển rất chậm. Tất cả là do vấn đề bản quyền quá phức tạp.

Quy trình phát triển HEVC
Quá trình phát triển HEVC gần như được tiến hành ngay sau khi AVC được chuẩn hóa xong từ năm 2004. Người tiền nhiệm chuẩn AVC gần như trở thành định dạng phổ biến nhất cho cả chụp video, nén và phân phối nội dung video trên khắp thế giới.
Cha đẻ của công nghệ HEVC là các đại gia công nghệ  Samsung Qualcomm, LG, MediaTek, Microsof, SK Telecom, Huawei, và rất nhiều các công ty khác.
Profile chính của HEVC (video 8bit) được hoàn thiện bản đẩu tiên vào năm 2013 với lộ trình phát triển như sau

![Fig. 1](https://scontent-sjc3-1.xx.fbcdn.net/v/t1.0-9/82096064_2769894076404546_6734642701632798720_n.jpg?_nc_cat=104&_nc_sid=32a93c&_nc_ohc=umIuWiLBSDwAX-BfSWu&_nc_ht=scontent-sjc3-1.xx&oh=f96d7cb0bb28f9ff3483a9c156f74dc7&oe=5F2939B2)

Figure 1: Lộ trình phát triển nén video , Source: SlideShare

Công nghệ được mô tả trong phiên bản đầu tiên HEVC cho profile chính 8-bit đã được thực thi trong rất nhiều bộ giải mã cả phần cứng lẫn phần mềm và đã có mặt trong rất nhiều nhãn hiệu điện thoại thông minh, máy tính, truyền hình, đầu thu kỹ thuật số. HEVC được dự đoán sẽ được dùng trong cả truyền thông vệ tinh, truyền hình cap, truyền hình mặt đất, lĩnh vực game, và streaming cho tới cuối thập kỷ 2010-2019.
Ai Sở Hữu HEVC

HEVC có tổng cộng 993 họ bằng sáng chế liên quan - được xác định dựa trên nhóm phân tích 6500 họ bằng sáng chế. Phần lớn số họ bằng sáng chế này được sở hữu bởi những công ty lớn tham gia quá trình chuẩn hóa phiên bản đầu tiên như Qualcomm, Samsung, LG, MediaTek, Huawei .v.v Tuy nhiên cũng có gần 75 công ty và viện nghiên cứu khác sở hữu bằng sáng chế định hình lên HEVC. Hình dưới đây mô tả những chủ sở hữu của công nghệ nén này.

Figure 2: Phân bố sở hữu bản quyền của HEVC
Họ bằng sáng chế giúp xác định rõ quy mô cũng như phạm vi bảo vệ của bằng sáng chế, đồng thời đưa cái nhìn sâu sắc vê những bằng sáng chế nào được bảo vệ ở những quốc gia nào. Nhìn vào các chủ sở hữu lớn nhất bản quyền HEVC được thống kê dưới đây.

Table 1: Danh sách các công ty sở hữu nhiều bằng sáng chế HEVC nhất
Một điều thú vị là, sở hữu của một số bằng sáng chế đã thay đổi trong những năm gần đây. Phân tích về 993 họ bằng sáng chế liên quan cho thấy 12% bằng sáng chế đã được chuyển chượng và mua bán lại.

Table 2: Danh sách chuyển nhượng bản quyền
Hãng Panasonic đã chuyển lượng lớn bằng sáng chế của mình cho các công ty khác. Thời điểm ban đầu chỉ có một Nhóm bằng sáng chế duy nhất là MPEG LA, thì Panassonic đã gửi gắm 5 bằng sáng chế của mình cho công ty Tagivan II LLC (trực thuộc của MPEG LA) năm 2014. Tuy nhiên sau đó, Panasonic lại bán đi 34 họ bằng sáng chế liên quan tới HEVC cho Sun Patent Trust.
Hãng GE Video Compression đã mua tổng cộng 7 họ bằng sáng chế liên quan tới HEVC từ viện nghiên cứu Fraunhofer hàng đầu Đức, trong khi đó 75% bằng sáng chế của Dolby (9 trên tổng số 12) được mua lại từ các công ty khác như Sharp, France Telecom và Broadcom.
Nhóm bằng sáng chế: chuyển nhượng

Mặc dù quá trình phát triển chuẩn HEVC là nỗ lực hợp tác từ nhiều công ty, bản quyền công nghệ HEVC không được định nghĩa như quá trình hợp tác hoặc được thống nhất lại. Thời điểm hiện tại có ít nhất 3 nhóm bằng sáng chế là MPEG LA, HEVC Advance, và Velos Media.


Table 3: Nhà cung ứng bằng sáng chế lớn

Cả 3 nhà cung ứng bằng sáng chế trên đã bao gồm 4200 tài liệu bằng sáng chế được chia thành 560 họ bằng sáng chế. MPEG LA có phần lớn với 360 họ, HEVC Advance có 73, và Velos Media có 27. Trong số 460 họ bằng sáng chế trên thì có 321 họ liên quan tới mã nóa profile chính 8-bit của HEVC, đây cũng chiếm 1/3 số lượng bawgnf sáng chế liên quan tới HEVC.
Xây dựng có tính kế thừa

Quá trình phát triển HEVC dựa trên việc cải tiến những công nghệ có sẵn trong H.264/AVC. Trong quá trình phát triển, HEVC cũng đã sử dụng lại những công nghệ có sẵn ở AVC. Hình 4 thể hiện tỷ lệ bắng sáng chế liên quan tới HEVC và AVC.


Figure 3: Kế thừa từ AVC
Gần 1/3 họ bằng sáng chế liên quan tới HEVC có liên hệ với AVC. Phần lớn các công ty sở hữu công nghệ đó là Fujitsu, NTT, và Panasonic.
Kịch bản bản quyền cho HEVC

Một điều rất đáng chú ý là chi phí bản quyền HEVC không thống nhất giữa các nhóm bằng sáng chế khác nhau. Mỗi nhóm bằng sáng chế có chiến lược cấp bằng sáng chế riêng, với nhiều loại và thiết bị khác nhau. Chi tiết mức đọ loằng ngoằng của cách tính phí bản quyền của AVC (MPEG-LA) và HEVC (MPEG-LA, HEVC Advance) như sau

Bảng 4: Cơ cấu bản quyền của AVC (MPEG LA)


Bảng 5: Cơ cấu bản quyền của HEVC (MPEG LA) and HEVC Advance
Sau khi phân tích, sự khác biệt giữa các nhóm bằng sáng chế chính là
AVC có phí bản quyền thấp hơn với số lượng đơn vị hơn 5 triệu.
AVC có mức phí trần thấp hơn - 9.75 triệu đô. Trong khi MPEG-LA là 25 triệu đô, và HEVC Advance là 40 triệu đô cho HEVC
Nhà phân phối nội dung và truyền hình trực tiếp sẽ không còn được tính phí theo cách tính của AVC nữa mà theo nhóm bản quyền mới MPEG LA và HEVC Advance cho HEVC
Ngoài ra, cấu trúc nhóm bản quyền của Velos Media và các nhà cung cấp bản quyền chưa nằm trong nhóm khác như Technicolor vẫn còn rất mù mờ và có thể làm chậm quá trình thực thi chuẩn hóa.
Trên thực tế, HEVC đã đắt hơn vài lần so với AVC với bất kỳ thiết bị nào sản suất trên 5 triệu đơn vị. Thậm chí nhà sản suất, phát triển có thể phải mua bản quyền từ nhiều nhóm bằng sáng chế khác nhau, và từ các công ty không nằm trong nhóm đó (vì nhóm bằng sáng chế chỉ bao gồm 1/3 số bằng sáng chế liên quan tới HEVC), từ đó đẫn đến gia tăng đáng kể chi phí cũng như phức tạp bản quyền.
Tương lai nào cho HEVC

Công nghệ HEVC cũng đang đần được thực thi ở tốc độ rất chậm hơn dự kiến. Phần lớn là do hậu quả của cấu trúc cấp bản quyền quá lằng nhằng và gặp phải sự cạnh tranh từ các công nghệ khác như AV1-Chuẩn open và AVS2 - Chuẩn của Trung Quốc.  Trong khi đó công nghệ nén AVC vẫn là phổ biến và giá thành rẻ nhất.
Quá trình hình thành nhiều nhóm bằng sáng chế khác nhau đã khiến các chủ sở hữu bằng sáng chế HEVC khó định nghĩa quy mô của bản quyền. Một vài hãng công nghệ lớn ở hữu HEVC gồm cả LG và Huawei lại không tham gia vào các nhóm bằng sáng chế, trong khi các hãng khác như Samsung, Mediatek chỉ góp vào nhóm bằng sáng chế một phần bằng sáng chể của họ cho một hoặc nhiều nhóm bằng sáng chế. Trên thực tế, chỉ 1/3 số bằng sáng chế là được nằm trong nhóm bằng sáng chế mà thôi.
Bất chấp các nỗ lực đó, chi phí bản quyền của công nghệ HEVC vẫn cao hơn rất nhiều so với AVC. Khi một nhà sản xuất và phát triển có thể đứng trước nguy cơ phải mua bản quyền từ nhiều nhóm bằng sáng chế khác nhau mà vẫn không hoàn toàn được bảo vệ vì một vài công ty khác vẫn chưa công bố cấu trúc bản quyền của họ.
Giới công nghiệp có thể sẽ gặp rắc rối khi triển khai công nghệ chuẩn HEVC với nhiều khác biệt cũng như phức tạp về cơ cấu chi phí liên quan tới nhóm bản quyền. Đặc biệt khi 2/3 lượng bản quyền liên quan đều không rõ ràng về cơ cấu bản quyền. Tương lai của HEVC sẽ không mấy sáng sủa, và tốc độ thực thi/chấp nhận công nghệ HEVC vẫn sẽ tiến triển rất chậm.

Bản gốc: [High Efficiency Video Coding ecosystem evolving](https://www.ipwatchdog.com/2018/07/11/high-efficiency-video-coding-video-ecosystem-evolving/id=99094/)

