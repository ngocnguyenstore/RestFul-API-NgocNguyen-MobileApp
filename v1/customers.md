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

```json
//Nếu thành công
{
  "success": true,
  "message": "Đổi mật khẩu thành công"
}

```