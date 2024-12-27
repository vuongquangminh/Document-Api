---
sidebar_position: 3
custom_edit_url: null
---

# Update Shop OA

## Api update shop OA

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/zalo/update-shop-oa
:::

:::info Lưu ý 

  - __API-KEY__: là duy nhất
  - Các bước lấy __API-KEY__: 
    1. Doanh nghiệp đăng nhập
    2. Di chuyển đến trang Key (hoặc License)
    3. Lấy 1 API-KEY thỏa mãn điều kiện hoạt động

:::

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/update-shop-oa`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: Key license
- **Body**:
  - `oa_id`: ID của OA
  - `webhook_url`: URL Webhook mà bạn muốn nhận event



- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`      | string                | true            |    Key license         |
| oa_id `body`         | string                | false           |     ID của OA          |
| webhook_url `body`         | string                | false             |      URL Webhook mà bạn muốn nhận event         |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/update-shop-oa' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
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
| verified     | boolean         |    <ul><li>**True** : OA được verify </li><li>**False** : OA chưa được verify </li></ul>   |
| app_id     | string         |    ID của ứng dụng   |
| avatar     | string         |    Đường dẫn đến ảnh bìa của OA   |
| connection_id     | string         |    ID kết nối   |
| connection_method     | UNKNOWN         |    Phương thức kết nối `unknown` `builtin` `direct`   |
| created_at     | string         |    Ngày tạo   |
| current_quality     | number         |    Chất lượng gửi thông báo ZNS trong 48 giờ gần nhất của OA. <ul><li>`HIGH` : Mức độ chất lượng tốt </li><li>`MEDIUM` : Mức độ chất lượng trung bình</li><li>`LOW` : Mức độ chất lượng kém </li><li>`UNDEFINED` : Mức độ chất lượng OA chưa được xác định (trường hợp OA không gửi thông báo ZNS nào trong khung thời gian đánh giá) </li></ul>    |
| description     | string         |    Mô tả   |
| expires_at     | string         |    Thời gian hết hạn của refresh token   |
| is_verified     | boolean         |    <ul><li>**True** : OA được verify </li><li>**False** : OA chưa được verify </li></ul>   |
| last_week_quality     | UNKNOWN         |    Chất lượng gửi thông báo ZNS trong 7 ngày gần nhất của OA. Các giá trị trả về: <ul><li>`HIGH` : Mức độ chất lượng tốt </li><li>`MEDIUM` : Mức độ chất lượng trung bình</li><li>`LOW` : Mức độ chất lượng kém </li><li>`UNDEFINED` : Mức độ chất lượng OA chưa được xác định (trường hợp OA không gửi thông báo ZNS nào trong khung thời gian đánh giá) </li></ul>    |
| name     | string         |    Tên OA   |
| oa_id     | string         |    ID của OA   |
| owner_id     | string         |    ID của chủ shop trên hệ thống eTelecom   |
| remaining_quota     | number         |    Số thông báo ZNS OA được gửi trong ngày còn lại.   |
| shop_id     | string         |    ID của shop trên hệ thống eTelecom   |
| status     | Z         |    Trạng thái <ul><li>**P** : Đang kết nối </li><li>**N** : Ngắt kết nối </li></ul>   |
| updated_at     | string         |    Ngày cập nhật   |
| webhook_url     | string         |    URL Webhook mà bạn muốn nhận event   |

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



