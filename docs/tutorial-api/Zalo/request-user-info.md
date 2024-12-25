---
sidebar_position: 5
custom_edit_url: null
---

# Request User Info

## Api Request User Info lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/request-user-info

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/request-user-info`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (Mô tả về API-KEY)
- **Body**:
  - `oa_id`: (Mô tả về oa_id)
  - `zl_user_id`: (Mô tả về zl_user_id)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| oa_id `body`         | string                | false            |     Mô tả về oa_id          |
| zl_user_id `body`         | string                | false            |      Mô tả về zl_user_id         |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/request-user-info' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
  "oa_id": "string",
  "zl_user_id": "string"
}'
```

### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

- **Ví dụ Response**

```json
{
  "code": "number",
  "data": {
    "updated": "number"
  },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key        | Type            | Description       |
|------------- |-----------------|-------------------|
| updated         | number           |    Mô tả updated   |

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



