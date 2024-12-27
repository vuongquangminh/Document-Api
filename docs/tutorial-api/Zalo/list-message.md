---
sidebar_position: 14
custom_edit_url: null
---

# List Message

## Api List Message  

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/zalo/list-messages
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
- **URL**: `/api/vendor/v1/zalo/list-messages`
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
| filter `body`         | object                | false            |     <ul><li>**charged** với kiểu dữ liệu là `boolean`: Tính phí hay không</li><li>**campaign_id** với kiểu dữ liệu là `string`: ID của chiến dịch  </li><li>**date_from** với kiểu dữ liệu là `string`: Ngày bắt đầu  </li><li>**date_to** với kiểu dữ liệu là `string`: Ngày kết thúc  </li><li>**delivery_status** với kiểu dữ liệu là `enum`: <ul><li>`unknown`</li><li>`received`</li><li>`seen`</li></ul> </li><li>**is_charged** với kiểu dữ liệu là `boolean`: Tính phí hay không  </li><li>**journey_id** với kiểu dữ liệu là `string`: ID của journey  </li><li>**msg_id** với kiểu dữ liệu là `string`: ID của thông báo ZNS </li><li>**msg_type** với kiểu dữ liệu là `enum`: <ul><li>`unknown`</li><li>`template`</li><li>`journey`</li><li>`uid`</li></ul>  </li><li>**oa_id** với kiểu dữ liệu là `string`: ID của OA  </li><li>**phone** với kiểu dữ liệu là `string`: Số điện thoại người nhận  </li><li>**status** với kiểu dữ liệu là `enum`:<ul><li>`Z`: Mới tạo</li><li>`P`: Enable</li><li> `N`: Disable</li></ul></li><li>**template_id** với kiểu dữ liệu là `number`: ID của mẫu tin</li><li>**tracking_id** với kiểu dữ liệu là `string`: Mã số đánh dấu lần gọi API của bạn, do bạn định nghĩa. Bạn có thể dùng `tracking_id` để đối soát mà không phụ thuộc vào `message_id` của ITS cung cấp.</li></ul> |
- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/list-messages' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
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
| id         | string          |    ID tin nhắn trên hệ thống của ITS   |
| shop_id         | string          |  ID cửa hàng trên hệ thống của ITS   |
| user_id         | string          |    ID người gửi tin trên hệ thống của ITS   |
| campaign_id         | string          |    ID của chiến dịch   |
| delivery_status         | UNKNOWN          |    <ul><li>`Unkown`: Không xác định</li><li>`Received`: Đã nhận </li><li>`Seen`: Đã xem</li></ul>   |
| delivery_time         | string          |    Thời gian thiết bị của người dùng nhận được thông báo ZNS   |
| error_code         | number          |    Mã lỗi   |
| error_message         | string          |   Thông báo lỗi   |
| fee_main         | number          |    Phí chính   |
| fee_token         | number          |    Phí khởi tạo token   |
| is_charged         | boolean          |    <ul><li>`True`: Tin ZNS được tính phí</li><li>`False`: Tin ZNS không được tính phí</li></ul>   |
| journey_id         | string          |    ID của journey   |
| msg_id         | string          |    ID của thông báo ZNS   |
| type         | UNKNOWN          |    <ul><li>`template`: Tin ZNS được tính phí</li><li>`journey`: Tin ZNS không được tính phí</li></ul>   |
| status         | Z          |    Trạng thái <ul><li>`Z`:  Mới tạo</li><li>`P`: Enable</li><li>`N`: Disable</li></ul>   |
| rate         | number          |    Số sao được khách hàng đánh giá   |
| note         | string          |    Phần ghi chú thêm của khách hàng   |
| feedback         | array          |    Phần nhận xét của khách hàng   |
| submit_time         | string          |    Thời điểm khách hàng gửi đánh giá   |
| template_data         | object          |    Tham số tin nhắn   |
| phone         | string          |    Số điện thoại người nhận   |

| sent_time         | string          |    Thời gian gửi thông báo ZNS   |
| template_id         | number          |    ID của mẫu tin   |
| timeout         | number          |    Thời gian tối đa mà hệ thống xử lý yêu cầu   |
| tracking_id         | string          |    Mã số đánh dấu lần gọi API của bạn, do bạn định nghĩa. Bạn có thể dùng `tracking_id` để đối soát mà không phụ thuộc vào `message_id` của ITS cung cấp.   |
| updated_at         | string          |    Ngày cập nhật   |
| created_at         | string          |    Ngày tạo   |


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



