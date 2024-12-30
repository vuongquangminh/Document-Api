---
sidebar_position: 24
custom_edit_url: null
---

# Message Detail

## Api Message Detail  

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/zalo/message-detail
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
- **URL**: `/api/vendor/v1/zalo/message-detail`
- **Headers**: 
  - `accept: */*`
  - `Content-Type: application/json`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: Key License
- **Body**:
  - `msg_id`: Message ID
  - `oa_id`: ID của OA

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Key License         |
| msg_id `body`         | object                | false            |     Message ID      |
| oa_id `body`         | string                | false            |     ID của OA         |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/message-detail' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Content-Type: application/json' \
  -d '{
  "msg_id": "string",
  "oa_id": "string"
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
    "campaign_id": "string",
    "created_at": "string",
    "delivery_status": "UNKNOWN",
    "delivery_time": "string",
    "error_code": "number",
    "error_message": "string",
    "fee_main": "number",
    "fee_token": "number",
    "feedback": {},
    "id": "string",
    "is_charged": true,
    "journey_id": "string",
    "msg_id": "string",
    "note": "string",
    "oa_id": "string",
    "phone": "string",
    "rate": "number",
    "sent_time": "string",
    "shop_id": "string",
    "status": "Z",
    "submit_time": "string",
    "template_data": {},
    "template_id": "number",
    "timeout": "number",
    "tracking_id": "string",
    "type": "UNKNOWN",
    "updated_at": "string",
    "user_id": "string",
    "zl_user_id": "string",
    "enable_sms_on_zns_failure": "string",
    "sms": "string"
  },
  "message": "string",
  "referentId": "string"
}
```

- **Cấu trúc data của response**

| Key          | Type            |    Description       |
|------------- |-----------------|-------------------|
| is_charged     | boolean         |    <ul><li>`True`: Tin ZNS được tính phí</li><li>`Received`: Tin ZNS không được tính phí</li></ul>   |
| campaign_id     | string         |    ID của chiến dịch   |
| created_at     | string         |    Ngày tạo   |
| delivery_status     | string         |    <ul><li>`Unkown`: Không xác định</li><li>`Received`: Đã nhận </li></ul>   |
| delivery_time     | string         |    Thời gian thiết bị của người dùng nhận được thông báo ZNS   |
| error_code     | number         |    Mã lỗi   |
| error_message     | string         |    Thông báo lỗi   |
| fee_main     | number         |    Phí chính   |
| fee_token     | number         |    Phí khởi tạo token   |
| feedback     | array         |    Phần nhận xét từ khách hàng   |
| id     | string         |    ID tin nhắn trên hệ thống của ITS   |
| journey_id     | string         | ID của journey   |
| msg_id     | string         |    ID của thông báo ZNS   |
| note     | string         |    Phần ghi chú thêm của khách hàng   |
| phone     | string         |   Số điện thoại người nhận   |
| rate     | number         |    Số sao được khách hàng đánh giá   |
| sent_time     | string         |   Thời gian gửi thông báo ZNS   |
| shop_id     | string         |    ID cửa hàng trên hệ thống của ITS   |
| status     | Z         |    Trạng thái <ul><li>`Z`:  Mới tạo</li><li>`P`: Enable</li><li>`N`: Disable</li></ul>   |
| submit_time     | string         |    Thời điểm khách hàng gửi đánh giá   |
| template_data     | object         |    Tham số tin nhắn   |
| template_id     | number         |    ID của mẫu tin   |
| timeout     | number         |    Thời gian tối đa mà hệ thống xử lý yêu cầu   |
| tracking_id     | string         |   Mã số đánh dấu lần gọi API của bạn, do bạn định nghĩa. Bạn có thể dùng `tracking_id` để đối soát mà không phụ thuộc vào `message_id` của ITS cung cấp.   |
| type     | string         |    <ul><li>`template`: ZNS thường</li><li>`journey`: ZNS  journey</li></ul>   |
| user_id     | string         |    ID người gửi tin trên hệ thống của ITS   |



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



