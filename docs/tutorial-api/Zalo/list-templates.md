---
sidebar_position: 12
custom_edit_url: null
---

# List Templates

## Api List Template lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/list-templates

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/list-templates`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `accessToken: {accessToken}`
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (Mô tả về API-KEY)
  - `accessToken`: (Mô tả về accessToken)
- **Body**:
  - `filter`: (Mô tả dữ liệu filter)
  - `paging`: (Mô tả dữ liệu paging)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| accessToken `header`   | string                | true            |    Mô tả về accsessToken           |
| filter `body`         | object                | false            |     <ul><li>**date_from** với kiểu dữ liệu là `string` đại diện cho ngày bắt đầu  </li><li>**date_to** với kiểu dữ liệu là `string` đại diện cho ngày kết thúc  </li><li>**oa_id** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li><li>**template_id** với kiểu dữ liệu là `number` đại diện cho ID của template </li><li>**template_name** với kiểu dữ liệu là `string` đại diện cho tên của template </li><li>**type** với kiểu dữ liệu là `unknow` đại diện cho loại template  </li></ul>      |
| page `body` | object | false | <ul><li>**after** với kiểu dữ liệu là `string` đại diện cho trang trước  </li><li>**before** với kiểu dữ liệu là `string` đại diện cho trang sau  </li><li>**limit** với kiểu dữ liệu là `number` đại diện cho giới hạn </li><li>**sort** với kiểu dữ liệu là `string` đại diện cho sắp xếp </li></ul> |
- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/list-templates' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'accessToken: $accessToken' \
  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
  "filter": {
    "date_from": "string",
    "date_to": "string",
    "oa_id": "string",
    "template_id": 0,
    "template_name": "string",
    "type": "UNKNOWN"
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



