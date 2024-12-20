---
sidebar_position: 2
---

# Callback

## Api Callback lên zalo

`POST` $BASE_URL/api/vendor/v1/sms/callback

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/sms/callback`
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
  - `msisdn`: (Mô tả dữ liệu msisdn)
  - `requestId`: (Mô tả dữ liệu requestId)
  - `sendTime`: (Mô tả dữ liệu sendTime)
  - `responseTimeTelco`: (Mô tả dữ liệu responseTimeTelco)
  - `status`: (Mô tả dữ liệu status)
  - `referentId`: (Mô tả dữ liệu referentId)
  - `retryCount`: (Mô tả dữ liệu retryCount)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| accessToken `header`   | string                | true            |    Mô tả về accsessToken           |
| msisdn `body`         | string                | true            |     Mô tả trường msisdn      |
| requestId `body`         | string                | true            |     Mô tả trường requestId      |
| sendTime `body`         | string                | true            |     Mô tả trường sendTime      |
| responseTimeTelco `body`         | 	string                | false            |     Mô tả trường responseTimeTelco      |
| status `body`         | number                | false            |     Mô tả trường status      |
| referentId `body`         | string                | true            |     Mô tả trường referentId      |
| retryCount `body`         | number                | true            |     Mô tả trường retryCount      |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/sms/callback' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'accessToken: $accessToken' \
  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
  "msisdn": "string",
  "requestId": "string",
  "sendTime": "string",
  "responseTimeTelco": "string",
  "status": 0,
  "referentId": "string",
  "retryCount": 0
}'
```

### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

- **Ví dụ Response**

```json
{
  "code": 0,
  "data": {
    "msisdn": "string",
    "requestId": "string",
    "sendTime": "string",
    "responseTimeTelco": "string",
    "status": 0,
    "referentId": "string",
    "retryCount": 0
  },
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


