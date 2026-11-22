# Khai báo dùng AI — Nguyễn Thảo Linh

Không đưa ảnh cabin hoặc ảnh tài xế cho công cụ AI. Các nội dung dưới đây là trao đổi bằng văn bản; kết quả kiểm tra được chạy cục bộ bằng `cabin_check`.

| # | Công cụ | Bạn hỏi gì (tóm tắt) | Bạn dùng kết quả thế nào | Bạn có kiểm lại không? Bằng gì? |
|---|---|---|---|---|
| 1 | Copilot trong VS Code | Hỏi `frame_meta` có cần cho ảnh OMS không và cách chạy checkpoint A, B, checkpoint cuối | Dùng hướng dẫn để chạy các lệnh kiểm tra trên file export cục bộ | Có; đối chiếu GUIDE/CHECKPOINTS và xem kết quả `cabin_check` |
| 2 | Copilot trong VS Code | Hỏi cách thực hiện review chéo giữa export của mình và peer | Chạy `cabin_check diff` và xem `disagreement_log.csv` | Có; lệnh báo 22 ảnh chung và 0 điểm khác |

