# Tài liệu API Mobile App Ngoc Nguyen Store


## Thông tin Chung

- Live URL: https://ngocnguyen.vn/api
- Sanbox URL: https://sanbox.ngocnguyen.vn/api

Cấu trúc Request Header:

```text
content-type: application/json
X-API-Key: xxxx
```


- Cấu trúc Response

Nếu thành công:

```json
{
  "success": true,
  "data": [],
  "message": "success"
}
```

Nếu thất bại:

```json
{
  "success": false,
  "data": "",
  "message": "error message"
}
```


## Danh mục Endpoints V1

- [1. ads](v1/ads.md) - Banner quảng cáo (Updated)
- [2. articles](v1/articles.md) - Tin tức (Updated)
- [3. auth](v1/auth.md) - Authentication (Updated)
- [4. cart](v1/cart.md) - Giỏ hàng
- [5. categories](v1/categories.md) - Danh mục sản phẩm (Updated)
- [6. checkout](v1/checkout.md) - Checkout đơn hàng
- [7. customers](v1/customers.md) - Khách hàng
- [8. navigation](v1/navigations.md) - Link liên kết
- [9. payments](v1/payments.md) - Phương thức thanh toán
- [10. products](v1/products.md) - Sản phẩm (Updated)
- [11. regions](v1/regions.md) - Danh bạ hành chính Tỉnh thành (Updated)