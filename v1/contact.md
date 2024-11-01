# Liên hệ

## Gửi liên hệ

### Request

- Method:  POST 
- URL: /v1/contact
- Body: 
    - user_name (*): tên khách hàng
    - user_email (*): Email khách hàng
    - user_tel (*): số điện thoại khách hàng
    - msg_type (*): 0=Tin nhắn, 1=Than phiền, 2=Tư vấn, 3=Khác, 4=Mua hàng
    - msg_title (*): Tiêu đề tin nhắn
    - msg_content (*): Nội dung tin nhắn

```js
{
    "user_name": "user_name",
    "user_email": "useremail@gmail.com",
    "user_tel": "user_tel",
    "msg_type": 0,
    "msg_title": "msg_title msg_title",
    "msg_content": "msg_content"
}
```

### Response

```js
//Nếu thành công
{
  "success": true,
  "message": "Gửi liên hệ thành công"
}

//Nếu thất bại
{
  "success": true,
  "message": "Gửi liên hệ không thành công"
}
```