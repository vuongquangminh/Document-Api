---
sidebar_position: 1
---

# Send Message

## Api Send Message lên zalo

`POST` $BASE_URL/api/vendor/v1/sms/send-message

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/sms/send-message`
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
  - `destinations`: (Mô tả dữ liệu destinations)
  - `from`: (Mô tả dữ liệu from)
  - `text`: (Mô tả dữ liệu text)
  - `scheduled`: (Mô tả dữ liệu scheduled)
  - `requestId`: (Mô tả dữ liệu requestId)
  - `useUnicode`: (Mô tả dữ liệu useUnicode)
  - `type`: (Mô tả dữ liệu type)
  - `ext`: (Mô tả dữ liệu ext)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| accessToken `header`   | string                | true            |    Mô tả về accsessToken           |
| destinations `body`         | array                | true            |     Mô tả trường destinations      |
| from `body`         | string                | true            |     Mô tả trường from      |
| text `body`         | string                | true            |     Mô tả trường text      |
| scheduled `body`         | 	string                | false            |     Mô tả trường scheduled      |
| requestId `body`         | string                | false            |     Mô tả trường requestId      |
| useUnicode `body`         | string                | true            |     Mô tả trường useUnicode      |
| type `body`         | string                | true            |     Mô tả trường type      |
| ext `body`         | object                | false            |     Mô tả trường ext      |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/sms/send-message' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'accessToken: $accessToken' \
  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
  "destinations": [
    "string"
  ],
  "from": "string",
  "text": "string",
  "scheduled": "2024-12-20T03:33:44.757Z",
  "requestId": "string",
  "useUnicode": 0,
  "type": 0,
  "ext": {}
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



