# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` | Xe con chở người, thân liền khối, cỡ nhỏ đến vừa. Gồm cả xe bán tải. | Sedan, hatchback, SUV, taxi, bán tải. Thấp và thon hơn `van`; không có thùng hàng tách riêng như `truck`. |
| `truck` | Xe tải chở hàng, có cabin tách biệt với thùng hàng phía sau; gồm xe đầu kéo. | Tải thùng kín, thùng lửng, xe chở hàng chất cao. Cabin và thùng là hai khối riêng, khác `van` (thân liền khối). |
| `bus` | Xe buýt, xe khách, minibus chở khách; thân dài, nhiều cửa sổ dọc thân. | Buýt thành phố, buýt hai khúc nối. Dài và cao hơn hẳn `van`, nhiều cửa sổ liên tiếp. |
| `van` | Xe thân hộp cỡ vừa, cabin và khoang sau liền khối, chở hàng hoặc chở người. | Xe van, minivan. Cao và vuông hơn `car`, ngắn và thấp hơn `bus`. Nếu mơ hồ với `bus` hoặc `car` thì không tự chọn, ghi lại và hỏi giảng viên. |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: mỗi xe một box riêng, cạnh box chạm sát phần thân xe nhìn thấy được, không lấy thêm mặt đường, trời hay xe bên cạnh, không gộp hai xe thành một box.
- Vật thể bị che khuất: vẫn gán box quanh phần nhìn thấy được nếu nhận ra được lớp. Vật che mảnh (như cột đèn) chạy ngang giữa xe thì vẫn vẽ một box ôm toàn bộ xe. Hai xe chồng lên nhau thì vẽ hai box riêng trên phần nhìn thấy của từng xe.
- Vật thể bị cắt bởi rìa ảnh: vẫn gán, box chạm đúng rìa ảnh, không đoán phần nằm ngoài ảnh.
- Vật thể rất nhỏ/mơ hồ: nếu chỉ còn là mảng mờ, không thể xác định chắc đó là xe hay thuộc lớp nào thì không tự đoán, không gán, ghi vào bảng ca mơ hồ và hỏi giảng viên. Ngưỡng kích thước đã dùng: [ĐIỀN NGƯỠNG THẬT BẠN ĐÃ DÙNG, ví dụ "box nhỏ hơn khoảng ... px thì không gán"], áp dụng nhất quán cho cả 50 ảnh.
- Không gán: người đi bộ, xe đạp, mô tô/xe máy, xe ba bánh, biển báo, đèn giao thông, phản chiếu trong kính/gương, hình xe trên bảng quảng cáo. Xe đang đỗ vẫn gán theo loại xe.

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_001` | Xe con ở làn gần bị cột đèn mảnh che dọc giữa thân xe. | Một box `car` ôm toàn bộ xe, không tách hai box ở hai bên cột. | Cột chỉ che một dải hẹp, xe vẫn nhận ra rõ. Quy tắc mỗi xe một box ôm phần nhìn thấy. |
| `drive_017` | Xe rất nhỏ, mờ sau hàng cây (cạnh khoảng 30 px), có một xe nghi `van` hay `car` nhưng không chắc. | Không gán các xe quá nhỏ/mờ này. Ca nghi `van` thì không tự chọn lớp, ghi lại để hỏi giảng viên. | Quy tắc không tự đoán khi không xác định chắc xe hay lớp. Với `van` mơ hồ, GUIDE yêu cầu ghi case ID và hỏi. |
| `drive_042` | Xe con màu tím nhỏ bị xe buýt che phía dưới, ban đầu bị gán nhầm là `bus`. | Sửa thành `car`, box ôm phần nhìn thấy của xe. | Lớp mô tả loại vật thể, không mô tả trạng thái bị che. Phần thân nhìn thấy đủ để nhận ra là xe con. |
| `drive_042` | Xe tải chở hàng chất cao hơn cabin, box ban đầu chỉ ôm cabin và thân dưới. | Giữ `truck`, kéo cạnh trên box lên tới đỉnh đống hàng; box chạm rìa ảnh ở phía bị cắt. | Hàng chất trên thùng là phần xe nhìn thấy được; box phải ôm sát toàn bộ phần nhìn thấy. |
