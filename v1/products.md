# APIs Sản phẩm

(*) là tham số yêu cầu điền

## 1. Lấy danh sách sản phẩm theo danh mục

### Request

- Method:  GET 
- URL: GET /v1/products?cat_id=1&f=man-hinh-15-inch,nhu-cau-gaming
- Query String: 
    - cat_id (*): id danh mục
    - f: là tham số để lọc, mỗi giá trị lọc phân cách bằng dấu phẩy. Giá trị của bộ lọc được lấy lên từ thuộc tính lọc `filter_attrs` theo mỗi request.

### Response

```json
"success": true,
"data": {
    "filter_prices": [],
    "filter_brands": [],
    "filter_attrs" => [],
    "products_list" => [],
    "pagination" => [
        "page" => 1,
        "page_size"=> 20,
        "total_records"=> 40,
        "total_pages" =>  2
    ]
},
"query": {
    "cat_id": "1"
},
"message": "success"
```

Trong đó:

- filter_prices: Là một mảng, danh sách bộ lọc giá
- filter_brands: Là một mảng, danh sách bộ lọc theo thương hiệu
- filter_attrs: Là một mảng, danh sách bộ lọc theo thuộc tính, biến thể
- products_list: Là một mảng, danh sách sản phẩm khớp với điều kiện lọc hiện tại
- pagination: Là một mảng, phân trang



# APIs Sản phẩm

(*) là tham số yêu cầu điền

## 1. Lấy danh sách sản phẩm theo danh mục

### Request

- Method:  GET 
- URL: GET /v1/products/details/:id
- Param: 
    - id (*): id sản phẩm

### Response

```json
{
  "success": true,
  "data": {
    "goods_id": 15194,
    "is_service": false,
    "goods_sn": "15194",
    "goods_name": "Samsung Galaxy Z Fold 4 5G Qu\u1ed1c T\u1ebf [ Like New 99% ]",
    "goods_name_custom": "Samsung Galaxy Z Fold 4 5G Qu\u1ed1c T\u1ebf [ Like New 99% ]",
    "market_price": 25485000,
    "promote_price": 0,
    "promote_start_date": "0",
    "promote_end_date": "0",
    "goods_brief": "",
    "goods_desc": "",
    "time_gift": "0",
    "gift_start_date": "0",
    "gift_end_date": "0",
    "time_gift2": "0",
    "gift_start_date2": "0",
    "gift_end_date2": "0",
    "goods_gifts": "<p>T\u1eb7ng b\u1ed9 s\u1ea1c nhanh \r<\/p><p>Thu c\u0169 \u0111\u1ed5i m\u1edbi tr\u1ee3 gi\u00e1\r<\/p><p>C\u00e0i \u0111\u1eb7t ph\u1ea7n m\u1ec1m mi\u1ec5n ph\u00ed tr\u1ecdn \u0111\u1eddi\r<\/p><p>Giao h\u00e0ng COD to\u00e0n qu\u1ed1c<\/p>",
    "goods_gifts2": "",
    "goods_status": "\u0110\u00e3 qua s\u1eed d\u1ee5ng",
    "goods_cauhinh": [],
    "goods_number": 100,
    "goods_img": "https:\/\/ngocnguyen.vn\/cdn\/images\/202308\/goods_img\/samsung-galaxy-z-fold4-5g-G15194-1693040584538.jpg",
    "goods_thumb": "https:\/\/ngocnguyen.vn\/cdn\/images\/202308\/thumb_img\/samsung-galaxy-z-fold4-5g-thumb-G15194-1693040584914.jpg",
    "shop_price": 16990000,
    "measure_unit": "",
    "brand_id": "154",
    "goods_brand": "Samsung",
    "bonus_money": null,
    "comment_rank": 5,
    "rank_price": 16990000,
    "price_final": 16990000,
    "gmt_end_time": 0,
    "alepay_allow": true,
    "gallery": [],
    "specification": [],
    "pro_extra": []
  },
  "message": "success"
}
```

Trong đó:

- goods_desc: là mô tả chi tiết sản phẩm
- gallery: là danh sách hình ảnh
- specification: là danh sách các biến thể
- pro_extra: thông tin mở rộng
- goods_cauhinh: Danh sách thông số kỹ thuật
- alepay_allow: True, cho phép hiện nút trả góp
- is_service: là dịch vụ sửa chữa.