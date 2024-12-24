---
sidebar_position: 19
custom_edit_url: null
---

# Get Journey

## Api Get Journey lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/get-journey

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/get-journey`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (Mô tả về API-KEY)
- **Body**:
  - `journey_id`: (Mô tả dữ liệu journey_id)
  - `oa_id`: (Mô tả dữ liệu oa_id)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| journey_id `body`         | string                | false            |     Mô tả trường journey_id      |
| oa_id `body`         | string                | false            |     Mô tả trường oa_id      |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/get-journey' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \

  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
  "journey_id": "string",
  "oa_id": "string"
}'
```

### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

- **Ví dụ Response**

```json
{
  "code": "number",
  "data": {
    "charged": true,
    "created_at": "string",
    "error_code": "number",
    "error_message": "string",
    "expired_at": "string",
    "id": "string",
    "is_charged": true,
    "journey_id": "string",
    "journey_token": "string",
    "phone": "string",
    "status": "Z",
    "updated_at": "string"
  },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key        | Type            | Description       |
|------------- |-----------------|-------------------|
| charged         | boolean          |    Mô tả msg_id   |
| created_at         | string          |    Mô tả msg_id   |
| error_code         | number          |    Mô tả msg_id   |
| error_message         | string          |    Mô tả msg_id   |
| expired_at         | string          |    Mô tả msg_id   |
| id         | string          |    Mô tả msg_id   |
| is_charged         | boolean          |    Mô tả msg_id   |
| journey_id         | string          |    Mô tả msg_id   |
| journey_token         | string          |    Mô tả msg_id   |
| phone         | string          |    Mô tả msg_id   |
| status         | Z          |    Mô tả msg_id   |
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



