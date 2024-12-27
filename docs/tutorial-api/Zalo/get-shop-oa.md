---
sidebar_position: 18
custom_edit_url: null
---

# Get Shop OA

## Api Get Shop OA  

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/zalo/get-shop-oa
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
- **URL**: `/api/vendor/v1/zalo/get-shop-oa`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: Key License
- **Body**:
  - `oa_id`: ID của OA

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Key License         |
| oa_id `body`         | string                | false            |     ID của OA      |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/get-shop-oa' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
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
| verified         | boolean          |    <ul><li>`True`: OA được verify</li><li> `False`: OA chưa được verify</li></ul>    |
| app_id         | string          |    ID của ứng dụng   |
| avatar         | string          |    Đường dẫn đến ảnh bìa của OA   |
| connection_id         | string          |    ID kết nối   |
| connection_method         | string          |    Phương thức kết nối <ul><li>`unknown`</li><li>`builtin`</li><li>`direct`</li></ul>   |
| cover         | string          |    Mô tả cover   |
| created_at         | string          |    Mô tả created_at   |
| description         | string          |    Mô tả   |
| estimated_next_month_promotion_quota         | number          |   Số tin ZNS hậu mãi dự kiến mà OA có thể gửi trong tháng tiếp theo.  |
| expires_at         | string          |    Thời gian hết hạn của refresh token   |
| is_verified         | boolean          |    <ul><li>`True`: OA được verify</li><li> `False`: OA chưa được verify</li></ul>   |
| name         | string          |   Tên OA   |
| oa_id         | string          |    ID của OA   |
| onwer_id         | string          |    ID của chủ shop trên hệ thống eTelecom   |
| remaining_monthly_promotion_quota         | number          |    Số tin ZNS hậu mãi còn lại OA được gửi trong tháng.   |
| remaining_quota         | number          |    Mô tả remaining_quota   |
| shop_id         | string          |    ID của shop trên hệ thống eTelecom   |
| status         | Z          |    Trạng thái <ul><li>**P** : Đang kết nối </li><li>**N** : Ngắt kết nối </li></ul>   |
| current_quality         | string          |    Chất lượng gửi thông báo ZNS trong 48 giờ gần nhất của OA. <ul><li>`HIGH` : Mức độ chất lượng tốt </li><li>`MEDIUM` : Mức độ chất lượng trung bình</li><li>`LOW` : Mức độ chất lượng kém </li><li>`UNDEFINED` : Mức độ chất lượng OA chưa được xác định (trường hợp OA không gửi thông báo ZNS nào trong khung thời gian đánh giá) </li></ul>   |
| last_week_quality         | string          |    Chất lượng gửi thông báo ZNS trong 7 ngày gần nhất của OA. Các giá trị trả về: <ul><li>`HIGH` : Mức độ chất lượng tốt </li><li>`MEDIUM` : Mức độ chất lượng trung bình</li><li>`LOW` : Mức độ chất lượng kém </li><li>`UNDEFINED` : Mức độ chất lượng OA chưa được xác định (trường hợp OA không gửi thông báo ZNS nào trong khung thời gian đánh giá) </li></ul>   |
| daily_quota         | number          |    Số thông báo ZNS OA được gửi trong 1 ngày.   |
| remaining_quota         | number          |    Số thông báo ZNS OA được gửi trong ngày còn lại.   |
| daily_quota_promotion         | number          |   Số tin ZNS hậu mãi OA được gửi trong ngày. Ghi chú: Từ ngày 1/11, thuộc tính này sẽ trả về giá trị null   |
| monthly_promotion_quota         | string          |    Ngày cập nhật   |
| updated_at         | string          |    Ngày cập nhật   |
| webhook_url         | string          |    Mô tả webhook_url   |

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



