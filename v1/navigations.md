# Link điều hướng theo vị trí

### Request

- Method:  GET 
- URL: /v1/navigator/:position
- Params:
    - position (*): Tên vị trí ('top', 'middle', 'bottom', 'home_mobile', 'home_pc','header_mobile')


### Response

```json
{
  "success": true,
  "data": [
    {
      "name": "Laptop",
      "opennew": 0,
      "url": "laptop.html",
      "ctype": "",
      "cid": 0,
      "order": 1,
      "active": 0,
      "class": "",
      "icon": "6789.png",
      "rel": "",
      "children": []
    },
  ],
  "message": "success"
}
```