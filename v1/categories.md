# APIs Danh mục sản phẩm

(*) là tham số yêu cầu điền

## 1. Lấy danh sách Danh mục sản phẩm


### Request

- Method:  GET 
- URL: /v1/categories


### Response

```json
{
  "success": true,
  "data": [
    {
      "cat_id": 1,
      "cat_name": "Laptop",
      "icon": "https:\/\/ngocnguyen.vn\/cdn2\/files\/cat_icon\/laptop.png",
      "thumb": "https:\/\/ngocnguyen.vn\/cdn\/upload\/images\/thumbnail-thu-muc\/ewffsd.jpg",
      "parent_id": 0,
      "url": "laptop.html",
      "childs": [
                {
                "cat_id": 105,
                "cat_name": "Dell",
                "icon": 0,
                "thumb": "https:\/\/ngocnguyen.vn\/cdn\/upload\/images\/thumbnail-thu-muc\/untitled-1.jpg",
                "parent_id": 1,
                "url": "laptop-dell.html",
                "childs": [
                    {
                    "cat_id": 456,
                    "cat_name": "Dell XPS",
                    "icon": 0,
                    "thumb": "https:\/\/ngocnguyen.vn\/cdn\/upload\/images\/thumbnail-thu-muc\/untitled-1.jpg",
                    "parent_id": 105,
                    "url": "dellxps.html",
                    "childs": []
                    },
                
                ]
                }
        
        ]
    }
  ],
  "message": "success"
}
```

## 2. Thông tin chi tiết 1 danh mục

### Request

- Method:  GET 
- URL: /v1/categories/details/:id
- Params: 
  - id (*): id của danh mục


### Response

```json
{
  "success": true,
  "data": {
    "details": {
      "cat_id": 1,
      "cat_name": "Laptop",
      "custom_name": "Laptop Ch\u00ednh H\u00e3ng",
      "hide_brand": 0,
      "ads_category": 0,
      "ads_category_mobile": 0,
      "cat_desc": "",
      "filter_attr": "648,649,650",
      "parent_id": 0,
      "template_file": ""
    },
    "sub_childs": [
      {
        "cat_id": 105,
        "cat_name": "Dell",
        "icon": 0,
        "thumb": "https:\/\/ngocnguyen.vn\/cdn\/upload\/images\/thumbnail-thu-muc\/untitled-1.jpg",
        "class": "",
        "parent_id": 0,
        "url": "laptop-dell.html",
        "childs": [
          {
            "cat_id": 456,
            "cat_name": "Dell XPS",
            "icon": 0,
            "thumb": "https:\/\/ngocnguyen.vn\/cdn\/upload\/images\/thumbnail-thu-muc\/untitled-1.jpg",
            "class": "",
            "parent_id": 0,
            "url": "dellxps.html",
            "childs": []
          },
          
        ]
      },
    ]
  },
  "message": "success"
}
```