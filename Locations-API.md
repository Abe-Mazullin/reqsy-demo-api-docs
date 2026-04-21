# Locations API

## Назначение

Локации используются для привязки заявок к конкретным объектам.

## GET /locations

Возвращает список локаций.

### Query Parameters

- `organizationId` — фильтрация по организации
- `limit` — ограничение количества записей

### Example

```http
GET /v1/locations?organizationId=org_demo_001&limit=20
Authorization: Bearer demo_token_123456
```

### Response 200

```json
{
  "locations": [
    {
      "id": "loc_demo_007",
      "title": "Head Office",
      "address": "Demo street 10"
    },
    {
      "id": "loc_demo_008",
      "title": "Warehouse A",
      "address": "Industrial road 5"
    }
  ]
}
```

## GET /locations/{locationId}

Возвращает карточку локации.

### Response 200

```json
{
  "id": "loc_demo_007",
  "organizationId": "org_demo_001",
  "title": "Head Office",
  "address": "Demo street 10",
  "status": "active"
}
```
