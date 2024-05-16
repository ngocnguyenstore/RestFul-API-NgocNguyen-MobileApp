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
- Params:
    - order_id (*): ID của đơn hàng

### Response

```js
//Nếu thành công
{
  "success": true,
  "data": {...},
  "message": "success"
}

```

## 4. Hủy đơn hàng

### Request

- Method:  POST 
- URL: /v1/customers/cancel_order/:order_id
- Header: 
    - Authorization: Bearer token
- Params:
    - order_id (*): ID của đơn hàng

### Response

```js
//Nếu thành công
{
  "success": true,
  "message": "Hủy đơn hàng thành công!"
}

```

## 5. Lấy danh sách địa chỉ giao hàng

### Request

- Method:  GET 
- URL: /v1/customers/address
- Header: 
    - Authorization: Bearer token

### Response

```js
//Nếu thành công
{
  "success": true,
  "data": {
    "address_list": [
      {
        "address_id": "32",
        "address_name": "",
        "user_id": "126",
        "consignee": "toi la tester",
        "email": "tivateo@gmail.com",
        "country": "1",
        "province": "3",
        "city": "623",
        "district": "943",
        "address": "171 nguyen xi",
        "zipcode": "",
        "tel": "0988777666",
        "mobile": "",
        "sign_building": "",
        "best_time": "goi truoc khi giao"
      }
    ],
    "country_list": [
      {
        "region_id": "1",
        "region_name": "Vi\u1ec7t Nam"
      }
    ]
  },
  "message": "success"
}

```

## 6. Cập nhật địa chỉ giao hàng

### Request

- Method:  PUT 
- URL: /v1/customers/update_address/:address_id
- Header: 
    - Authorization: Bearer token
- Params:
    - address_id (*): ID của địa chỉ giao hàng
- Body:

```js
{
  "country": 1, //Require
  "province": 3, //Require
  "city": 623, //Require
  "district": 943, //Require
  "address": "171 nguyen xi", //Require
  "consignee": " toi la tester", //Require
  "email": "tivateo@gmail.com", //Require
  "tel": "0988777666", //Require
  "mobile": "0988777666", 
  "best_time": "goi truoc khi giao"
}
```

### Response

```js
//Nếu thành công
{
  "success": true,
  "message": "Cập nhật địa chỉ thành công !"
}

```