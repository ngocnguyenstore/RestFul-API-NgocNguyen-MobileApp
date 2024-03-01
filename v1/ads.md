# ADS API

(*) là tham số yêu cầu điền

## Lấy danh sách banner theo vị trí quảng cáo

### Request

- Method:  GET 
- URL: /v1/ads/:position_id?limit=5
- Params: 
  - position_id (*): id của vị trí quảng cáo
- Query String: 
    - limit: số lượng banner cần lấy


### Response

```json
{
  "success": true,
  "data": [
    {
      "ad_id": 109,
      "position_id": 1,
      "ad_link": "watch.html",
      "ad_code": "https:\/\/ngocnguyen.vn\/cdn\/data\/afficheimg\/apple-watch-1693986186.png",
      "ad_name": " Apple Watch"
    },
    {
      "ad_id": 107,
      "position_id": 1,
      "ad_link": "gia-dung-nha-bep.html",
      "ad_code": "https:\/\/ngocnguyen.vn\/cdn\/data\/afficheimg\/do-gia-dung-xiaomi-1698044467.png",
      "ad_name": "\u0110\u1ed3 Gia D\u1ee5ng Xiaomi"
    }
  ],
  "message": "success"
}
```