# Check Bảo hành, sửa chửa


(*) là tham số yêu cầu điền

## 1. Lấy Thông tin bảo hành sửa chữa

### Request

- Method:  GET 
- URL: /v1/warranty?type=1&query_code=206100099402
- Queries:
  - type (*): `1`=Kiểm tra hạn bảo hành, `2`=Trạng thái bảo hành sửa chữa 
  - query_code (*): Số Điện thoại hoặc imei sản phẩm


### Response

Trường hợp với `type=1`

```json
{
  "success": true,
  "data": {
    "customerInfo": {
      "name": "A Tu\u1ea5n Anh",
      "mobile": "0967384033",
      "address": "HN "
    },
    "goods_list": {
      "19186": {
        "goods_name": "\tTivi Xiaomi 65 inch 4K (EA65 model 2023)",
        "imei": "206100099402",
        "goods_attr": "",
        "actived": "\u0110\u00e3 k\u00edch ho\u1ea1t",
        "end_date": "2024-12-08 16:50:04",
        "care": null
      }
    }
  },
  "message": "success"
}
```

Trường hợp với `type=2`

```json
{
  "success": true,
  "data": {
    "customerInfo": {
      "name": "Anh Ti\u1ebfn",
      "mobile": "0939355240",
      "address": "hcm "
    },
    "goods_list": {
      "5915": {
        "goods_name": "Dell E5440 I5-4300U\/ RAM 4GB\/ SSD 128GB\/ HD Graphics 4400\/ 14 INCH HD",
        "imei": "6MPMYZ1       ",
        "goods_attr": "",
        "actived": "\u0110\u00e3 k\u00edch ho\u1ea1t",
        "end_date": "2022-11-11 11:50:32",
        "care": {
          "259": {
            "add_time": "2023-03-31 15:11:35",
            "add_soon": "2023-04-07 15:10:57",
            "icare_desc": "M\u00e1y kh\u00f4ng l\u00ean ngu\u1ed3n\r\n0774399481 (ANH H\u1eb0NG)",
            "icare_status": "Ti\u1ebfp nh\u1eadn b\u1ea3o h\u00e0nh",
            "icare_note": ""
          },
          "243": {
            "add_time": "2022-09-30 19:22:07",
            "add_soon": "2022-10-07 12:21:19",
            "icare_desc": "036 2695 878 C Th\u1ea3o. m\u00e1y b\u1eadt kh\u00f4ng l\u00ean ngu\u1ed3n",
            "icare_status": "\u0110ang b\u1ea3o h\u00e0nh",
            "icare_note": ""
          }
        }
      }
    }
  },
  "message": "success"
}
```

Mô tả các trường:

- goods_name: Tên máy
- imei: số imei máy
- actived: trạng thái bảo hành
- end_date: Hạn bảo hành
- add_time: Ngày bảo hành
- add_soon: Ngày dự kiến bảo hành xong
- icare_desc: mô tả lỗi chuẩn đoán
- icare_status: Trạng thái đơn bảo hành
- icare_note: ghi chú bảo hành