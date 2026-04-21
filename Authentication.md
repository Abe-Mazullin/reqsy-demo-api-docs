# Authentication

## Общий принцип

API использует аутентификацию по Bearer Token.

Каждый защищённый запрос должен включать заголовок:

```http
Authorization: Bearer demo_token_123456
```

## Пример запроса

```http
GET /v1/me HTTP/1.1
Host: api.example.local
Authorization: Bearer demo_token_123456
Accept: application/json
```

## Пример успешного ответа

```json
{
  "id": "usr_demo_001",
  "email": "integration@example.local",
  "role": "owner",
  "organizationId": "org_demo_001"
}
```

## Возможные ошибки

### Токен не передан

```json
{
  "error": "UNAUTHORIZED",
  "message": "Authorization token is required."
}
```

### Токен некорректен

```json
{
  "error": "INVALID_TOKEN",
  "message": "The provided token is invalid."
}
```

### Токен просрочен

```json
{
  "error": "TOKEN_EXPIRED",
  "message": "The access token has expired."
}
```

## Рекомендации

- не храните токен в клиентском коде;
- используйте серверный proxy или backend-интеграцию;
- не публикуйте токен в логах;
- регулярно обновляйте секреты доступа.
