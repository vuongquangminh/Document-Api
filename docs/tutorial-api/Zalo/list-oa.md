---
sidebar_position: 4
custom_edit_url: null
---

# List OA

## Api List OA  

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/zalo/list-oa
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
- **URL**: `/api/vendor/v1/zalo/list-oa`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: Key License
- **Body**:
  - `filter`: (Mô tả dữ liệu filter)
  - `paging`: (Mô tả dữ liệu paging)
- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Key License         |
| filter `body`         | object                | false            |     <ul><li>**app_id** với kiểu dữ liệu là `number`: ID của ứng dụng </li><li>**date_from** với kiểu dữ liệu là `string`: Ngày bắt đầu  </li><li>**date_to** với kiểu dữ liệu là `string`: Ngày kết thúc  </li><li>**oa_id** với kiểu dữ liệu là `string`: ID của OA  </li><li>**name** với kiểu dữ liệu là `string`: Tên OA </li></ul>      |

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/list-oa' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Content-Type: application/json' \
  -d '{
  "filter": {
    "app_id": "string",
    "date_from": "string",
    "date_to": "string",
    "name": "string",
    "oa_id": "string"
  },
  "paging": {
    "after": "string",
    "before": "string",
    "limit": 0,
    "sort": "string"
  }
}'
```

### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

- **Ví dụ Response**

```json
{
  "code": "number",
  "data": {
    "accounts": [
      {
        "verified": true,
        "app_id": "string",
        "avatar": "string",
        "connection_id": "string",
        "connection_method": "UNKNOWN",
        "cover": "string",
        "created_at": "string",
        "current_quality": "UNKNOWN",
        "daily_quota": 0,
        "description": "string",
        "expires_at": "string",
        "is_verified": true,
        "last_week_quality": "UNKNOWN",
        "name": "string",
        "oa_id": "string",
        "onwer_id": "string",
        "remaining_quota": "number",
        "shop_id": "string",
        "status": "Z",
        "updated_at": "string"
      }
    ],
    "paging": {
      "after": "string",
      "before": "string",
      "limit": "number",
      "next": "string",
      "prev": "string",
      "sort": "string"
    }
  },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key        | Type            | Description       |
|------------- |-----------------|-------------------|
| accounts | array |  <ul><li>**app_id** với kiểu dữ liệu là `string`: ID của ứng dụng  </li><li>**avatar** với kiểu dữ liệu là `string`: Đường dẫn đến ảnh bìa của OA  </li><li>**connection_id** với kiểu dữ liệu là `string`: ID kết nối </li><li>**connection_method** với kiểu dữ liệu là `string`: Phương thức kết nối `direct` </li><li>**description** với kiểu dữ liệu là `string`: Mô tả  </li><li>**is_verified** với kiểu dữ liệu là `boolean`: <ul><li>`True`: OA được verify</li><li> `False`: OA chưa được verify</li></ul> </li><li>**name** với kiểu dữ liệu là `string`: Tên OA  </li><li>**oa_id** với kiểu dữ liệu là `string`: ID của OA  </li><li>**onwer_id** với kiểu dữ liệu là `string`: ID của chủ shop trên hệ thống ITS  </li><li>**shop_id** với kiểu dữ liệu là `string`: ID của shop trên hệ thống ITS  </li><li>**status** với kiểu dữ liệu là `Z`: Trạng thái <ul><li>`P`: Đang kết nối</li><li> `N`: Ngắt kết nối</li></ul> </li><li>**current_quality** với kiểu dữ liệu là `string`: Chất lượng gửi thông báo ZNS trong 48 giờ gần nhất của OA  </li><li>**last_week_quality** với kiểu dữ liệu là `string`: Chất lượng gửi thông báo ZNS trong 7 ngày gần nhất của OA.  </li><li>**daily_quota** với kiểu dữ liệu là `number`: Số thông báo ZNS OA được gửi trong 1 ngày.  </li><li>**remaining_quota** với kiểu dữ liệu là `number`: Số thông báo ZNS OA được gửi trong ngày còn lại </li><li>**expires_at** với kiểu dữ liệu là `string`: Thời gian hết hạn của refresh token  </li><li>**created_at** với kiểu dữ liệu là `string`: Ngày tạo  </li><li>**updated_at** với kiểu dữ liệu là `string`: Ngày cập nhật  </li></ul> | 

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



