---
sidebar_position: 21
custom_edit_url: null
---

# Create Template

## Api Create Template  

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/zalo/create-template
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
- **URL**: `/api/vendor/v1/zalo/create-template`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: Key License
- **Body**:
  - `oa_id`: ID của OA
  - `template_id`: ID của mẫu tin
  - `type`: Loại template

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Key License         |
| oa_id `body`         | string                | false            |     ID của OA oa_id      |
| template_id `body`         | number                | false            |     ID của mẫu tin      |
| type `body`         | unknow                | false            |     Loại template      |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/create-template' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Content-Type: application/json' \
  -d '{
  "oa_id": "string",
  "template_id": 0,
  "type": "UNKNOWN"
}'
```

### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

- **Ví dụ Response**

```json
{
  "code": "number",
  "data": {
    "price": "number",
    "apply_template_quota": true,
    "created_at": "string",
    "preview_url": "string",
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
  },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key        | Type            | Description       |
|-------------|-------------------|-----------------|
| price         | number         |    Đơn giá của mẫu tin   |
| apply_template_quota         | boolean         |    <ul><li>`True`</li><li>`False`</li></ul>   |
| created_at         | boolean         |    Thời gian tạo   |
| preview_url         | string         |    Mô tả msg_id   |
| template_daily_quota         | number         |    Số lượng tin ZNS có thể gửi trong 1 ngày   |
| template_id         | number         |    ID của mẫu tin    |
| template_name         | string         |    Tên của mẫu tin   |
| template_params         | array         |    Danh sách các thuộc tính của mẫu tin   |
| template_quality         | UNKNOWN         |    <ul><li>`unknown`:  Không xác định</li><li>`UNDEFINED`:  Mức độ chất lượng OA chưa được xác định (trường hợp OA không gửi thông báo ZNS nào trong khung thời gian đánh giá)</li><li>`LOW`:  Mức độ chất lượng kém</li><li>`MEDIUM`:  Mức độ chất lượng trung bình</li><li>`HIGH`: Mức độ chất lượng cao</li></ul>   |
| template_remaining_quota         | number         |    Số lượng tin ZNS có thể gửi còn lại trong 1 ngày   |
| template_status         | string         |    Trạng thái mẫu tin: <ul><li>`Unkown`: Không xác định</li><li>`PENDING_REVIEW`: Đang duyệt</li><li>`DISABLE`: Bị khóa</li><li>`ENABLE`: Đã duyệt</li><li>`REJECT`: Bị từ chối</li></ul>   |
| template_tag         | string         |    Cấp độ mẫu tin: <ul><li>`Unkown`: Không xác định</li><li>`OTP`: Tin OTP (tag 0)</li><li>`IN_TRANSACTION`: Xác nhận/Cập nhật thông tin giao dịch (Tag 1)</li><li>`POST_TRANSACTION`: Hỗ trợ dịch vụ liên quan sau giao dịch (Tag 2)</li><li>`ACCOUNT_UPDATE`:  Cập nhật thông tin tài khoản (Tag 3)</li><li>`GENERAL_UPDATE`:  Thay đổi thông tin dịch vụ (Tag 4)</li><li>`FOLLOW_UP`:  Thông báo ưu đãi đến khách hàng cũ (Tag 5)</li></ul>  |
| timeout         | number         |    Thời gian tính phí của mẫu tin   |
| type         | UNKNOWN         |    Mô tả msg_id   |
| updated_at         | string         |    Thời gian cập nhật   |

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



