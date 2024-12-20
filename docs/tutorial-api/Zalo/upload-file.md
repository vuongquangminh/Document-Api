---
sidebar_position: 1
---

# Upload File

## Api upload file lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/upload-file

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/upload-file`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: multipart/form-data`
  - `accessToken: {accessToken}`
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (API-KEY dùng để xác thực và quản lý quyền truy cập vào API)
  - `accessToken`: (Access token là một chuỗi được sinh ngẫu nhiên giúp xác định người dùng)
  - `type`: (Mô tả ngắn về type nếu có)
  - `oaId`: (Mô tả ngắn về oaId nếu có)
- **Body**:
  - `file`: (Mô tả dữ liệu file truyền vào)



- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header` `header`      | string                | true            |    Mô tả về API-KEY         |
| accessToken `header` `header` | string                | true            |    Mô tả về accsessToken           |
| type `parameter`         | string                | true            |     Mô tả về type         |
| oaId `parameter`         | string                | true            |      Mô tả về oaId        |
| file `body`        | string          | false            |    Mô tả về file          |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/upload-file?type=UpLoadFile&oaId=Kmj394nbf82n' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'accessToken: $accessToken' \
  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
  "file": "string"
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



