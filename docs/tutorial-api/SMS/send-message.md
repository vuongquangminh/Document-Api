---
sidebar_position: 1
custom_edit_url: null

---

# Send Message

## Api Send Message  

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/sms/send-message
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
- **URL**: `/api/vendor/v1/sms/send-message`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
 
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: Key License

- **Body**:
  - `destinations`: Điểm nhận tin
  - `from`: Tên Brandname dùng để gửi tin
  - `text`: Nội dung tin
  - `scheduled`: Gửi tin đặt lịch
  - `requestId`: ID định danh của đối tác
  - `useUnicode`: Gửi tin Unicode
  - `type`: Loại gửi tin 
  - `ext`: Trường dự phòng, có thể bỏ trống.

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Key License         |
| destinations `body`         | array                | true            |     Điểm nhận tin       |
| from `body`         | string                | true            |     Tên Brandname dùng để gửi tin      |
| text `body`         | string                | true            |     Nội dung tin      |
| scheduled `body`         | 	string                | false            |     Gửi tin đặt lịch      |
| requestId `body`         | string                | false            |     ID định danh của đối tác, sẽ gửi lại trong nội dung phản hồi hoặc để trống      |
| useUnicode `body`         | string                | true            |     <ul><li>**0**: Gửi tin notUnicode</li><li>**1**: Nội dung Unicode</li><li>**2**: Tự động chuyển đổi nội dung Unicode sang notUnicodecode</li></ul>      |
| type `body`         | number                | true            |     <ul><li>**0**: Tư vấn</li><li>**1**: Quảng cáo</li><li>**2**: OTP</li></ul>      |
| ext `body`         | object                | false            |     Trường dự phòng, có thể bỏ trống      |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/sms/send-message' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \

  -H 'Content-Type: application/json' \
  -d '{
  "destinations": [
    "string"
  ],
  "from": "string",
  "text": "string",
  "scheduled": "2024-12-20T03:33:44.757Z",
  "requestId": "string",
  "useUnicode": 0,
  "type": 0,
  "ext": {}
}'
```

### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

- **Ví dụ Response**

```json
{
  "code": "number",
  "data": {
    "token": "string"
  },
  "message": "string",
  "referentId": "string"
}
```


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



