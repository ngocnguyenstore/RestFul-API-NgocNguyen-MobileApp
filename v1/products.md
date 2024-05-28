# APIs Sản phẩm

(*) là tham số yêu cầu điền

## 1. Lấy danh sách sản phẩm theo danh mục

### Request

- Method:  GET 
- URL: GET `/v1/products?cat_id=1&f=man-hinh-15-inch,nhu-cau-gaming&rc=moi-ve&page=1&page_size=10&brand_id=1&price_min=0&price_max=5000000&sort=sort_order&order=DESC`
- Query String: 
    - `cat_id` (*): id danh mục
    - `page`: trang hiện tại, mặc định 1
    - `page_size`: số lượng sản phẩm / 1 page, mặc định theo cấu hình trong admin,
    - `brand_id`: id thương hiệu,
    - `price_min`: giá nhỏ nhấtm
    - `price_max`: giá lớn nhất
    - `rc`: lọc theo đề xuất (xem bên dưới),
    - `sort`: sắp xếp (xem bên dưới)
    - `f`: là tham số để lọc, mỗi giá trị lọc phân cách bằng dấu phẩy. Giá trị của bộ lọc được lấy lên từ thuộc tính lọc `filter_attrs` theo mỗi request.

Trong đó:


- `rc`: gồm các giá trị, mặc định không truyền
  - `moi-ve`: lọc sản phẩm mới
  - `noi-bat`: lọc sản phẩm nổi bật
  - `ban-chay`: lọc sản phẩm bán chạy

- `sort`: sắp xếp theo trường: 
  - `sort_order`: vị trí, (là mặc định)
  - `goods_id`: lọc id sản phẩm
  - `shop_price`: theo giá bán
  - `last_update`: theo ngày cập nhật

- `order`: chiều sắp xếp 
  - `DESC`: giảm dần
  - `ASC`: tăng dần



### Response

```json
"success": true,
"data": {
    "filter_prices": [],
    "filter_brands": [],
    "filter_attrs" : [],
    "filter_recommend": "rc",
    "sort_order": {
        "sortBy": "order_by",
        "orderBy": "DESC"
    },
    "products_list" : [],
    "pagination" : {
        "page" : 1,
        "page_size": 20,
        "total_records": 40,
        "total_pages":  2
    }
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



## 2. Chi tiết thông tin 1 sản phẩm

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

- is_on_sale: tính sẵn sàng bán: 1 đang bán, 0 ngừng bán
- goods_sn: mã sản phẩm
- goods_id: id sản phẩm,
- goods_status: trạng thái sản phẩm
- goods_brief: mô tả ngắn
- goods_desc: là mô tả chi tiết sản phẩm
- specification: là danh sách các biến thể
- pro_extra: thông tin mở rộng
- goods_cauhinh: Danh sách thông số kỹ thuật
- alepay_allow: True, cho phép hiện nút trả góp
- is_service: là dịch vụ sửa chữa.
- shop_price: giá bán
- market_price: giá thị trường
- promotion_price: giá khuyến mãi
- price_final: giá cuối (giá đã giảm cuối cùng)
- brand_id: id thương hiệu
- goods_gifts: quà tặng,
- time_gift: áp dụng quà tặng theo thời gian
- gift_start_date: ngày bắt đầu áp dụng quà tặng
- gift_end_date: ngày kết thúc áp dụng quà tặng
- goods_number: số lượng tồn kho
- goods_img: hình sản phẩm,
- goods_thumb: hình đại diện
- gallery: bộ sưu tập hình sản phẩm
- is_real: là sản phẩm vật lý hay ảo
- is_shipping: miễn ship
- is_best: là sản phẩm bán chạy
- is_new: là sản phẩm mới,
- is_hot: là sản phẩm hot
- is_promote: là sản phẩm khuyến mãi
- is_home: đưa sản phẩm ra Home
- is_tragop: cho phép trả góp
- meta_title: nội dung cho thẻ meta title
- meta_desc: nội dung cho meta description
- meta_robots: nội dung cho content meta robot


## 3. Lấy danh sách sản phẩm khuyến mãi trang chủ

### Request

- Method:  GET 
- URL: /v1/products/promotion

### Response

```json

{
  "success": true,
  "data": [
    {
      "goods_id": 14427,
      "goods_name": " [New 100%] Dell XPS 13 Plus 9320 Core i7 12th \/ 13.4 inch (Model 2022)",
      "seller_note": "",
      "market_price": 54225000,
      "org_price": 39150000,
      "promote_price": 36150000,
      "is_new": false,
      "is_hot": false,
      "is_best": false,
      "is_tragop": false,
      "goods_type": 26,
      "shop_price": 39150000,
      "promote_start_date": "1693176420",
      "promote_end_date": "1819406880",
      "goods_thumb": "https:\/\/ngocnguyen.vn\/cdn\/images\/202304\/thumb_img\/dell-xps-13-plus-9320-core-i7-1260p-ram-16gb-ssd-512gb-fhd-newoutlet-thumb-G14427-1682236277247.jpg",
      "goods_img": "https:\/\/ngocnguyen.vn\/cdn\/images\/202304\/goods_img\/dell-xps-13-plus-9320-core-i7-1260p-ram-16gb-ssd-512gb-fhd-newoutlet-G14427-1682236277871.jpg",
      "brand_name": "Dell",
      "rnd": "0.16381709572283282",
      "discount": "-8%",
      "comment_rank": 0,
      "comment_count": 0,
      "url": "dellxps\/new-100-dell-xps-13-plus-9320-core-i7-1260p-13-4-inch-fhd"
    },
    
  ],
  "message": "success"

}
```


## 4. Lấy danh sách tin liên quan sản phẩm

### Request

- Method:  GET 
- URL: /v1/products/articles/:product_id
- Param:
  -  product_id (*): id của sản phẩm

### Response

```json
{
  "success": true,
  "data": [
    {
      "article_id": 3771,
      "title": "C\u00e1ch k\u00edch ho\u1ea1t Slide to Shut Down tr\u00ean Windows",
      "click_count": "592",
      "article_sthumb": "https:\/\/ngocnguyen.vn\/cdn\/article_thumb\/202308\/cach-kich-hoat-slide-to-shut-down-tren-windows-sthumb-1692860106.jpg",
      "add_time": "6 th\u00e1ng tr\u01b0\u1edbc",
      "url": "cach-kich-hoat-slide-to-shut-down-tren-windows",
      "viewed": 592
    },
    
  ],
  "message": "success"
}
```

## 4. Lấy danh sách sản phẩm liên quan

### Request

- Method:  GET 
- URL: /v1/products/goodsrelate/:product_id
- Param:
  -  product_id (*): id của sản phẩm

### Response

```json
"success": true,
  "data": [
    {
      "goods_id": 3095,
      "goods_name": "Dell Alienware M15 Core i7 4th\/ GTX 980M\/ 15.6 inch (Model 2014)",
      "goods_thumb": "https:\/\/ngocnguyen.vn\/cdn\/images\/202304\/thumb_img\/dell-alienware-m15-i7-4710hq-ram-8gb-ssd-128gb-hdd-1tb-gtx-980m-156-inch-fhd-thumb-G3095-1681209656629.jpg",
      "goods_img": "https:\/\/ngocnguyen.vn\/cdn\/images\/202304\/goods_img\/dell-alienware-m15-i7-4710hq-ram-8gb-ssd-128gb-hdd-1tb-gtx-980m-156-inch-fhd-G3095-1681209656697.jpg",
      "seller_note": "",
      "is_new": false,
      "is_best": false,
      "is_hot": false,
      "is_tragop": false,
      "org_price": 23900000,
      "shop_price": 23900000,
      "market_price": 0,
      "promote_price": 0,
      "promote_start_date": "0",
      "promote_end_date": "0",
      "discount": 0,
      "url": "dellalienware\/dell-alienware-m15-core-i7-4th-gtx-980m-15-6-inch-model-2014"
    },
   
  ],
  "message": "success"
}
```


## 5. Lấy danh sách sản phẩm cùng danh mục

### Request

- Method:  GET 
- URL: /v1/products/goodsrelate/:product_id/:cat_id
- Params:
  -  product_id (*): id của sản phẩm
  -  cat_id (*): id của danh mục

### Response

```json
{
  "success": true,
  "data": [
    {
      "goods_id": 15212,
      "goods_name": "[New 100%] Samsung Galaxy Z Flip 5 5G",
      "rnd": "0.1379601649362223",
      "goods_thumb": "https:\/\/ngocnguyen.vn\/cdn\/images\/202308\/thumb_img\/new-100-samsung-galaxy-z-flip5-5g-thumb-G15212-1693212165005.jpg",
      "goods_img": "https:\/\/ngocnguyen.vn\/cdn\/images\/202308\/goods_img\/new-100-samsung-galaxy-z-flip5-5g-G15212-1693212165955.jpg",
      "seller_note": "",
      "is_new": false,
      "is_best": false,
      "is_hot": false,
      "is_tragop": false,
      "org_price": 17500000,
      "shop_price": 17500000,
      "market_price": 26250000,
      "promote_price": 0,
      "promote_start_date": "0",
      "promote_end_date": "0",
      "discount": 0,
      "url": "samsung-galaxy-z\/new-100-samsung-galaxy-z-flip-5-5g"
    },
    
  ],
  "message": "success"
}
```

## 5. Lấy danh sách comments sản phẩm

### Request

- Method:  GET 
- URL: /v1/products/comments/:product_id
- Params:
  -  product_id (*): id của sản phẩm

### Response

```json
{
  "success": true,
  "data": {
    "comments": [
      {
        "comment_id": 252,
        "id_value": 15194,
        "email": "john@mail.com",
        "user_name": "nguyen van a",
        "content": "s\u1ea3n ph\u1ea9m r\u1ea5t ok",
        "add_time": "14-12-2023 10:26:05",
        "reply": [],
        "photos": []
      }
    ],
    "pagination": {
      "page": 1,
      "page_size": 5,
      "total_records": 1,
      "total_pages": 1
    }
  },
  "message": "success"
}
```

## 6. Lấy danh sách reviews sản phẩm

### Request

- Method:  GET 
- URL: /v1/products/reviews/:product_id
- Params:
  -  product_id (*): id của sản phẩm

### Response

```json
{
  "success": true,
  "data": {
    "reviews": [
      {
        "comment_id": 246,
        "id_value": 15194,
        "email": "",
        "user_name": "Hoa B\u1eb1ng",
        "content": "R\u1ea5t th\u00edch thi\u1ebft k\u1ebf em n\u00e0y",
        "add_time": "11-11-2023 19:05:16",
        "is_buy": false,
        "reply": [],
        "photos": []
      },
     
    ],
    "pagination": {
      "page": 1,
      "page_size": 5,
      "total_records": 2,
      "total_pages": 1
    }
  },
  "message": "success"
}
```

## 7. Thêm mới comment/review 

Đang cập nhật