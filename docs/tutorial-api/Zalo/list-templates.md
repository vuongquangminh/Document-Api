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
| filter `body`         | object                | false            |     <ul><li>**date_from** với kiểu dữ liệu là `string` đại diện cho ngày bắt đầu  </li><li>**date_to** với kiểu dữ liệu là `string` đại diện cho ngày kết thúc  </li><li>**oa_id** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li><li>**template_id** với kiểu dữ liệu là `number` đại diện cho ID của template </li><li>**template_name** với kiểu dữ liệu là `string` đại diện cho tên của template </li><li>**type** với kiểu dữ liệu là `unknow` đại diện cho loại template  </li></ul>      |
| page `body` | object | false | <ul><li>**after** với kiểu dữ liệu là `string` đại diện cho trang trước  </li><li>**before** với kiểu dữ liệu là `string` đại diện cho trang sau  </li><li>**limit** với kiểu dữ liệu là `number` đại diện cho giới hạn </li><li>**sort** với kiểu dữ liệu là `string` đại diện cho sắp xếp </li></ul> |
- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/list-templates' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
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
  "code": "number",
  "data": {
    "paging": {
      "after": "string",
      "before": "string",
      "limit": "number",
      "next": "string",
      "prev": "string",
      "sort": "string"
    },
    "templates": [
      {
        "apply_template_quota": true,
        "created_at": "string",
        "preview_url": "string",
        "price": "number",
        "template_daily_quota": "number",
        "template_id": "number",
        "template_name": "string",
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
      }
    ]
  },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key        | Type            | Description       |
|------------- |-----------------|-------------------|
| paging         | object          |    <ul><li>**after** với kiểu dữ liệu là `string` đại diện cho ngày bắt đầu  </li><li>**before** với kiểu dữ liệu là `string` đại diện cho ngày kết thúc  </li><li>**limit** với kiểu dữ liệu là `number` đại diện cho ID của OA  </li><li>**next** với kiểu dữ liệu là `string` đại diện cho ID của template </li><li>**prev** với kiểu dữ liệu là `string` đại diện cho tên của template </li><li>**sort** với kiểu dữ liệu là `string` đại diện cho loại template  </li></ul>      |
|  templates     | array |     <ul><li>**apply_template_quota** với kiểu dữ liệu là `boolean` đại diện cho ngày bắt đầu  </li><li>**created_at** với kiểu dữ liệu là `string` đại diện cho ngày kết thúc  </li><li>**preview_url** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li><li>**price** với kiểu dữ liệu là `number` đại diện cho ID của template </li><li>**template_daily_quota** với kiểu dữ liệu là `number` đại diện cho tên của template </li><li>**template_id** với kiểu dữ liệu là `number` đại diện cho loại template  </li><li>**template_name** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li><li>**template_name** với kiểu dữ liệu là `object` đại diện cho ID của OA  </li><li>**template_quality** với kiểu dữ liệu là `UNKNOWN` đại diện cho ID của OA  </li><li>**template_remaining_quota** với kiểu dữ liệu là `number` đại diện cho ID của OA  </li><li>**template_status** với kiểu dữ liệu là `UNKNOWN` đại diện cho ID của OA  </li><li>**template_tag** với kiểu dữ liệu là `UNKNOWN` đại diện cho ID của OA  </li><li>**timeout** với kiểu dữ liệu là `number` đại diện cho ID của OA  </li><li>**type** với kiểu dữ liệu là `UNKNOWN` đại diện cho ID của OA  </li><li>**updated_at** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li></ul> | 

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



