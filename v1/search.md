# Tìm kiếm sản phẩm

## Request

- Method: GET
- URL: /v1/search?keywords=laptop
- Query:
  - keywords (\*): Từ khóa cần tìm

## Response

```js
{
  "success": true,
  "data":
    {
      "products_list": [], //Mảng sản phẩm
      "pagination": {}, //Các thuộc tính phân trang
      "query": {}, //Danh sách các query string
    }
  ,
  "message": "success"
}
```
