# Tự đánh giá — Nguyễn Thảo Linh · G03

## 1. Tự rà soát 4 cảnh

Các phát hiện dưới đây dựa trên kết quả `cabin_check` của `export_final.zip`. Cần mở lại các ảnh trong CVAT sau khi sửa để xác nhận trực quan.

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S01_rgb | child_seat | wrong_class | `occupied=yes` không hợp lệ; đổi thành `no` nếu thấy rõ ghế trống hoặc `unknown` nếu không rõ | Chưa xác nhận |
| S03_ir | child_seat | wrong_class | `occupied=yes` không hợp lệ; đổi thành `no` nếu thấy rõ ghế trống hoặc `unknown` nếu không rõ | Chưa xác nhận |
| D03 | face / mắt phải | guess | `eye_right=open` trong khi cả 4 điểm `right_eye_*` được đánh dấu che; nếu không thấy mắt thì dùng `unknown` | Chưa xác nhận |
| D06 | frame_meta | missing | Thiếu tag `frame_meta` | Chưa xác nhận |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

Lỗi: Để `occupied=yes` cho `child_seat`; cabin_check phát hiện lỗi này ở S01, S03 và S07.

Vì sao mình mắc: Chưa xác định được nguyên nhân cụ thể; có thể mình đã chọn nhầm hoặc không rà lại giá trị thuộc tính.

Lần sau tránh bằng cách: Kiểm tra từng `child_seat` ngay sau khi vẽ, chỉ chọn `no` hoặc `unknown`, rồi chạy `cabin_check` sau mỗi nhóm ảnh.

## 3. Ghi chú về disagreement_log

Review chéo giữa hai export có 0 điểm khác và `disagreement_log.csv` không có dòng bất đồng. Vì vậy hiện chưa có ví dụ để kết luận bạn review đúng còn mình sai.
