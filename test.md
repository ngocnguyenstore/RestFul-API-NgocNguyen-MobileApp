```js
//// Gửi token đến server của bạn và lưu trữ để gửi thông báo sau này
fetch("https://ngocnguyen.vn/api/v1/notifications/token", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
    "X-API-Key":
      "OWt5Q0hGUXRLdXhSOWhPWkJUUjRuNU1Tb0lhdEM5UW1vYjJwMkx5SXBINTJ3ajZJdzFvbmFIRjNndkhmQisyQQ==",
  },
  body: JSON.stringify({ token: currentToken }),
})
  .then((response) => response.json())
  .then((data) => {
    // Xử lý dữ liệu trả về nếu cần
    console.log(data);
  })
  .catch((error) => {
    // Xử lý lỗi nếu có
    console.error(error);
  });
```
