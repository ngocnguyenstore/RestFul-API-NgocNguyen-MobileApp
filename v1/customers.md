# API về khách hàng 

## 1. Thay đổi thông tin khách hàng

### Request

- Method:  PUT 
- URL: /v1/auth/profile
- Header: 
    - Authorization: Bearer token
- Body: 
    - email (*): email khách hàng
    - sex (*): giới tính khách hàng (0 = Bí mật, 1 = Nam, 2 = Nữ)
    - mobile_phone (*): số điện thoại khách hàng
    - birthday (*): Ngày sinh nhật. Định dạng yyyy-mm-dd
    
### Response

```js
//Nếu thành công
{
  "success": true,
  "message": "Đổi mật khẩu thành công"
}

```

## 2. Lấy danh sách đơn hàng

### Request

- Method:  GET 
- URL: /v1/customers/orders
- Header: 
    - Authorization: Bearer token
  
### Response

```js
//Nếu thành công
{
  "success": true,
  "data": [
      {
        "order_id": 919,
        "order_sn": "2024051521038",
        "order_time": "15-05-2024 15:47:48",
        "order_status": "\u0110\u00e3 b\u1ecb h\u1ee7y,Ch\u01b0a thanh to\u00e1n,Ch\u01b0a giao h\u00e0ng",
        "shipping_status": 0,
        "total_fee": "4620000.00",
        "handler": "\u0110\u00e3 b\u1ecb h\u1ee7y,"
      },
  ],
  "message": "success"
}

```



## 3. Chi tiết đơn hàng

### Request

- Method:  GET 
- URL: /v1/customers/order_detail/:order_id
- Header: 
    - Authorization: Bearer token
  
### Response

```js
//Nếu thành công
{
  "success": true,
  "data": {...},
  "message": "success"
}

```