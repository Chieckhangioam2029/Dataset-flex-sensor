# Dữ liệu khảo sát cảm biến uốn SEN-10264

Dữ liệu đo điện trở của cảm biến uốn SparkFun SEN-10264 (2,2 inch) khi uốn trong khoảng 0–90°, dùng cho bài tập lớn môn Kỹ thuật đo lường và cảm biến.

## Thiết bị đo

- Cảm biến kẹp giữa hai tay đòn in 3D, góc đặt bằng thước đo góc điện tử (±0,5°).
- Mạch phân áp 5 V: ba điện trở 100 kΩ ±1% nối tiếp phía trên, cảm biến phía dưới, đọc bằng ADC 10 bit của Arduino Uno (chân A1).
- Điện trở tính theo R = 300 kΩ · ADC / (1023 − ADC).
- Nhiệt độ đọc từ DHT22.
- Chu kỳ lấy mẫu 400 ms, mỗi góc ghi 400 mẫu.

## Các file

| File | Nội dung |
|---|---|
| `data_chinh.txt` | Bộ dữ liệu chính, 261 khối góc. Lần 1 và lần 2: 0→90° rồi 90→0°. Lần 3: tương tự, có đặt nam châm quay gần cảm biến. |
| `do_thu.txt` | Hai lượt đo thử 0→90→0°, thực hiện trước bộ dữ liệu chính. |

## Định dạng

Mỗi khối ứng với một góc. Dòng đầu khối là nhãn góc (ví dụ `0 độ`), tiếp theo là dòng tiêu đề và 400 dòng mẫu:

```
STT,ADC,Voltage_V,Resistance_Ohm,Temperature_C
1,456,2.2287,241269.84,24.20
```

Cuối khối là các dòng tổng hợp do Arduino in (trung bình, độ lệch chuẩn). Nên tính lại các đại lượng này từ 400 dòng mẫu thô thay vì dùng các dòng đó.
