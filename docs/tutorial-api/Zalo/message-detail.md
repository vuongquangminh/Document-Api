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
  - `Authorization: Bearer {token}`
  - `API-KEY: {API_KEY}`
- **Parameters**:
  - `API-KEY`: (Mô tả về API-KEY)
- **Body**:
  - `msg_id`: (Mô tả dữ liệu msg_id)
  - `oa_id`: (Mô tả dữ liệu oa_id)

- **Cấu trúc request**

| Key          | Type Value            |     Required    | Description   |
|------------- |-----------------------|-----------------|---------------               |
| API-KEY `header`       | string                | true            |    Mô tả về API-KEY         |
| msg_id `body`         | object                | false            |     Mô tả về msg_id      |
| oa_id `body`         | string                | false            |     Mô tả về oa_id         |

- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/message-detail' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \

  -H 'Authorization: Bearer $accessToken' \
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
| charged     | boolean         |    Mô tả verified   |
| campaign_id     | string         |    Mô tả verified   |
| created_at     | string         |    Mô tả verified   |
| delivery_status     | UNKNOWN         |    Mô tả verified   |
| delivery_time     | string         |    Mô tả verified   |
| error_code     | number         |    Mô tả verified   |
| error_message     | string         |    Mô tả verified   |
| fee_main     | number         |    Mô tả verified   |
| fee_token     | number         |    Mô tả verified   |
| feedback     | object         |    Mô tả verified   |
| id     | string         |    Mô tả verified   |
| is_charged     | boolean         |    Mô tả verified   |
| journey_id     | string         |    Mô tả verified   |
| msg_id     | string         |    Mô tả verified   |
| note     | string         |    Mô tả verified   |
| oa_id     | string         |    Mô tả verified   |
| phone     | string         |    Mô tả verified   |
| rate     | number         |    Mô tả verified   |
| sent_time     | string         |    Mô tả verified   |
| shop_id     | string         |    Mô tả verified   |
| status     | Z         |    Mô tả verified   |
| submit_time     | string         |    Mô tả verified   |
| template_data     | object         |    Mô tả verified   |
| template_id     | number         |    Mô tả verified   |
| timeout     | number         |    Mô tả verified   |
| tracking_id     | string         |    Mô tả verified   |
| type     | UNKNOWN         |    Mô tả verified   |
| user_id     | string         |    Mô tả verified   |
| zl_user_id     | string         |    Mô tả verified   |
| enable_sms_on_zns_failure     | string         |    Mô tả verified   |
| sms     | string         |    Mô tả verified   |



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



