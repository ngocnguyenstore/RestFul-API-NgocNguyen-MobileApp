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
- [5. categories](v1/categories.md) - Danh mục sản phẩm (Updated)
- [6. checkout](v1/checkout.md) - Checkout đơn hàng (Updated)
- [7. customers](v1/customers.md) - Khách hàng (Updated)
- [8. navigation](v1/navigations.md) - Link điều hướng theo vị trí (Updated)
- [9. payments](v1/payments.md) - Phương thức thanh toán (Updated)
- [10. products](v1/products.md) - Sản phẩm (Updated)
- [11. regions](v1/regions.md) - Danh bạ hành chính Tỉnh thành (Updated)
- [12. shippings](v1/shippings.md) - Phương thức giao hàng (Updated)
- [13. agency](v1/agency.md) - Hệ thống chi nhánh (Updated)
- [14. settings](v1/settings.md) - Thông tin cấu hình chung (Updated)
- [15. helps](v1/helps.md) - Links trợ giúp dưới footer (Updated)
- [16. notifications](v1/notifications.md) - Thông báo (Updated)
- [17. search](v1/searach.md) - Tìm kiếm sản phẩm (Updated)
