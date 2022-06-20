## CSC14116

## Lập trình song song ứng dụng

### Tổng quan

Làm mở hoặc thay đổi background(hậu cảnh) là một trong những ứng dụng cần thiết trong bối cảnh hậu đại dịch Covid, khi mà càng có nhiều cuộc họp được thực hiện trực tuyến mà người dùng muốn có một không gian họp riêng tư ngay trong chính căn phòng của mình. Việc thay đổi background gồm 2 bước chính là xác định khung viền bọc xung quanh người, sau đó tùy theo làm mờ hay thay đổi background mà có thể nhân ma trận để làm mờ hoặc ghép hình người vào một khung cảnh khác.

### Động lực

Việc thay đổi background có thể làm tốn rất nhiều tài nguyên nếu được thực hiện tuần tự trên CPU do mỗi giây trên video có rất nhiều khung hình cần được tính toán mà tài nguyên của CPU thì có hạn. Vì thể chúng tôi mong muốn có thể giả lập lại việc thay đổi background chạy song song trên GPU để tăng tốc quá trình xử lý, từ đó có thể đạt được hiệu năng như các ứng dụng họp online như Zoom, Google Meet, ...

### Input

Hình ảnh, Video ghi lại hình người trong các cuộc họp trực tuyến.

### Output

Hình ảnh, Video đã được làm mờ background.
