# Phương thức thanh toán

## Danh sách phương thức thanh toán

### Request

- Method:  GET 
- URL: /v1/payments


### Response

```json
{
  "success": true,
  "data": [
    {
      "pay_id": 1,
      "pay_name": "Tên payment 1",
      "pay_desc": "Mô tả payment 1"
    },
    {
      "pay_id": 2,
      "pay_name": "Tên payment 2",
      "pay_desc": "Mô tả payment 2"
    }
  ],
  "message": "success"
}
```