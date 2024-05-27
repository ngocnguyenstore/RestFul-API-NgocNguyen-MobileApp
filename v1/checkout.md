# Checkout

Quy trình mua hàng của shop

1. Lựa chọn sản phẩm
1. Thêm sản phẩm vào giỏ hàng
1. Xem giỏ hàng
1. Điền thông tin khách hàng
 - Khách chưa phải thành viên: có thể điền trực tiếp vào form thông tin khách hàng
 - Khách hàng đã thành viên: Có thể login để lấy thông tin khách hàng.
5. Chọn phương thức thanh toán, giao hàng
6. Checkout đơn hàng

Lưu ý:

- Phí ship: không cần tính
- Discount: chưa áp dụng tại thời điểm này

## Request

- Method:  POST 
- URL: /v1/checkout
- Header:
  - Authorization: Bearer token (Tùy chọn, khi khách hàng có login thì truyền thêm token)
- Body

```js
{   
    "cart_goods": [
        {
            "goods_id": 15066, //ID sản phẩm
            "goods_name": "Surface Pro 8 Core i5 1135G7 /13 inch QHD (Model 2021)", //Tên sản phẩm
            "goods_sn": "15066", //Mã sản phẩm
            "goods_number": 1, //Số lượng chọn mua
            "goods_price": 13990000.00, //giá sản phẩm
            "market_price": 20985000.00,
            "goods_attr": "Cấu hình:Core i5/8G/128G-Màu :Graphite ( Xám ) ", //Danh sách tên các thuộc tính, nối vào nhau
            "is_real": 1, //Loại sản phẩm số hay vật lý
            "extension_code": "", //Để mặc định
            "parent_id": 0, //Để mặc định
            "is_gift": 0, //Để mặc định
            "is_shipping": 0, //Miễn ship hay không cho riêng sản phẩm ? 0 Không, 1 có.
            "goods_attr_id": "28864,26730" //Danh sách ID của thuộc tính được chọn, cách nhau bằng dấy phẩy
            //... Có thể bổ sung các trường khác: Ví dụ: goods_thumb
        }
        //...
    ],
    "consignee": {
        "consignee": "ngoc nhan test dev 1", //Tên khách hàng
        "country": 1, //ID quốc gia
        "province": 3, //ID Tỉnh thành phố
        "city": 627, //ID quận huyện
        "district": 910, //ID phường xã
        "address": "Địa chỉ khách hàng", //Địa chỉ
        "email": "nhannnbkc@gmail.com", //email
        "zipcode": "", //Để rỗng
        "tel": "0988071777", // Số điện thoại
        "mobile": "", //Để rỗng
        "sign_building": "", //Để rỗng
        "best_time": "đây là nội dung ghi chú thời gian giao hàng"
    },
    "shipping": 12, //ID phương thức giao hàng đã chọn
    "payment": 14, //ID phương thức thanh toán đã chọn
    "bonus_sn": "", //Để rỗng
    "voucher_code": "", //Để rỗng
    "voucher_sn": "", //Để rỗng
    "voucher_id": "" //Để rỗng
}
```


## Responsive

```js
{
    success: true,
    data: {
        order: {}, //Thông tin đơn hàng
        consignee: {}, //Thông tin khách hàng
        cart_goods: [] //Sản phẩm đã mua
    },
    message: "Tạo mới đơn hàng thành công !"
}
```