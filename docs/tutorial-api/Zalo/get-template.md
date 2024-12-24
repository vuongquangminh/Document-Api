---
sidebar_position: 17
custom_edit_url: null
---

# Get Template

## Api Get Template lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/get-template

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/get-template`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (Mô tả về API-KEY)

- **Body**:
  - `oa_id`: (Mô tả dữ liệu oa_id)
  - `template_id`: (Mô tả dữ liệu template_id)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| oa_id `body`         | string                | false            |     Mô tả trường oa_id      |
| template_id `body` | number | false | Mô tả trường template_id |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/get-template' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
  "oa_id": "string",
  "template_id": 0
}'
```

### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

- **Ví dụ Response**

```json
{
  "code": "number",
  "data": {
    "apply_template_quota": true,
    "created_at": "string",
    "preview_url": "string",
    "price": "number",
    "template_daily_quota": "number",
    "template_id": "number",
    "template_params": [
      {
        "accept_null": true,
        "max_length": "number",
        "min_length": "number",
        "name": "string",
        "require": true,
        "type": "string"
      }
    ],
    "template_quality": "UNKNOWN",
    "template_remaining_quota": "number",
    "template_status": "UNKNOWN",
    "template_tag": "UNKNOWN",
    "timeout": "number",
    "type": "UNKNOWN",
    "updated_at": "string"
  },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key        | Type            | Description       |
|------------- |-----------------|-------------------|
| apply_template_quota         | boolean          |    Mô tả msg_id   |
| created_at         | string          |    Mô tả msg_id   |
| preview_url         | string          |    Mô tả msg_id   |
| price         | number          |    Mô tả msg_id   |
| template_daily_quota         | number          |    Mô tả msg_id   |
| template_id         | number          |    Mô tả msg_id   |
| template_name         | string          |    Mô tả msg_id   |
| template_params         | object          |    Mô tả msg_id   |
| template_quality         | UNKNOWN          |    Mô tả msg_id   |
| template_remaining_quota         | number          |    Mô tả msg_id   |
| template_status         | UNKNOWN          |    Mô tả msg_id   |
| template_tag         | UNKNOWN          |    Mô tả msg_id   |
| timeout         | number          |    Mô tả msg_id   |
| type         | string          |    Mô tả msg_id   |
| updated_at         | string          |    Mô tả msg_id   |

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



