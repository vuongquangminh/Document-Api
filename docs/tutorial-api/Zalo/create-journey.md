---
sidebar_position: 20
custom_edit_url: null
---

# Create Journey

## Api Create Journey  

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/zalo/create-journey
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
- **URL**: `/api/vendor/v1/zalo/create-journey`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: Key License
- **Body**:
  - `oa_id`: ID của OA
  - `phone`: Số điện thoại của người nhận.
  
    :::info Lưu ý
      SĐT phải được liên kết với tài khoản Zalo
    :::

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Key License         |
| oa_id `body`         | string                | false            |     ID của OA      |
| phone `body`         | string                | false            |     Số điện thoại của người nhận      |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/create-journey' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Content-Type: application/json' \
  -d '{
  "oa_id": "string",
  "phone": "string"
}'
```

### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

- **Ví dụ Response**

```json
{
  "code": "number",
  "data": {
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
  },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key        | Type             | Description       |
|------------- |-----------------|------------------|
| id         | string           |    ID của journey trên hệ thống của ITS   |
| journey_id         | string           |    ID của journey   |
| journey_token         | string           |    Mã hành trình được kích hoạt   |
| expired_at         | string           |    Thời gian hết hạn   |
| phone         | string           |    Số điện thoại người nhận   |
| charged         | boolean           |    Mô tả msg_id   |
| created_at         | string           |    Thời gian tạo    |
| error_code         | number           |    Mã lỗi   |
| error_message         | string           |    Thông tin lỗi   |
| is_charged         | boolean           |    Tính phí hay không tính phí   |
| status         | Z           |    Trạng thái <ul><li>`Z`:  Mới tạo</li><li>`P`: Enable</li><li>`N`: Disable</li></ul>   |
| updated_at         | string           |    Thời gian cập nhật   |

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

