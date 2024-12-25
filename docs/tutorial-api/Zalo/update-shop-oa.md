---
sidebar_position: 3
custom_edit_url: null
---

# Update Shop OA

## Api update shop OA

`POST` $BASE_URL/api/vendor/v1/zalo/update-shop-oa

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/update-shop-oa`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (API-KE dùng để xác thực và quản lý quyền truy cập vào API của họ)
- **Body**:
  - `oa_id`: (Mô tả dữ liệu file oa_id)
  - `webhook_url`: (Mô tả dữ liệu file webhook_url)



- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`      | string                | true            |    Mô tả về API-KEY         |
| oa_id `body`         | string                | false           |     Mô tả về oa_id          |
| webhook_url `body`         | string                | false             |      Mô tả về webhook_url         |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/update-shop-oa' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
  "oa_id": "string",
  "webhook_url": "string"
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
    "owner_id": "string",
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

| Key          | Type            |    Description       |
|------------- |-----------------|-------------------|
| verified     | boolean         |    Mô tả verified   |
| app_id     | string         |    Mô tả app_id   |
| avatar     | string         |    Mô tả avatar   |
| connection_id     | string         |    Mô tả connection_id   |
| connection_method     | UNKNOWN         |    Mô tả connection_method   |
| cover     | string         |    Mô tả cover   |
| created_at     | string         |    Mô tả created_at   |
| current_quality     | number         |    Mô tả current_quality   |
| daily_quota_promotion     | number         |    Mô tả daily_quota_promotion   |
| description     | string         |    Mô tả description   |
| estimated_next_month_promotion_quota     | number         |    Mô tả estimated_next_month_promotion_quota   |
| expires_at     | string         |    Mô tả expires_at   |
| is_verified     | boolean         |    Mô tả is_verified   |
| last_week_quality     | UNKNOWN         |    Mô tả last_week_quality   |
| monthly_promotion_quota     | number         |    Mô tả monthly_promotion_quota   |
| name     | string         |    Mô tả name   |
| oa_id     | string         |    Mô tả oa_id   |
| owner_id     | string         |    Mô tả owner_id   |
| remaining_monthly_promotion_quota     | number         |    Mô tả remaining_monthly_promotion_quota   |
| remaining_quota     | number         |    Mô tả remaining_quota   |
| shop_id     | string         |    Mô tả shop_id   |
| status     | Z         |    Mô tả status   |
| updated_at     | string         |    Mô tả updated_at   |
| webhook_url     | string         |    Mô tả webhook_url   |

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



