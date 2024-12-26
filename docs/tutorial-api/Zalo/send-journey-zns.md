---
sidebar_position: 4
custom_edit_url: null
---

# Send Journey Zns

## Api send journey zns lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/send-journey-zns

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/send-journey-zns`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: Key License
- **Body**:
  - `journey_id`: ID journey token
  - `oa_id`: ID của OA
  - `phone`: Số điện thoại người nhận
  - `template_data`: Các thuộc tính của mẫu tin mà bạn đã đăng ký với Zalo
  - `template_id`: ID của mẫu tin
  - `tracking_id`: Mã số đánh dấu lần gọi API của bạn, do bạn định nghĩa

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Key License         |
| journey_id `body`         | string                | false            |     ID journey token          |
| oa_id `body`         | string                | false            |      ID của OA         |
| phone `body`        | string          | false            |    Số điện thoại người nhận           |
| template_data `body`        | object          | false            |    Các thuộc tính của mẫu tin mà bạn đã đăng ký với Zalo **Lưu ý**: Cấu trúc **template_data** được quy định riêng ứng với từng mẫu tin           |
| template_id `body`        | number          | false            |    ID của mẫu tin           |
| tracking_id `body`        | string          | false            |    Mã số đánh dấu lần gọi API của bạn, do bạn định nghĩa. Bạn có thể dùng **tracking_id** để đối soát mà không phụ thuộc vào **message_id** của eTelecom cung cấp           |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/send-journey-zns' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Content-Type: application/json' \
  -d '{
  "journey_id": "string",
  "oa_id": "string",
  "phone": "string",
  "template_data": {},
  "template_id": 0,
  "tracking_id": "string"
}'
```

### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

- **Ví dụ Response**

```json
{
  "code": "number",
  "data": {
    "created_at": "dateTime",
    "delivery_time": "dateTime",
    "id": "number",
    "is_charged": "boolean",
    "journey_id": "string",
    "msg_id": "string",
    "msg_type": "journey",
    "phone": "string",
    "price": "number",
    "sent_time": "dateTime",
    "template_id": "number",
    "timeout": "number",
    "tracking_id": "string",
    "updated_at": "dateTime"
  },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key          | Type            |    Description       |
|------------- |-----------------|-------------------|
| id     | number         |    ID tin nhắn trên hệ thống của eTelecom   |
| shop_id     | number         |    ID cửa hàng trên hệ thống của eTelecom   |
| user_id     | number         |    ID người gửi tin trên hệ thống của eTelecom   |
| campaign_id     | number         |    ID của chiến dịch   |
| delivery_status     | string         |    <ul><li>`Unkown`:  Không xác định</li><li>`Received`: Đã nhận</li><li>`Seen`: Đã xem</li></ul>   |
| delivery_time     | string         |    Thời gian thiết bị của người dùng nhận được thông báo ZNS   |
| error_code     | number         |    Mã lỗi   |
| error_message     | string         |   Thông báo lỗi   |
| fee_main     | number         |    Phí chính   |
| fee_token     | number         |    Phí khởi tạo token   |
| is_charged     | boolean         |    <ul><li>`True`: Tin ZNS được tính phí</li><li>`False`: Tin ZNS không được tính phí</li></ul>   |
| journey_id     | string         |    ID của journey   |
| msg_id     | string         |    ID của thông báo ZNS   |
| type     | string         |    <ul><li>`template`: Tin ZNS được tính phí</li><li>`journey`: Tin ZNS không được tính phí</li></ul>   |
| status     | string         |    Trạng thái <ul><li>`Z`:  Mới tạo</li><li>`P`: Enable</li><li>`N`: Disable</li></ul>   |
| template_data     | object         |    Tham số tin nhắn   |
| phone     | string         |    Số điện thoại người nhận   |
| sent_time     | string         |    Thời gian gửi thông báo ZNS   |
| template_id     | number         |    ID của mẫu tin   |
| timeout     | number         |    Thời gian tối đa mà hệ thống xử lý yêu cầu   |
| tracking_id     | string         |    Mã số đánh dấu lần gọi API của bạn, do bạn định nghĩa. Bạn có thể dùng `tracking_id` để đối soát mà không phụ thuộc vào `message_id` của eTelecom cung cấp.   |
| updated_at     | string         |    Ngày cập nhật   |
| created_at     | string         |    Ngày tạo   |





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



