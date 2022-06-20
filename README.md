## CSC14116 - Lập trình song song ứng dụng

### Tổng quan
Làm mở hoặc thay đổi background(hậu cảnh) là một trong những ứng dụng cần thiết trong bối cảnh hậu đại dịch Covid, khi mà càng có nhiều cuộc họp được thực hiện trực tuyến mà người dùng muốn có một không gian họp riêng tư ngay trong chính căn phòng của mình. \
Việc thay đổi background gồm 2 bước chính:
 1. Xác định khung viền bọc xung quanh người
 2. Tùy theo làm mờ hay thay đổi background mà có thể nhân ma trận để làm mờ hoặc ghép hình người vào một khung cảnh khác

### Động lực
Chúng tối thấy việc thay đổi background khá thiết thực và được sử dụng nhiều trong thời đại công nghệ hiện nay. Bên cạnh đó công việc này cũng có thể phân ra thành các bước áp dụng được song song hóa, từ đó cải thiện tốc độ xử lý vấn đề. 

### Vì sao cần song song hóa ?
Việc thay đổi background có thể làm tốn rất nhiều tài nguyên nếu được thực hiện tuần tự trên CPU do mỗi giây trên video có rất nhiều khung hình cần được tính toán mà tài nguyên của CPU thì có hạn. Vì thể chúng tôi mong muốn có thể giả lập lại việc thay đổi background chạy song song trên GPU để tăng tốc quá trình xử lý, từ đó có thể đạt được hiệu năng như các ứng dụng họp online như Zoom, Google Meet, ...

**Input**
Hình ảnh, Video người dùng trong các cuộc họp trực tuyến và hình ảnh background người dùng muốn thay thế.

**Output**
Hình ảnh, Video đã được thay đổi background.


<img src="https://user-images.githubusercontent.com/50958253/174557063-b2699158-4098-4929-b501-bc23eb55f2b0.png" alt="drawing" width="200"/> + <img src="https://user-images.githubusercontent.com/50958253/174557523-737ec1d9-5514-4a00-9d6f-6b0440eaf718.png" alt="drawing" width="200"/>
 = <img src="https://user-images.githubusercontent.com/50958253/174557505-e5784dcb-51b3-4c77-b6a7-36073d5a4e35.png" alt="drawing" width="200"/>


### Hướng tiếp cận 
Dựa trên 2 bước chính:
1. Cài đặt quá trình feedforward với bộ trọng số đã huấn luyện của mô hình U-Net để giải quyết bài toán human segmentation. \
   Các tầng layer chính: Conv2d, BatchNormalization, Activation('relu'), MaxPool2D, Conv2dTranspose. 
2. Thay thế các pixel thuộc lớp background với hình ảnh người dùng muốn thay thế
 
Tuần tự: viết code cho các layer sử dụng numpy \
Song song: sử dụng numba để tối ưu hóa code tuần tự     

![zoom5](https://user-images.githubusercontent.com/47071155/174651030-3d2a6216-8f11-4ee7-953e-9dae594b5348.jpg)
![zoom5](https://user-images.githubusercontent.com/47071155/174651046-1113c81a-2350-48c7-a774-5df50772c8cf.jpg)

_Ảnh kết quả khi xác định pixel của người dùng mô hình U-Net_

### Kế hoạch tuần 6
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky"></th>
    <th class="tg-rk9a">Main task</th>
    <th class="tg-rk9a">Sub-task</th>
    <th class="tg-rk9a">Assignee</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-9hil" rowspan="2">Tuần 6</td>
    <td class="tg-9wq8" rowspan="2">Thiết kế và viết code tuần tự cho feedforward</td>
    <td class="tg-0pky">Activation("relu"), MaxPool2D</td>
    <td class="tg-kgv7"><span style="color:#000">Nguyễn Thị Anh Đào</span></td>
  </tr>
  <tr>
    <td class="tg-0pky">Conv2d, Conv2dTranspose, BatchNormalization</td>
    <td class="tg-kgv7"><span style="color:#000">Võ Ngọc Minh</span></td>
  </tr>
</tbody>
</table>
