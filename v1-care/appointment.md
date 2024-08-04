# Đặt Lịch hẹn sửa chửa

## Lấy ngày hẹn

### Request

- Method: GET
- URL: /v1/appointment/date

### Response

```json
{
  "success": true,
  "message": "success",
  "data": [
    "2024-08-04",
    "2024-08-05",
    "2024-08-06",
    "2024-08-07",
    "2024-08-08",
    "2024-08-09",
    "2024-08-10",
    "2024-08-11",
    "2024-08-12",
    "2024-08-13"
  ]
}
```

---

## Lấy giờ hẹn

### Request

- Method: GET
- URL: /v1/appointment/hours?date=2024-08-08&open=8&close=19
- Queries:
  - date (\*): Ngày hẹn
  - open: giờ bắt đầu làm việc. Tùy chọn
  - close: giờ kết thúc làm việc. Tùy chọn

### Response

```json
{
  "success": true,
  "message": "success",
  "data": [
    "8:00",
    "8:30",
    "9:00",
    "9:30",
    "10:00",
    "10:30",
    "11:00",
    "11:30",
    "12:00",
    "12:30",
    "13:00",
    "13:30"
  ]
}
```

---

## Lấy Chi nhánh

Xem API agency

---

## Tạo lịch hẹn

### Request

- Method: POST
- URL: /v1/appointment/booking
- Body:
  - name (\*): Tên khách hàng
  - tel (\*): Số điện thoại khách hàng
  - agency_id (\*): Chi nhánh sửa chửa
  - content (\*): Nội dung yêu cầu sửa chửa

### Response

```json
{
  "success": true,
  "message": "Đặt lịch hẹn thành công !",
  "data": {
    "time": "2015-08-12 8:20:00",
    "agency_name": "Chi nhanh ha noi",
    "content": "Thay man hinh iPhone"
  }
}
```
