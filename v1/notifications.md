# APIs Thông báo

(*) là tham số yêu cầu điền


## Quy trình

- Client gửi token subscriber thông báo --> Backend lưu lại
- Backend bắn thông báo cho những Client đã subscriber --> đến --> FCM
- FCM forward lại thông báo cho Client


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



## 3. Lưu trữ thiết bị nhận thông báo

### Request

- Method:  POST 
- URL: /v1/notifications/token
- Body:
  - token (*): token thiết bị


### Response


```json
{
  "success": true,
  "data": {
    "token": "your token",
  },
  "message": "success"
}
```