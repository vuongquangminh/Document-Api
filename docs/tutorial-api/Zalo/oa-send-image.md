---
sidebar_position: 9
custom_edit_url: null
---

# OA send image

## Api OA send image  

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/zalo/oa-send-image
:::

:::info Lưu ý 

  - __API-KEY__: là duy nhất
  - Các bước lấy __API-KEY__: 
    1. Doanh nghiệp đăng nhập
    2. Di chuyển đến trang Key (hoặc License)
    3. Lấy 1 API-KEY thỏa mãn điều kiện hoạt động

:::

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/oa-send-image`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: Key License
- **Body**:
  - `message`: (Mô tả dữ liệu message)
  - `oa_id`: ID của OA
  - `recipient`: (Mô tả dữ liệu recipient)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Key License         |
| oa_id `body`         | string                | false            |     ID của OA          |
| message `body`         | object                | false            |     <ul><li>**attachment_id** với kiểu dữ liệu là `string` đại diện cho tệp ảnh đính kèm</li><li>**image_url** với kiểu dữ liệu là `string` đại diện cho đường dẫn ảnh</li></ul>      |
| recipient `body`        | object          | false            |    <ul><li>**user_id** với kiểu dữ liệu là `string` đại diện cho người nhận tin nhắn </li></ul>           |



- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/oa-send-image' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Content-Type: application/json' \
  -d '{
  "message": {
    "attachment_id": "string",
    "image_url": "string"
  },
  "oa_id": "string",
  "recipient": {
    "user_id": "string"
  }
}'
```

### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

- **Ví dụ Response**

```json
{
  "code": "number",
  "data": {
    "direction": "in",
    "msg_id": "string",
    "oa_id": "string",
    "recipient_id": "string",
    "sender_id": "string",
    "shop_id": "string",
    "type": "unknown",
    "user_id": "string",
    "zl_user_id": "string"
    },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key          | Type            |    Description       |
|------------- |-----------------|-------------------|
| direction     | string          |    `in` `out`   |
| msg_id     | string          |    ID của thông báo   |
| oa_id     | string          |     ID của OA   |
| recipient_id     | string          |    ID của người nhận   |
| sender_id     | string          |    ID người gửi   |
| shop_id     | string          |    ID của shop trên eTelecom   |
| type     | string          |    `unknown` `text` `audio` `video` `photo` `GIF` `file`  `sticker`  `location`  `business_card`   |
| user_id     | string          |    ID user trên eTelecom   |

- **Cấu trúc data của response**

| Key          | Type            |    Description       |
|------------- |-----------------|-------------------|
| direction     | string          |    `in` `out`   |
| msg_id     | string          |    ID của thông báo   |
| oa_id     | string          |     ID của OA   |
| recipient_id     | string          |    ID của người nhận   |
| sender_id     | string          |    ID người gửi   |
| shop_id     | string          |    ID của shop trên eTelecom   |
| type     | string          |    `unknown` `text` `audio` `video` `photo` `GIF` `file`  `sticker`  `location`  `business_card`   |
| user_id     | string          |    ID user trên eTelecom   |

### Bảng Status Response

| Status Code | Status Message            | Description                                                                 |
|-------------|---------------------------|-----------------------------------------------------------------------------|
| 200         | OK                        | Yêu cầu đã thành công và server trả về kết quả.                           |
| 201         | Created                   | Yêu cầu đã thành công và server đã tạo ra tài nguyên mới.                  |
| 204         | No Content                | Yêu cầu đã thành công nhưng không có nội dung trả về.                      |
| 400         | Bad Request               | Server không thể hiểu yêu cầu do cú pháp không hợp lệ.                    |
| 401         | Unauthorized              | Cần xác thực để truy cập tài nguyên.                                       |
| 403         | Forbidden                 | Server từ chối thực hiện yêu cầu, mặc dù người dùng đã xác thực.           |
| 404         | Not Found                 | Tài nguyên yêu cầu không tồn tại trên server.                              |
| 405         | Method Not Allowed         | Phương thức HTTP không được phép cho tài nguyên yêu cầu.                   |
| 500         | Internal Server Error     | Lỗi không xác định trong server.                                            |
| 502         | Bad Gateway               | Server là một gateway hoặc proxy và nhận được phản hồi không hợp lệ từ server khác. |
| 503         | Service Unavailable       | Server không thể xử lý yêu cầu do quá tải hoặc bảo trì.                    |
| 504         | Gateway Timeout           | Server không nhận được phản hồi kịp thời từ server phụ trợ.                |



