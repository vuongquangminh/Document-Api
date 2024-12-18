---
sidebar_position: 1
---

# Send Zns

## Api send zns lên zalo

`POST` $BASE_URL/api/vendor/v1/zalo/send-zns

### Thông tin Request

- **Method**: `POST`
- **URL**: `/api/vendor/v1/zalo/send-zns`
- **Headers**: 
  - `Content-Type: multipart/form-data`
  - `Authorization: Bearer {token}`
- **Body**:
  - `API-KEY`: (Dữ liệu file cần upload)
  - `accessToken`: (Mô tả ngắn về file nếu có)
  - `type`: (Mô tả ngắn về file nếu có)
  - `oaId`: (Mô tả ngắn về file nếu có)


- **Cấu trúc body của request**

| Field        | Type            |     Required    | Description   |
|------------- |-----------------|-----------------|---------------               |
| API-KEY      | string          | True            |    Đối với các API sử dụng cho Shop thì API key:<api_key>.Thông tin base_url của Shop         |
| accessToken  | string          | True            |    Accecss tokentoken           |
| type         | string          | True            |     typw của nónó          |
| oaId         | string          | True            |      123123123123123123         |

- **Ví dụ Request**
```json
{
  "API-KEY": "string",
  "accessToken": "string",
  "type": "string",
  "oaId ": "string"
}
 ```
### Thông tin Response

Mô tả: Mô tả dữ liệu trả về dùng làm gì 

```json
{
  "file": "string"
}
```

- **Cấu trúc body của request**

| Field        | Type            |     Required    | Description       |
|------------- |-----------------|-----------------|-------------------|
| file         | string          | True            |    Mô tả msg_id   |




