# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` |xe con |xe ô tô cỡ nhỏ |
| `truck` |xe tải |dạng xe bồn |
| `bus` |xe bus |dạng xe khách |
| `van` |xe chở hàng |to hon xe con |
## Quy tắc chung


- Box bám sát vật thể nghĩa là: vẽ bounding box sát viền vật thể
- Vật thể bị che khuất: bị các xẻ khác che một phần vật thể
- Vật thể bị cắt bởi rìa ảnh: camara khuất tầm xe
- Vật thể rất nhỏ/mơ hồ: ảnh mờ không thấy

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_002.jpg` | vật thể ở xa bị mơ hồ |bỏ qua |không thể xác định vật thể |
| `drive_007.jpg` | vật thể vị che bởi cây|gán nhãn |vẫn có thể xác định vật thể |
| `drive_017.jpg` |dãy vật thể sát nhau và mờ khó xác định biên |không gán nhãn |không thể xác định biên vật thể |
