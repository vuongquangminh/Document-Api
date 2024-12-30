---
sidebar_position: 7
custom_edit_url: null
---

# List Followers

## Api List Followers  

:::tip API
  `POST` __$BASE_URL__/api/vendor/v1/zalo/list-followers
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
- **URL**: `/api/vendor/v1/zalo/list-followers`
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
| filter `body`         | object                | false            |     <ul><li>**assigned_user_id** với kiểu dữ liệu là `string`: ID nhân viên được gán</li><li>**date_from** với kiểu dữ liệu là `string`: Ngày bắt đầu</li><li>**date_to** với kiểu dữ liệu là `string`: Ngày kết thúc </li><li>**gender** với kiểu dữ liệu là `enum `: <ul><li>`unknown`</li><li>`male`</li><li>`female`</li><li>`other`</li></ul></li><li>**has_conversation** với kiểu dữ liệu là `boolean`: <ul><li>`True`: Có cuộc hội thoại</li><li>`False`: Không có cuộc hội thoại</li></ul>  </li><li>**name** với kiểu dữ liệu là `string`: Tên người dùng Zalo </li><li>**oa_id** với kiểu dữ liệu là `string`: ID của OA  </li><li>**phone** với kiểu dữ liệu là `string`: Số điện thoại người dùng </li><li>**state** với kiểu dữ liệu là `string`: <ul><li>`follow`: Đã quan tâm</li><li>`unfollow`: Chưa quan tâm</li></ul>  </li><li>**tags** với kiểu dữ liệu là `array`: Nhãn được gán cho người dùng  </li><li>**zl_user_id** với kiểu dữ liệu là `string`: ID người dùng Zalo</li><li>**zl_user_ids** với kiểu dữ liệu là `array`: Danh sách ID người dùng Zalo</li></ul>      |
- **Ví dụ Request**

```bash
curl -X 'POST' \
  'https://cpaas.interits.com/api/vendor/v1/zalo/list-followers' \
  -H 'accept: */*' \
  -H 'API-KEY: $API_KEY' \
  -H 'Content-Type: application/json' \
  -d '{
  "filter": {
    "assigned_user_id": "string",
    "date_from": "string",
    "date_to": "string",
    "gender": "UNKNOWN",
    "has_conversation": true,
    "name": "string",
    "oa_id": "string",
    "phone": "string",
    "state": "FOLLOW",
    "tags": [
      "string"
    ],
    "zl_user_id": "string",
    "zl_user_ids": [
      "string"
    ]
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
    "followers": [
      {
        "assigned_user_id": "string",
        "avatar": "string",
        "avatars": {
          "120": "string",
          "240": "string"
        },
        "created_at": "string",
        "full_name": "string",
        "gender": "UNKNOWN",
        "has_conversation": true,
        "id": "string",
        "last_conversation": {
          "attachments": {
            "audio": [
              {
                "url": "string"
              }
            ],
            "business_card": [
              {
                "description": "string",
                "thumbnail": "string",
                "url": "string"
              }
            ],
            "file": [
              {
                "checksum": "string",
                "name": "string",
                "size": "string",
                "type": "string",
                "url": "string"
              }
            ],
            "gif": [
              {
                "thumbnail": "string",
                "url": "string"
              }
            ],
            "image": [
              {
                "thumbnail": "string",
                "url": "string"
              }
            ],
            "link": [
              {
                "description": "string",
                "thumbnail": "string",
                "url": "string"
              }
            ],
            "location": [
              {
                "latitude": "string",
                "longitude": "string"
              }
            ],
            "sticker": [
              {
                "id": "string",
                "url": "string"
              }
            ],
            "video": [
              {
                "description": "string",
                "thumbnail": "string",
                "url": "string"
              }
            ]
          },
          "direction": "IN",
          "message": "string",
          "sent_time": "string",
          "type": "UNKNOWN"
        },
        "oa_id": "string",
        "phone": "string",
        "shared_info": {
          "address": "string",
          "city": "string",
          "district": "string",
          "name": "string",
          "phone": "string",
          "ward": "string"
        },
        "shop_id": "string",
        "state": "FOLLOW",
        "tags_and_notes_info": {
          "notes": [
            {
              "items": "string"
            }
          ],
          "tag_names": [
            {
              "items": "string"
            }
          ]
        },
        "updated_at": "string",
        "zl_user_id": "string",
        "zl_user_id_by_app": "string"
      }
    ],
    "paging": {
      "after": "string",
      "before": "string",
      "limit": "number"v,
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
|  followers | array | <ul><li>**assigned_user_id** với kiểu dữ liệu là `string`: ID nhân viên được gán  </li><li>**avatar** với kiểu dữ liệu là `string`: Ảnh đại diện người dùng  </li><li>**avatars** với kiểu dữ liệu là `object`: ID của OA  </li><li>**created_at** với kiểu dữ liệu là `string`: Thời điểm ghi nhận tương tác </li><li>**full_name** với kiểu dữ liệu là `string`: Tên người dùng </li><li>**id** với kiểu dữ liệu là `string`: ID người dùng trên eTelecom</li><li>**gender** với kiểu dữ liệu là `enum`: <ul><li>`unknown`</li><li>`male`</li><li>`female`</li><li>`other`</li></ul></li><li>**has_conversation** với kiểu dữ liệu là `boolean`: <ul><li>`True`: Có cuộc hội thoại</li><li>`False`: Không có cuộc hội thoại</li></ul> </li><li>**last_conversation** với kiểu dữ liệu là `object`: tên của template </li><li>**oa_id** với kiểu dữ liệu là `string`: ID của OA</li><li>**phone** với kiểu dữ liệu là `string`: Số điện thoại người dùng</li><li>**shared_info** với kiểu dữ liệu là `object`: Người dùng đồng ý chia sẻ thông tin: <ul><li>**address** với kiểu dữ liệu là `string`: Địa chỉ </li><li>**city** với kiểu dữ liệu là `string`: Thành phố </li><li>**district** với kiểu dữ liệu là `string`: Quận, Huyện </li><li>**ward** với kiểu dữ liệu là `string`: Phường </li><li>**name** với kiểu dữ liệu là `string`: Tên người dùng Zalo </li></ul> </li><li>**shop_id** với kiểu dữ liệu là `string`: ID shop trên eTelecom</li><li>**state** với kiểu dữ liệu là `enum`: <ul><li>`follow`: Đã quan tâm</li><li>`unfollow`: Chưa quan tâm</li></ul>  </li><li>**tag** với kiểu dữ liệu là `array`: Nhãn được gán cho người dùng </li><li>**tags_and_notes_info** với kiểu dữ liệu là `object`: tên của template </li><li>**updated_at** với kiểu dữ liệu là `string`: Thời điểm update</li><li>**zl_user_id** với kiểu dữ liệu là `string`: ID người dùng Zalo</li><li>**zl_user_id_by_app** với kiểu dữ liệu là `string`: ID người dùng Zalo theo app</li></ul> |

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



