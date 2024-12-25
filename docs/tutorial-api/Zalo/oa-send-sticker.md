---
sidebar_position: 8
custom_edit_url: null
---

# OA send sticker

## Api OA send sticker lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/oa-send-sticker

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/oa-send-sticker`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (Mô tả về API-KEY)
- **Body**:
  - `message`: (Mô tả dữ liệu message)
  - `oa_id`: (Mô tả dữ liệu oa_id)
  - `recipient`: (Mô tả dữ liệu recipient)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| oa_id `body`         | string                | false            |     Mô tả về oa_id          |
| message `body`         | object                | false            |      <ul><li>**attachment_id** với kiểu dữ liệu là `string` đại diện cho sticker tin nhắn</li></ul>         |
| recipient `body`        | object          | false            |     <ul><li> **user_id** với kiểu dữ liệu là `string` đại diện cho người nhận tin nhắn </li></ul>           |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/oa-send-sticker' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
  "message": {
    "attachment_id": "string"
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
{}
```
 

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



