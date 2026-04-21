# Examples

## Получение списка организаций

```bash
curl --request GET \
  --url https://api.example.local/v1/organizations \
  --header 'Authorization: Bearer demo_token_123456' \
  --header 'Accept: application/json'
```

## Получение списка локаций

```bash
curl --request GET \
  --url 'https://api.example.local/v1/locations?organizationId=org_demo_001' \
  --header 'Authorization: Bearer demo_token_123456' \
  --header 'Accept: application/json'
```

## Создание заявки

```bash
curl --request POST \
  --url https://api.example.local/v1/tickets \
  --header 'Authorization: Bearer demo_token_123456' \
  --header 'Content-Type: application/json' \
  --data '{
    "organizationId": "org_demo_001",
    "locationId": "loc_demo_007",
    "title": "Printer is offline",
    "description": "The printer in the front office is not responding."
  }'
```

## Получение сообщений по заявке

```bash
curl --request GET \
  --url https://api.example.local/v1/tickets/tkt_demo_1001/messages \
  --header 'Authorization: Bearer demo_token_123456' \
  --header 'Accept: application/json'
```

## Отправка сообщения по заявке

```bash
curl --request POST \
  --url https://api.example.local/v1/tickets/tkt_demo_1001/messages \
  --header 'Authorization: Bearer demo_token_123456' \
  --header 'Content-Type: application/json' \
  --data '{
    "content": "Please confirm whether the device was restarted."
  }'
```
