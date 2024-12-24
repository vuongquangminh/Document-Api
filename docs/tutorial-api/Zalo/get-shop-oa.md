---
sidebar_position: 18
custom_edit_url: null
---

# Get Shop OA

## Api Get Shop OA lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/get-shop-oa

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/get-shop-oa`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (Mô tả về API-KEY)
- **Body**:
  - `oa_id`: (Mô tả dữ liệu oa_id)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| oa_id `body`         | string                | false            |     Mô tả trường oa_id      |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/get-shop-oa' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
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
    "verified": true,
    "app_id": "string",
    "avatar": "string",
    "connection_id": "string",
    "connection_method": "UNKNOWN",
    "cover": "string",
    "created_at": "string",
    "current_quality": "UNKNOWN",
    "daily_quota": "number",
    "daily_quota_promotion": "number",
    "description": "string",
    "estimated_next_month_promotion_quota": "number",
    "expires_at": "string",
    "is_verified": true,
    "last_week_quality": "UNKNOWN",
    "monthly_promotion_quota": "number",
    "name": "string",
    "oa_id": "string",
    "onwer_id": "string",
    "remaining_monthly_promotion_quota": "number",
    "remaining_quota": "number",
    "shop_id": "string",
    "status": "Z",
    "updated_at": "string",
    "webhook_url": "string"
  },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key        | Type            | Description       |
|------------- |-----------------|-------------------|
| verified         | boolean          |    Mô tả msg_id   |
| app_id         | string          |    Mô tả msg_id   |
| avatar         | string          |    Mô tả msg_id   |
| connection_id         | string          |    Mô tả msg_id   |
| connection_method         | UNKNOWN          |    Mô tả msg_id   |
| cover         | string          |    Mô tả msg_id   |
| created_at         | string          |    Mô tả msg_id   |
| current_quality         | UNKNOWN          |    Mô tả msg_id   |
| daily_quota         | number          |    Mô tả msg_id   |
| daily_quota_promotion         | number          |    Mô tả msg_id   |
| description         | string          |    Mô tả msg_id   |
| estimated_next_month_promotion_quota         | number          |    Mô tả msg_id   |
| expires_at         | string          |    Mô tả msg_id   |
| is_verified         | boolean          |    Mô tả msg_id   |
| last_week_quality         | UNKNOWN          |    Mô tả msg_id   |
| monthly_promotion_quota         | number          |    Mô tả msg_id   |
| name         | string          |    Mô tả msg_id   |
| oa_id         | string          |    Mô tả msg_id   |
| onwer_id         | string          |    Mô tả msg_id   |
| remaining_monthly_promotion_quota         | number          |    Mô tả msg_id   |
| remaining_quota         | number          |    Mô tả msg_id   |
| shop_id         | string          |    Mô tả msg_id   |
| status         | Z          |    Mô tả msg_id   |
| updated_at         | string          |    Mô tả msg_id   |
| webhook_url         | string          |    Mô tả msg_id   |

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



