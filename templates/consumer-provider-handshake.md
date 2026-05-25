# Consumer–Provider Handshake

## Thông tin chung

- Lab: FIT4110 Lab 03
- Ngày: 2026-05-25
- Provider team: Core Business Team (B6)
- Consumer team: AI Vision Team
- Provider service: Core Business Service
- Consumer service: AI Vision Service

## Contract

- Contract file: contracts/core-business-ai-vision.openapi.yaml
- Mock base URL: http://localhost:3001
- Auth method: Bearer JWT
- Endpoint được test:

POST /analysis/request

## Smoke test

### Request

```http
POST /analysis/request
Authorization: Bearer {{authToken}}
Content-Type: application/json
```

```json
{
  "eventId": "evt-2026-05-21-001",
  "imageUrl": "https://cdn.campus.local/images/camera-01.jpg",
  "priority": "HIGH",
  "idempotencyKey": "ai-vision-001"
}
```

### Expected response

```json
{
  "eventId": "evt-2026-05-21-001",
  "analysisId": "ana-2026-05-21-001",
  "status": "CREATED",
  "createdAt": "2026-05-21T08:00:00Z"
}
```

## Kết quả

- [X] Consumer gọi mock thành công
- [X] Consumer parse được response
- [X] Consumer xử lý lỗi provider
- [X] Có Newman report

## Ghi chú thay đổi hợp đồng

| Nội dung | Trước | Sau | Người đồng ý |
|---|---|---|---|
| Không thay đổi contract | | | Core Business & AI Vision |

## Xác nhận

Provider representative: Core Business Team

Consumer representative: AI Vision Team