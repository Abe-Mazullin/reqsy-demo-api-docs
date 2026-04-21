# Organizations API

## Назначение

Методы раздела позволяют:

- получить список доступных организаций;
- получить карточку конкретной организации;
- обновить основные данные организации.

## GET /organizations

Возвращает список организаций, доступных текущему токену.

### Request

```http
GET /v1/organizations
Authorization: Bearer demo_token_123456
Accept: application/json
```

### Response 200

```json
{
  "organizations": [
    {
      "id": "org_demo_001",
      "name": "Demo Retail Group",
      "status": "active",
      "type": "company"
    },
    {
      "id": "org_demo_002",
      "name": "Demo Logistics",
      "status": "active",
      "type": "company"
    }
  ]
}
```

## GET /organizations/{organizationId}

Возвращает карточку организации.

### Response 200

```json
{
  "id": "org_demo_001",
  "name": "Demo Retail Group",
  "status": "active",
  "type": "company",
  "inn": "7701234567",
  "address": "Demo street 1",
  "createdAt": "2026-04-01T10:00:00Z"
}
```

## PATCH /organizations/{organizationId}

Обновляет основные данные организации.

### Request Body

```json
{
  "name": "Demo Retail Group Updated",
  "address": "Demo avenue 15"
}
```

### Response 200

```json
{
  "id": "org_demo_001",
  "name": "Demo Retail Group Updated",
  "status": "active",
  "address": "Demo avenue 15"
}
```
