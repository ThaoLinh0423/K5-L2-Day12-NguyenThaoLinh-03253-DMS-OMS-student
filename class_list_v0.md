# Danh sách lớp v0 — Nguyễn Thảo Linh · G03

## DMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | eye_state | open / closed / unknown | Phát hiện mắt nhắm kéo dài để cảnh báo buồn ngủ | Thường thấy; có thể bị kính hoặc phản xạ che |
| 2 | gaze_zone | road / mirror_l / mirror_r / mirror_c / cluster / center / lap / other | Phát hiện tài xế nhìn khỏi đường hoặc mất tập trung | Một phần; phụ thuộc hướng đầu, mắt và phản xạ |
| 3 | glasses | none / clear / sun / unknown | Hỗ trợ diễn giải độ tin cậy của nhận diện mắt và hướng nhìn | Thường thấy nhưng NIR có thể làm kính râm trông trong suốt |
| 4 | face13 | 13 điểm mặt; mỗi điểm có cờ occluded / outside | Xác định cấu trúc mặt để hỗ trợ ước lượng hướng đầu và trạng thái mắt | Có nếu mặt đủ lớn và điểm không bị che |
| 5 | hand | whose, side, on_wheel: yes / no / unknown | Theo dõi tay tài xế và việc tay có chạm vô lăng hay không | Thường thấy nếu tay không bị che |
| 6 | phone | held / mounted / lap | Phát hiện sử dụng điện thoại khi lái xe | Có khi thấy cạnh, góc hoặc màn hình; không suy đoán từ vật tối |
| 7 | seatbelt | worn_correct / worn_incorrect / not_worn / unknown | Theo dõi việc thắt dây an toàn của tài xế | Có thể thấy; nếu tối hoặc bị che thì unknown |

## OMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | person | box người; thuộc tính seat | Phát hiện người và xác định vị trí ngồi trong xe | Thường thấy theo hình dáng; ảnh tối hoặc che khuất làm giảm độ rõ |
| 2 | seat | driver / front_passenger / rear_left / rear_middle / rear_right | Xác định vị trí người hoặc vật để hỗ trợ giám sát từng ghế | Thường thấy theo vị trí; phải quy đổi trái/phải theo xe |
| 3 | seatbelt | worn_correct / worn_incorrect / not_worn / unknown | Kiểm tra trạng thái dây an toàn của người ngồi | Có thể khó thấy trên ảnh IR tối hoặc khi dây chìm trong bóng |
| 4 | child_seat | occupied: no / unknown | Phát hiện ghế trẻ em và hỗ trợ nhắc kiểm tra ghế | Hình dáng thường thấy; bên trong có thể không rõ |
| 5 | infant_seat | facing: rear / front | Phát hiện nôi em bé và hướng quay để hỗ trợ kiểm tra an toàn | Thường nhận ra theo hình dáng; hướng quay cần thấy đủ hình |
| 6 | object | type: bag / box / cup / other | Phát hiện đồ vật bị bỏ lại trong cabin hoặc đặt trên ghế | Hình dáng có thể thấy; không dùng màu để suy loại trên IR |

## 2 câu hỏi leo thang

1. Câu hỏi: Nếu một vật chỉ phân biệt được trên một ảnh trong cặp RGB/IR-sim thì có cần quy tắc bổ sung nào cho việc ghi chú đối chiếu, ngoài việc gán từng ảnh theo bằng chứng trực tiếp?
   Khung ví dụ: S02_rgb và S02_ir.
   Bạn tạm gán thế nào và vì sao: Không chuyển nhãn từ ảnh này sang ảnh kia; chỉ gán khi vật nhìn thấy trên ảnh đang xét, vì guideline yêu cầu không suy từ ảnh cặp.
2. Câu hỏi: Khi một mắt bị phản xạ che nhưng hướng đầu vẫn nhìn rõ, mức độ nào của bằng chứng là đủ để gán gaze_zone khác `other`?
   Khung ví dụ: D03.png.
   Bạn tạm gán thế nào và vì sao: Chọn `other` nếu không xác định chắc vùng nhìn; ghi lý do, không suy đoán hướng mắt từ mắt còn lại.
