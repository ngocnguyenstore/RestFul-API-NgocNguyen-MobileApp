# APIs tin tức

(*) là tham số yêu cầu điền

## 1. Lấy danh sách Danh mục tin tức

### Request

- Method:  GET 
- URL: /v1/articles/categories


### Response

```json
{
  "success": true,
  "data": [
    {
      "id": 46,
      "name": "Th\u1ee7 Thu\u1eadt Hay",
      "url": "thu-thuat-hay"
    },
    {
      "id": 1786,
      "name": "\u0110\u00e1nh gi\u00e1 Review",
      "url": "danh-gia-reivew"
    },
    ...
  ],
  "message": "success"
}
```

## 2. Lấy danh sách tin tức theo danh mục

### Request

- Method:  GET 
- URL: /v1/articles?cat_id=4&page=1&limit=10
- Query String: 
    - cat_id (*): id danh mục cần lấy
    - page: số trang hiện tại, mặc định 1.
    - limit: số lượng tin trên 1 trang, mặc định bằng cấu hình.


### Response

```json
{
  "success": true,
  "data": {
    "filters": {
      "cat_id": 4,
      "keywords": ""
    },
    "article_list": [
      {
        "article_id": 3771,
        "title": "C\u00e1ch k\u00edch ho\u1ea1t Slide to Shut Down tr\u00ean Windows",
        "author": "Ng\u1ecdc Nguy\u1ec5n Store",
        "add_time": "6 th\u00e1ng tr\u01b0\u1edbc",
        "description": "",
        "article_thumb": "https:\/\/ngocnguyen.vn\/cdn\/article_thumb\/202308\/cach-kich-hoat-slide-to-shut-down-tren-windows-thumb-1692860106.jpg",
        "article_sthumb": "https:\/\/ngocnguyen.vn\/cdn\/article_thumb\/202308\/cach-kich-hoat-slide-to-shut-down-tren-windows-sthumb-1692860106.jpg",
        "click_count": 592,
        "url": "cach-kich-hoat-slide-to-shut-down-tren-windows"
      }
    ],
    "pagination": {
      "page": 1,
      "page_size": 10,
      "total_records": 195,
      "total_pages": 20
    }
  },
  "message": "success"
}
```



## 3. Chi tiết 1 bài tin tức

### Request

- Method:  GET 
- URL: /v1/articles/details/:id
- Params: 
    - id (*): id bài tin tức


### Response

```json
{
  "success": true,
  "data": {
    "article_id": 3771,
    "title": "C\u00e1ch k\u00edch ho\u1ea1t Slide to Shut Down tr\u00ean Windows",
    "custom_title": "",
    "content": "",
    "article_thumb": "https:\/\/ngocnguyen.vn\/cdn\/article_thumb\/202308\/cach-kich-hoat-slide-to-shut-down-tren-windows-thumb-1692860106.jpg",
    "disable_comment": "0",
    "click_count": 592,
    "add_time": "6 th\u00e1ng tr\u01b0\u1edbc",
    "modify_time": "1692860126",
    "comment_rank": 0,
    "utc_time_public": "2023-08-24T13:55:06+07:00",
    "utc_time_modify": "2023-08-24T13:55:26+07:00",
    "url": "cach-kich-hoat-slide-to-shut-down-tren-windows",
    "author": "Ng\u1ecdc Nguy\u1ec5n Store"
  },
  "message": "success"
}
```


## 4. Danh sách tin mới

### Request

- Method:  GET 
- URL: /v1/articles/news

### Response

```json
{
  "success": true,
  "data": [
    {
      "article_id": 3771,
      "title": "C\u00e1ch k\u00edch ho\u1ea1t Slide to Shut Down tr\u00ean Windows",
      "add_time": "6 th\u00e1ng tr\u01b0\u1edbc",
      "article_sthumb": "https:\/\/ngocnguyen.vn\/cdn\/article_thumb\/202308\/cach-kich-hoat-slide-to-shut-down-tren-windows-sthumb-1692860106.jpg",
      "click_count": 592,
      "url": "cach-kich-hoat-slide-to-shut-down-tren-windows"
    },
    
  ],
  "message": "success"
}
```


## 5. Danh sách comments một bài tin tức

### Request

- Method:  GET 
- URL: /v1/articles/comments/:id
- Params: 
    - id (*): id bài tin tức
    
### Response


```json
{
  "success": true,
  "data": {
    "comments": [],
    "pagination": {
      "page": 1,
      "page_size": 5,
      "total_records": 0,
      "total_pages": 1
    }
  },
  "message": "success"
}
```