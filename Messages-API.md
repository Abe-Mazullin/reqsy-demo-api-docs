# Messages API

## Назначение

Раздел сообщений используется для переписки внутри конкретной заявки.

## GET /tickets/{ticketId}/messages

Возвращает список сообщений по заявке.

### Response 200

```json
{
  "messages": [
    {
      "id": "msg_demo_001",
      "ticketId": "tkt_demo_1001",
      "author": {
        "id": "usr_demo_101",
        "name": "John Smith"
      },
      "content": "We have started investigating the issue.",
      "createdAt": "2026-04-21T08:10:00Z"
    }
  ]
}
```

## POST /tickets/{ticketId}/messages

Создаёт новое сообщение в заявке.

### Request Body

```json
{
  "content": "Please confirm whether the device was restarted."
}
```

### Response 201

```json
{
  "message": {
    "id": "msg_demo_002",
    "ticketId": "tkt_demo_1001",
    "content": "Please confirm whether the device was restarted.",
    "createdAt": "2026-04-21T08:12:00Z"
  }
}
```
