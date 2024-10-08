# Auth - Xác thực

(*) là tham số yêu cầu điền

## 1. Login

### Request

- Method:  POST 
- URL: /v1/auth/login
- Body: 
    - email (*): email khách hàng
    - password (*): mật khẩu khách hàng

### Response

```json
//Thành công
{
  "success": true,
  "data": {
    "access_token": "",
    "refresh_token": ""
  },
  "message": "Đăng nhập thành công"
}
//Thất bại
{
  "success": false,
  "data": "",
  "message": "Đăng nhập thất bại"
}
```

## 2. Lấy Profile Khách hàng

Cần truyền thêm token vào header của request

### Request

- Method:  GET 
- URL: /v1/auth/profile
- Header: 
    - Authorization: Bearer token

### Response

```json
{
  "success": true,
  "message": "success",
  "data": {
    "user_id": 3,
    "email": "youremail@gmail.com",
    "user_name": "ngocnguyenstore",
    "sex": 0,
    "birthday": "1999-01-01",
    "mobile_phone": "098807xxx",
    "address_id": 1
  }
}

```

## 3. Quyên mật khẩu

Khách hàng cần gửi lên email. Nếu email tồn tại, hệ thống sẽ gửi mã bảo mật qua email để khách hàng khôi phục.

### Request

- Method:  POST 
- URL: /v1/auth/forgetpassword
- Body: 
    - email (*): email khách hàng
    
### Response

```json
//Nếu thành công
{
  "success": true,
  "message": "Gửi email khôi phục mật khẩu thành công",
  "data": {
    "user_id": 1,
    "user_name" : "abc",
    "email": "youremail@gmail.com"
  },
  "links": {
    "self": "/v1/auth/forgetpassword",
    "next": "/v1/auth/getpassword"
  }
}

```

## 4. Khôi phục mật khẩu

Cần truyền thêm token vào header của request.

Mật khẩu khớp với:

```js
$pattern = '/^(?=.*[!@#$%^&*-])(?=.*[0-9])(?=.*[A-Z]).{8,20}$/'
```

### Request

- Method:  POST 
- URL: /v1/auth/getpassword
- Body: 
    - password (*): mật khẩu khách hàng
    - confirm_password (*): mật khẩu khách hàng
    - code (*): Mã bảo mật OTP gửi qua email 
    - user_id (*): User ID received at pre API
    
### Response

```json
//Nếu thành công
{
  "success": true,
  "message": "Khôi phục mật khẩu thành công",
  "data": ""
}

```


## 5. Thay đổi mật khẩu

Áp dụng cho user đã login rồi, muốn thay đổi mật khẩu.

Mật khẩu khớp với:

```js
$pattern = '/^(?=.*[!@#$%^&*-])(?=.*[0-9])(?=.*[A-Z]).{8,20}$/'
```

### Request

- Method:  POST 
- URL: /v1/auth/changepassword
- Body: 
    - new_password (*): mật khẩu mới khách hàng
    - old_password (*): mật khẩu cũ khách hàng
    
### Response

```json
//Nếu thành công
{
  "success": true,
  "message": "Đổi mật khẩu thành công"
}

```

## 6. Đăng ký Người dùng

Follow: Register --> Verify OTP --> Success

Mật khẩu khớp với:

```js
$pattern = '/^(?=.*[!@#$%^&*-])(?=.*[0-9])(?=.*[A-Z]).{8,20}$/'
```

### Request

- Method:  POST 
- URL: /v1/auth/register
- Body: 
    - email (*): email khách hàng
    - password (*): mật khẩu khách hàng
    - mobile (*): số điện thoại khách hàng
    
### Response

```json
//Nếu thành công
{
  "success": true,
  "message": "Đăng ký thành công",
  "data": {
    "user_id": 1,
    "user_name" : "abc",
    "email": "youremail@gmail.com"
  },
  "links": {
    "self": "/v1/auth/register",
    "next": "/v1/auth/verifyemail"
  }
}
//Nếu thất bại. Ví dụ
{
  "success": false,
  "message": "Email không hợp lệ"
}
```



## 7. Verify OTP


### Request

- Method:  POST 
- URL: /v1/auth/verifyemail
- Body: 
    - code (*): Code OTP
    - user_id (*): User ID received at pre API
    
### Response

```json
//Nếu thành công
{
  "success": true,
  "message": "Xác thực người dùng thành công"
}
//Nếu thất bại. Ví dụ
{
  "success": false,
  "message": "Xác thực email thất bại"
}
```



## 8. Send OTP


### Request

- Method:  POST 
- URL: /v1/auth/sendotp
- Body: 
    - user_id (*): User ID,
    - user_name (*): Username,
    - email (*): Email
    
### Response

```json
//Nếu thành công
{
  "success": true,
  "message": "Gửi mã OTP thành công",
  "data": {
    "user_id": 1,
    "user_name" : "abc",
    "email": "youremail@gmail.com"
  }
  
}
//Nếu thất bại. Ví dụ
{
  "success": false,
  "message": "Gửi mã OTP thất bại",
  "data": {
    "user_id": 1,
    "user_name" : "abc",
    "email": "youremail@gmail.com"
  }
}
```