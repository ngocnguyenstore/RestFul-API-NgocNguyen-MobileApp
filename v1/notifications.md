# APIs Thông báo

(*) là tham số yêu cầu điền


## 1. Lấy danh sách thông báo

### Request

- Method:  GET 
- URL: /v1/notifications 


### Response

Trả về mặc định `20` thông báo mới nhất

```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "title": "Th\u00f4ng b\u00e1o 1",
      "type": "Th\u00f4ng b\u00e1o chung",
      "thumb": "",
      "add_time": "28-06-2024 15:59:14"
    },
    {
      "id": 2,
      "title": "Th\u00f4ng b\u00e1o 2",
      "type": "Th\u00f4ng b\u00e1o chung",
      "thumb": "",
      "add_time": "28-06-2024 16:13:14"
    }
  ],
  "message": "success"
}
```


## 2. Chi tiết thông báo

### Request

- Method:  GET 
- URL: /v1/notifications/details/:id


### Response


```json
{
  "success": true,
  "data": {
    "id": 1,
    "title": "Th\u00f4ng b\u00e1o 1",
    "type": "Th\u00f4ng b\u00e1o chung",
    "content": "",
    "thumb": "",
    "add_time": "28-06-2024 15:59:14"
  },
  "message": "success"
}
```