---
layout: post
title: "Machine Learning: Làm việc với video"
categories: Machine Learning
---

Làm việc với video dành cho học máy – P1. 
--------------------
Về cơ bản thì tín hiệu video là tập các ảnh có tính chất tuần tự theo miền thời gian, nó có những đặc tính, thông số đặc tính riêng so với làm việc với ảnh, đặc biệt khi video đã qua nén. Trong phần này mình sẽ nói về chất lượng khung hình trong video cũng như hưởng tới các trích chọn khung hình, phần kế tiếp mình sẽ trình bày về các dạng lỗi/nhiễu trong video. 

1) Dữ liệu đầu ra của các camera (gần như hầu hết trường hợp) là đã ở dạng nén. Và do nén video là dạng nén có suy hao, nên rất nhiều thông tin đã bị xóa bỏ khỏi tín hiệu video gốc để sao cho video sau nén nhìn vẫn giống video gốc nhất nhưng dung lượng lưu trữ giảm đi nhiều. 
Vậy bạn nên nhớ, nén video là để chất lượng “nhìn giống” không nén nhất. Hoàn toàn không để ý tới mục đích bảo toàn thông tin cho các bài toán machine learning. 

2) Chất lượng của video phụ thuộc vào độ phân giải camera, kỹ thuật mã hóa (H264, H265, VP9, AV1), phần mềm mã hóa (phần mềm thực thi mã hóa, ví dụ như cùng chuẩn H264 có nhiều thực thi khác nhau), cấu hình mã hóa (ngoại tuyến, trực tuyến, tốc độ mã hóa, v.v.), và tốc độ bits per second (bps). 
Vậy nên cùng một camera có thể trả về chất lượng video khác nhau, tốc độ fps cũng như độ phân giải, hoặc định dạng mã hóa khác nhau. 

3) Chất lượng các khung hình (frame) là không đồng đều.
Ví dụ khung hình thứ 1 và thứ 5 chất lượng khác nhau rất lớn. Lý do là do đặc tính mã hóa video là mã hóa suy hao. Nên chất lượng các khung hình được thiết kế nén sao cho thứ tự tăng giảm đan xen để tận dụng đặc tính lưu ảnh của mắt người. Ví dụ 1 ảnh chất lượng cao, 3 ảnh chất lượng kém diễn ra trong khoảng thời gian ngắn thì mắt người không cảm nhận được. 
Trong khi xử lý dữ liệu video, các bạn thường không dung tất cả các khung hình, mà chỉ dung một phần của nó, vậy thì chọn khung hình nào? 

![qownnotes-media-ZeMnHM](media/qownnotes-media-ZeMnHM.png)

Mã hóa video nếu không trong trạng thái cấu hình nhóm khung (Group of Pictures) động, tức là sẽ dung nhóm khung tĩnh cố định. Thường ở dạng 8, 16 hoặc 32, khung ảnh hình thành một nhóm. Vì vậy nên trích suất các khung hình có vị trí chia hết cho 8. Nếu muốn lấy nhiều hơn thì chia hết cho 4, rồi tới 2.  
(chi tiết hơn mình sẽ trình bày ở bài khác). 
 
Ví dụ về một GOP kích thước 4. POC là Picture Order Count, thứ tự hiển thị các khung ảnh. 
Decoding order: là thứ tự giải mã các khung hình. 

4. Việc truy suất các khung hình
Ví dụ bạn muốn truy suất khung hình thứ POC3 ở phần trên, thì thực chất bạn phải chờ giải mã hết 4 khung hình trước đó thì mới tới POC3. Như vậy việc trích suất khung hình nào ảnh hưởng nhiều đến độ trễ cho ứng dụng. Vậy nếu bạn nổi hứng muốn truy suất POC7, thì bạn càng phải đợi lâu hơn nữa. Lý do là mã hóa video tận dụng sự giống nhau của các bức ảnh lân cận nên chỉ mã hóa sự khác biệt. Từ đó gây ra sự phụ thuộc của một nhóm ảnh. 

 ![qownnotes-media-QkZxFX](media/qownnotes-media-QkZxFX.png)

Lưu ý, cấu trúc lặp lại này phụ thuộc tần suất suất hiện của khung hình I – Intra frame (khung dự đoán liên khung). Hình trên ví dụ là 4 và 8, trong thực tế thường tần suất suất hiện của I frame cỡ 120 khung trở lên nên cần lựa chọn khung hình vừa chất lượng cao vừa giảm trễ truy suất. 

Phía trên là cấu hình dạng truy suất ngẫu nhiên (Random Access), còn các cấu hình khác như Độ trễ thấp (Low-delay) thì cách thức truy vấn lại khác nhau một chút. 



## Tác giả