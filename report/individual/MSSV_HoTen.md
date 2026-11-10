# Báo cáo cá nhân — Ngày 2 Object Detection

Đổi tên file theo `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md`. Điền kết quả thật, xóa dòng hướng dẫn khi nộp. Xem [quy định nộp](../../SUBMISSION.md).

## 1. Thông tin học viên

- Họ tên:Bùi Sỹ Tùng
- MSSV:2A202603323
- Email:buisytungk25cntt@gmail.com
- Lớp:K5-L2
- Link repo bài làm:https://github.com/BuffDarkAI/K5-L2-Day02-BUISYTUNG_2A202603323_ObjectDetection.git
- Link Colab đã chạy:https://colab.research.google.com/drive/1GROoB-OZEnmI3K-ebzBWs9Kj97AOo354?hl=vi#scrollTo=6f78b880

## 2. Schema và mini guideline

Dẫn tới [GUIDELINE_MINI.md](../../GUIDELINE_MINI.md). Tóm tắt ba ca mơ hồ đã quyết định, cách áp dụng schema và phần cần giảng viên làm rõ.

## 3. Annotation và self-QC

- Số file nhãn train:50 file
- Kết quả checker và lỗi đã xử lý:Không có file nhãn bị thiếu, Điều chỉnh một số bounding box quá chật hoặc quá rộng
- Danh sách ít nhất 10 ảnh đã rà bằng mắt:drive_001.jpg
drive_005.jpg
drive_010.jpg
drive_012.jpg
drive_019.jpg
drive_024.jpg
drive_026.jpg
drive_030.jpg
drive_041.jpg
drive_050.jpg
- Lỗi bỏ sót/box/class phát hiện khi rà và cách sửa:
Bỏ sót xe nhỏ ở xa thêm bounding box
- Commit khóa nhãn ban đầu:

## 4. Gold QC và rework

| Chỉ số | Trước sửa | Sau sửa nếu có |
|---|---:|---:|
| TP |Chưa đo | |
| FP |Chưa đo | |
| FN | Chưa đo| |
| Precision | Chưa đo| |
| Recall |Chưa đo | |
| F1 |Chưa đo | |
| mean_iou_of_matches |Chưa đo | |
| passed |Chưa xác định | |

Dẫn tới `outputs/annotation_evaluation.json` trong repo. Nếu rework, ghi ảnh, lỗi đã kiểm, quyết định sửa/giữ và lý do. Không suy nguyên nhân chỉ từ FP/FN. Không có rework thì ghi rõ.

## 5. Kết quả YOLO

- Runtime, GPU/CPU, phiên bản Ultralytics và Torch:
- Các tham số thay đổi so với notebook nếu có và lý do:
- Đường dẫn best checkpoint trong phiên chạy:

| Chỉ số trên 10 ảnh eval | Giá trị |
|---|---:|
| Precision |0.411 |
| Recall |0.230 |
| mAP50 |0.272 |
| mAP50–95 | 0.201|

Đặt cả 2 folder `assets/eval_predictions/` và `assets/yolo26_runs/` (giải nén từ `day2_colab_outputs.zip`) cạnh báo cáo và dẫn link tương đối. Không chỉ ghi số; chỉ ra ít nhất một ảnh và vật thể cụ thể.

Trả lời bốn câu hỏi cuối notebook:

1. Lớp nào recall thấp nhất? Ảnh nào minh họa?
 lớp bus, drive_058
2. Nếu mAP50 cao nhưng mAP50–95 thấp, cần kiểm điều gì trên box?
- mAP50 chỉ yêu cầu IoU ≥ 0.5.
- mAP50-95 đánh giá ở nhiều ngưỡng IoU từ 0.5 đến 0.95.
cần kiểm box quá rộng chứa nhiều nền, box quá chật cắt mất vật thể,box lệch tâm, box không bao hết phương tiện
3. Lỗi class nào có thể liên quan guideline? Dữ kiện nào hỗ trợ nhận xét?
Các lớp truck, bus và van có khả năng bị ảnh hưởng bởi việc hiểu guideline chưa thống nhất
truck có recall:	0.200 và mAP50:	0.239
4. Vì sao không dùng 10 ảnh eval để train? Vai trò validation của chúng trong notebook là gì?
đánh giá hiệu năng của mô hình trên dữ liệu chưa từng xuất hiện trong train,
so sánh các phiên bản mô hình, phát hiện hiện tượng overfitting, kiểm chứng chất lượng annotation trước khi triển khai huấn luyện thực tế.
Không sử dụng 10 ảnh eval để train nhằm đảm bảo việc đánh giá mô hình là khách quan

## 6. Khó khăn và cách xử lý

| Bước/thời điểm | Lỗi quan sát | Cách đã thử | Kết quả/còn thiếu |
|---|---|---|---|
|Gán nhãn dữ liệu | Một số xe bị che khuất hoặc xuất hiện rất nhỏ|Phóng to ảnh và rà thủ công từng đối tượng | Phóng to ảnh và rà thủ công từng đối tượng|

## 7. Tự đánh giá theo rubric

Đối chiếu [RUBRIC.md](../../RUBRIC.md): phần nào đã có kết quả, phần nào còn thiếu hoặc chưa kiểm được. Không tự nhận hoàn thành bước chưa chạy.

## 8. Công cụ AI và tài liệu tham khảo

Ghi công cụ đã dùng, dùng ở bước nào và phần đã tự kiểm tra; không dùng thì ghi rõ. Liệt kê nguồn ngoài repo được sử dụng. Không ghi mật khẩu/token hoặc đính kèm gold train.

-không dùng công cụ nào khác ngoài cvat và kiểm thử bằng tay
