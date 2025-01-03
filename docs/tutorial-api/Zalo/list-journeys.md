---
sidebar_position: 22
custom_edit_url: null
---

# List Journeys

## Api List Journeys  

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/zalo/list-journeys
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
- **URL**: `/api/vendor/v1/zalo/list-journeys`
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
| filter `body`         | object                | false            |     <ul><li>**charged** với kiểu dữ liệu là `boolean`: Tính phí hay không </li><li>**date_from** với kiểu dữ liệu là `string`: Ngày bắt đầu  </li><li>**date_to** với kiểu dữ liệu là `string`: Ngày kết thúc  </li><li>**is_charged** với kiểu dữ liệu là `boolean`: Tính phí hay không   </li><li>**journey_id** với kiểu dữ liệu là `string`: ID của journey  </li><li>**oa_id** với kiểu dữ liệu là `string`: ID của OA  </li><li>**phone** với kiểu dữ liệu là `string`: Số điện thoại người nhận </li><li>**status** với kiểu dữ liệu là `string`: Trạng thái <ul><li>`Z`:  Mới tạo</li><li>`P`: Enable</li><li>`N`: Disable</li></ul></li></ul>      |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/list-journeys' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Content-Type: application/json' \
  -d '{
  "filter": {
    "charged": true,
    "date_from": "string",
    "date_to": "string",
    "is_charged": true,
    "journey_id": "string",
    "oa_id": "string",
    "phone": "string",
    "status": "Z"
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
    "journeys": [
      {
        "charged": true,
        "created_at": "string",
        "error_code": "number",
        "error_message": "string",
        "expired_at": "string",
        "id": "string",
        "is_charged": true,
        "journey_id": "string",
        "journey_token": "string",
        "phone": "string",
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
| journeys         | array          |    <ul><li>**charged** với kiểu dữ liệu là `boolean`: Tính phí hay không   </li><li>**created_at** với kiểu dữ liệu là `string`: Thời gian tạo </li><li>**error_code** với kiểu dữ liệu là `number`: Mã lỗi  </li><li>**error_message** với kiểu dữ liệu là `string`: Thông báo lỗi </li><li>**expired_at** với kiểu dữ liệu là `string`: Thời gian hết hạn </li><li>**id** với kiểu dữ liệu là `string`: ID của journey trên hệ thống eTelecom  </li><li>**is_charged** với kiểu dữ liệu là `boolean`: Tính phí hay không</li><li>**journey_id** với kiểu dữ liệu là `string`: ID của journey </li><li>**journey_token** với kiểu dữ liệu là `string`: Mã hành trình được kích hoạt  </li><li>**phone** với kiểu dữ liệu là `string`: Số điện thoại người nhận  </li><li>**status** với kiểu dữ liệu là `Z`: loại template  </li><li>**updated_at** với kiểu dữ liệu là `string`: Thời gian cập nhật  </li></ul>   |

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



