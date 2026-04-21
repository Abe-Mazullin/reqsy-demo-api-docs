# Quick Start

## Шаг 1. Получите доступ к API

Для работы с API интегратор получает:

- базовый URL API;
- токен доступа;
- список доступных методов;
- при необходимости — секрет для webhook-подписей.

В демонстрационной версии используются тестовые значения:

```text
Base URL: https://api.example.local/v1
Token: demo_token_123456
Webhook Secret: demo_webhook_secret
```

## Шаг 2. Добавьте токен в заголовок

Каждый запрос к защищённым методам должен содержать заголовок:

```http
Authorization: Bearer demo_token_123456
```

## Шаг 3. Проверьте доступ

Первым запросом обычно выполняют проверку текущего контекста:

```http
GET /me
```

Пример ответа:

```json
{
  "id": "usr_demo_001",
  "role": "owner",
  "email": "integration@example.local",
  "organizationId": "org_demo_001"
}
```

## Шаг 4. Получите организации и локации

Перед созданием заявки внешняя система обычно:

1. получает список организаций;
2. выбирает нужную организацию;
3. получает список доступных локаций;
4. использует нужную локацию при создании заявки.

## Шаг 5. Создайте заявку

Минимальный пример:

```http
POST /tickets
Content-Type: application/json
Authorization: Bearer demo_token_123456
```

```json
{
  "organizationId": "org_demo_001",
  "locationId": "loc_demo_007",
  "title": "Printer is offline",
  "description": "The printer in the front office is not responding."
}
```

## Шаг 6. Отслеживайте изменения

Изменения можно получать:

- опросом API;
- через webhook-события;
- через периодическую синхронизацию.
