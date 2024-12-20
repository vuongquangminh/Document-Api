---
sidebar_position: 9
---

# OA send image

## Api OA send image lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/oa-send-image

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/oa-send-image`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `accessToken: {accessToken}`
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (Dữ liệu file cần upload)
  - `accessToken`: (Mô tả ngắn về file nếu có)
- **Body**:
  - `message`: (Mô tả dữ liệu message)
  - `oa_id`: (Mô tả dữ liệu oa_id)
  - `recipient`: (Mô tả dữ liệu recipient)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| accessToken `header`   | string                | true            |    Mô tả về accsessToken           |
| oa_id `body`         | string                | false            |     Mô tả về oa_id          |
| message `body`         | object                | false            |     <ul><li>**attachment_id** với kiểu dữ liệu là `string` đại diện cho tệp ảnh đính kèm</li><li>**image_url** với kiểu dữ liệu là `string` đại diện cho đường dẫn ảnh</li></ul>      |
| recipient `body`        | object          | false            |    <ul><li>**user_id** với kiểu dữ liệu là `string` đại diện cho người nhận tin nhắn </li></ul>           |



- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/oa-send-image' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'accessToken: $accessToken' \
  -H 'Authorization: Bearer $accessToken' \
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
  "code": 0,
  "data": {},
  "message": "string",
  "errors": {
    "additionalProp1": {},
    "additionalProp2": {},
    "additionalProp3": {}
  },
  "total_record": 0,
  "current_page": 0
}
```

- **Cấu trúc data của response**

| Key        | Type            |     Required    | Description       |
|------------- |-----------------|-----------------|-------------------|
| file         | string          | True            |    Mô tả msg_id   |

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



