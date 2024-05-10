# Danh bạ hành chính Tỉnh thành

Bao gồm các cấp hành chính:

1. country - Quốc gia
1. province - Tỉnh/ Thành phố
1. city - Quận / Huyện
1. district - Phường / xã
1. address - địa chỉ nhà: Số nhà + Tên đường

## country - Quốc gia

Giá trị mặc định: 1

## province - Tỉnh / Thành phố

Mặc định Backend đã set country, để lấy về tất cả danh sách tỉnh thành phố có `country = 1`

### Request

- Method:  GET 
- URL: /v1/regions


### Response

```json
{
  "success": true,
  "message": "success",
  "data": [
    {
      "region_id": "2",
      "region_name": "Hà Nội"
    },
    {
      "region_id": "3",
      "region_name": "Đà Nẵng"
    },
  ]
}
```


## city - Quận / Huyện


### Request

- Method:  GET 
- URL: /v1/regions/districts/:province_id
- Params:
    - province_id (*): ID của Tỉnh / thành phố

### Response

```json
{
  "success": true,
  "message": "success",
  "data": [
    {
      "region_id": "658",
      "region_name": "Đống Đa"
    },
    {
      "region_id": "657",
      "region_name": "Hai Bà Trưng"
    },
  ]
}
```


## district - Phường / xã

### Request

- Method:  GET 
- URL: /v1/regions/wards/:district_id
- Params:
    - district_id (*): ID của Quận / Huyện

### Response

```json
{
  "success": true,
  "message": "success",
  "data": [
    {
      "region_id": "1254",
      "region_name": "Bình Yên"
    },
    {
      "region_id": "1255",
      "region_name": "Cẩm Phú"
    },
  ]
}
```