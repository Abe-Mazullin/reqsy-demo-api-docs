# Tickets API

## Назначение

Методы раздела заявок позволяют:

- получать список заявок;
- создавать заявку;
- получать карточку конкретной заявки;
- изменять статус заявки.

## GET /tickets

Возвращает список заявок.

### Query Parameters

- `organizationId`
- `locationId`
- `status`
- `limit`
- `page`

### Example

```http
GET /v1/tickets?organizationId=org_demo_001&status=new&limit=20
Authorization: Bearer demo_token_123456
```

### Response 200

```json
{
  "tickets": [
    {
      "id": "tkt_demo_1001",
      "number": 1001,
      "title": "Printer is offline",
      "status": "new",
      "organizationId": "org_demo_001",
      "locationId": "loc_demo_007",
      "createdAt": "2026-04-21T08:00:00Z",
      "updatedAt": "2026-04-21T08:00:00Z"
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 1
  }
}
```

## POST /tickets

Создаёт новую заявку.

### Request Body

```json
{
  "organizationId": "org_demo_001",
  "locationId": "loc_demo_007",
  "title": "Printer is offline",
  "description": "The printer in the front office is not responding.",
  "priority": "normal"
}
```

### Response 201

```json
{
  "ticket": {
    "id": "tkt_demo_1001",
    "number": 1001,
    "title": "Printer is offline",
    "status": "new",
    "organizationId": "org_demo_001",
    "locationId": "loc_demo_007",
    "createdAt": "2026-04-21T08:00:00Z"
  }
}
```

## GET /tickets/{ticketId}

Возвращает карточку заявки.

### Response 200

```json
{
  "id": "tkt_demo_1001",
  "number": 1001,
  "title": "Printer is offline",
  "description": "The printer in the front office is not responding.",
  "status": "in_progress",
  "organizationId": "org_demo_001",
  "locationId": "loc_demo_007",
  "createdAt": "2026-04-21T08:00:00Z",
  "updatedAt": "2026-04-21T08:30:00Z"
}
```

## PATCH /tickets/{ticketId}/status

Обновляет статус заявки.

### Request Body

```json
{
  "status": "done"
}
```

### Response 200

```json
{
  "id": "tkt_demo_1001",
  "status": "done",
  "updatedAt": "2026-04-21T09:00:00Z"
}
```
