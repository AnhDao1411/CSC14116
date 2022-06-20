## CSC14116 - Lập trình song song ứng dụng

### Tổng quan
Làm mở hoặc thay đổi background(hậu cảnh) là một trong những ứng dụng cần thiết trong bối cảnh hậu đại dịch Covid, khi mà càng có nhiều cuộc họp được thực hiện trực tuyến mà người dùng muốn có một không gian họp riêng tư ngay trong chính căn phòng của mình. Việc thay đổi background gồm 2 bước chính là xác định khung viền bọc xung quanh người, sau đó tùy theo làm mờ hay thay đổi background mà có thể nhân ma trận để làm mờ hoặc ghép hình người vào một khung cảnh khác.

### Động lực
Chúng tối thấy việc thay đổi background khá thiết thực và được sử dụng nhiều trong thời đại công nghệ hiện nay. Bên cạnh đó công việc này cũng có thể phân ra thành các bước áp dụng được song song hóa, từ đó cải thiện tốc độ xử lý vấn đề. 

### Vì sao cần song song hóa ?
Việc thay đổi background có thể làm tốn rất nhiều tài nguyên nếu được thực hiện tuần tự trên CPU do mỗi giây trên video có rất nhiều khung hình cần được tính toán mà tài nguyên của CPU thì có hạn. Vì thể chúng tôi mong muốn có thể giả lập lại việc thay đổi background chạy song song trên GPU để tăng tốc quá trình xử lý, từ đó có thể đạt được hiệu năng như các ứng dụng họp online như Zoom, Google Meet, ...

### Input
Hình ảnh, Video người dùng trong các cuộc họp trực tuyến và hình ảnh background người dùng muốn thay thế.

### Output
Hình ảnh, Video đã được thay đổi background.


<img src="https://user-images.githubusercontent.com/50958253/174557063-b2699158-4098-4929-b501-bc23eb55f2b0.png" alt="drawing" width="200"/> + <img src="https://user-images.githubusercontent.com/50958253/174557523-737ec1d9-5514-4a00-9d6f-6b0440eaf718.png" alt="drawing" width="200"/>
 = <img src="https://user-images.githubusercontent.com/50958253/174557505-e5784dcb-51b3-4c77-b6a7-36073d5a4e35.png" alt="drawing" width="200"/>
