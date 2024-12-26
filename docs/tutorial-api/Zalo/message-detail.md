---
sidebar_position: 11
custom_edit_url: null
---

# Message Detail

## Api Message Detail lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/message-detail

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
  - `msg_id`: (Mô tả dữ liệu msg_id)
  - `oa_id`: ID của OA

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Key License         |
| msg_id `body`         | object                | false            |     Mô tả về msg_id      |
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
| charged     | boolean         |    Mô tả charged   |
| campaign_id     | string         |    Mô tả campaign_id   |
| created_at     | string         |    Mô tả created_at   |
| delivery_status     | UNKNOWN         |    Mô tả delivery_status   |
| delivery_time     | string         |    Mô tả delivery_time   |
| error_code     | number         |    Mô tả error_code   |
| error_message     | string         |    Mô tả error_message   |
| fee_main     | number         |    Mô tả fee_main   |
| fee_token     | number         |    Mô tả fee_token   |
| feedback     | object         |    Mô tả feedback   |
| id     | string         |    Mô tả id   |
| is_charged     | boolean         |    Mô tả is_charged   |
| journey_id     | string         |    Mô tả journey_id   |
| msg_id     | string         |    Mô tả msg_id   |
| note     | string         |    Mô tả note   |
| oa_id     | string         |    Mô tả oa_id   |
| phone     | string         |    Mô tả phone   |
| rate     | number         |    Mô tả rate   |
| sent_time     | string         |    Mô tả sent_time   |
| shop_id     | string         |    Mô tả shop_id   |
| status     | Z         |    Mô tả status   |
| submit_time     | string         |    Mô tả submit_time   |
| template_data     | object         |    Mô tả template_data   |
| template_id     | number         |    Mô tả template_id   |
| timeout     | number         |    Mô tả timeout   |
| tracking_id     | string         |    Mô tả tracking_id   |
| type     | UNKNOWN         |    Mô tả type   |
| user_id     | string         |    Mô tả user_id   |
| zl_user_id     | string         |    Mô tả zl_user_id   |
| enable_sms_on_zns_failure     | string         |    Mô tả enable_sms_on_zns_failure   |
| sms     | string         |    Mô tả sms   |



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



