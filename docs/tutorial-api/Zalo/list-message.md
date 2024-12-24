---
sidebar_position: 14
custom_edit_url: null
---

# List Message

## Api List Message lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/list-messages

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/list-messages`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (Mô tả về API-KEY)
- **Body**:
  - `filter`: (Mô tả dữ liệu filter)
  - `paging`: (Mô tả dữ liệu paging)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| filter `body`         | object                | false            |     <ul><li>**charged** với kiểu dữ liệu là `boolean` đại diện cho ID của template </li><li>**campaign_id** với kiểu dữ liệu là `string` đại diện cho ngày bắt đầu  </li><li>**date_from** với kiểu dữ liệu là `string` đại diện cho ngày kết thúc  </li><li>**date_to** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li><li>**delivery_status** với kiểu dữ liệu là `unknow` đại diện cho tên của template </li><li>**is_charged** với kiểu dữ liệu là `boolean` đại diện cho ID của OA  </li><li>**journey_id** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li><li>**msg_id** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li><li>**msg_type** với kiểu dữ liệu là `unknow` đại diện cho ID của OA  </li><li>**oa_id** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li><li>**phone** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li><li>**status** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li><li>**template_id** với kiểu dữ liệu là `number` đại diện cho ID của OA  </li><li>**tracking_id** với kiểu dữ liệu là `string` đại diện cho ID của OA  </li></ul>      |
| page `body` | object | false | <ul><li>**after** với kiểu dữ liệu là `string` đại diện cho trang trước  </li><li>**before** với kiểu dữ liệu là `string` đại diện cho trang sau  </li><li>**limit** với kiểu dữ liệu là `number` đại diện cho giới hạn </li><li>**sort** với kiểu dữ liệu là `string` đại diện cho sắp xếp </li></ul> |
- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/list-messages' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \

  -H 'Authorization: Bearer $accessToken' \
  -H 'Content-Type: application/json' \
  -d '{
  "filter": {
    "charged": true,
    "campaign_id": "string",
    "date_from": "string",
    "date_to": "string",
    "delivery_status": "UNKNOWN",
    "is_charged": true,
    "journey_id": "string",
    "msg_id": "string",
    "msg_type": "UNKNOWN",
    "oa_id": "string",
    "phone": "string",
    "status": "Z",
    "template_id": 0,
    "tracking_id": "string"
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
  "filter": {
    "charged": true,
    "campaign_id": "string",
    "date_from": "string",
    "date_to": "string",
    "delivery_status": "UNKNOWN",
    "is_charged": true,
    "journey_id": "string",
    "msg_id": "string",
    "msg_type": "UNKNOWN",
    "oa_id": "string",
    "phone": "string",
    "status": "Z",
    "template_id": 0,
    "tracking_id": "string"
  },
  "paging": {
    "after": "string",
    "before": "string",
    "limit": 0,
    "sort": "string"
  }
}
```

- **Cấu trúc data của response**

| Key        | Type            | Description       |
|------------- |-----------------|-------------------|
| charged         | boolean          |    Mô tả msg_id   |
| campaign_id         | string          |    Mô tả msg_id   |
| date_from         | string          |    Mô tả msg_id   |
| date_to         | string          |    Mô tả msg_id   |
| delivery_status         | UNKNOWN          |    Mô tả msg_id   |
| is_charged         | boolean          |    Mô tả msg_id   |
| journey_id         | string          |    Mô tả msg_id   |
| msg_id         | string          |    Mô tả msg_id   |
| msg_type         | UNKNOWN          |    Mô tả msg_id   |
| oa_id         | string          |    Mô tả msg_id   |
| phone         | string          |    Mô tả msg_id   |
| status         | Z          |    Mô tả msg_id   |
| template_id         | number          |    Mô tả msg_id   |
| charged         | string          |    Mô tả msg_id   |
| tracking_id         | string          |    Mô tả msg_id   |

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



