# Webhooks

## Назначение

Webhook-события позволяют внешней системе получать уведомления об изменениях без постоянного опроса API.

## Поддерживаемые события

В демонстрационной версии используются следующие примеры:

- `ticket.created`
- `ticket.updated`
- `ticket.status_changed`
- `ticket.message_created`

## Пример события

```json
{
  "event": "ticket.status_changed",
  "timestamp": "2026-04-21T09:00:00Z",
  "data": {
    "ticketId": "tkt_demo_1001",
    "status": "done",
    "organizationId": "org_demo_001"
  }
}
```

## Подпись запроса

Для проверки подлинности webhook можно использовать заголовок подписи, например:

```http
X-Demo-Signature: sha256=abcdef123456
```

## Рекомендации

- принимайте webhook только по HTTPS;
- проверяйте подпись;
- обрабатывайте повторную доставку событий идемпотентно;
- сохраняйте журнал входящих webhook-событий.
