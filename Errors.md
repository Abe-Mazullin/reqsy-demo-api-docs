# Errors

## Формат ошибки

Во всех методах ошибки возвращаются в едином формате:

```json
{
  "error": "VALIDATION_ERROR",
  "message": "The field `title` is required.",
  "details": {
    "field": "title"
  }
}
```

## Основные коды HTTP

- `200 OK` — успешное чтение данных
- `201 Created` — объект успешно создан
- `400 Bad Request` — ошибка в параметрах запроса
- `401 Unauthorized` — отсутствует или неверен токен
- `403 Forbidden` — недостаточно прав
- `404 Not Found` — объект не найден
- `409 Conflict` — конфликт состояния
- `422 Unprocessable Entity` — ошибка бизнес-валидации
- `500 Internal Server Error` — внутренняя ошибка сервиса

## Примеры ошибок

### 400

```json
{
  "error": "BAD_REQUEST",
  "message": "Invalid request format."
}
```

### 401

```json
{
  "error": "UNAUTHORIZED",
  "message": "Authorization token is required."
}
```

### 403

```json
{
  "error": "FORBIDDEN",
  "message": "You do not have access to this resource."
}
```

### 404

```json
{
  "error": "NOT_FOUND",
  "message": "The requested ticket was not found."
}
```
