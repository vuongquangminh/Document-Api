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
|  templates     | array |     <ul><li>**apply_template_quota** với kiểu dữ liệu là `boolean`: <ul><li>`True`</li><li>`False`</li></ul>  </li><li>**created_at** với kiểu dữ liệu là `string`: Thời gian tạo </li><li>**price** với kiểu dữ liệu là `number`: Đơn giá của mẫu tin </li><li>**template_daily_quota** với kiểu dữ liệu là `number`: Số lượng tin ZNS có thể gửi trong 1 ngày </li><li>**template_id** với kiểu dữ liệu là `number`: ID của mẫu tin  </li><li>**template_name** với kiểu dữ liệu là `string`: Tên của mẫu tin  </li><li>**template_quality** với kiểu dữ liệu là `string`: <ul><li>`unknown`:  Không xác định</li><li>`UNDEFINED`:  Mức độ chất lượng OA chưa được xác định (trường hợp OA không gửi thông báo ZNS nào trong khung thời gian đánh giá)</li><li>`LOW`:  Mức độ chất lượng kém</li><li>`MEDIUM`:  Mức độ chất lượng trung bình</li><li>`HIGH`: Mức độ chất lượng cao</li></ul>  </li><li>**template_remaining_quota** với kiểu dữ liệu là `number`: Số lượng tin ZNS có thể gửi còn lại trong 1 ngày  </li><li>**template_status** với kiểu dữ liệu là `string`: Trạng thái mẫu tin: <ul><li>`Unkown`: Không xác định</li><li>`PENDING_REVIEW`: Đang duyệt</li><li>`DISABLE`: Bị khóa</li><li>`ENABLE`: Đã duyệt</li><li>`REJECT`: Bị từ chối</li></ul>  </li><li>**template_tag** với kiểu dữ liệu là `string`: Cấp độ mẫu tin: <ul><li>`Unkown`: Không xác định</li><li>`OTP`: Tin OTP (tag 0)</li><li>`IN_TRANSACTION`: Xác nhận/Cập nhật thông tin giao dịch (Tag 1)</li><li>`POST_TRANSACTION`: Hỗ trợ dịch vụ liên quan sau giao dịch (Tag 2)</li><li>`ACCOUNT_UPDATE`:  Cập nhật thông tin tài khoản (Tag 3)</li><li>`GENERAL_UPDATE`:  Thay đổi thông tin dịch vụ (Tag 4)</li><li>`FOLLOW_UP`:  Thông báo ưu đãi đến khách hàng cũ (Tag 5)</li></ul> </li><li>**timeout** với kiểu dữ liệu là `number`: Thời gian tính phí của mẫu tin  </li><li>**updated_at** với kiểu dữ liệu là `string`: Thời gian cập nhật  </li></ul> | 

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



