# Редактирование параметров магазина

## PUT /shop
- Ресурс **/shop**
- HTTP-метод **PUT**
- Тип данных **application/json, application/x-json**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Варианты ответа

```
HTTP/1.1 200 OK - Переданные значения курсов успешно сохранены
```
```
HTTP/1.1 400 Bad Request - Переданы неверные значения курсов
```
```
HTTP/1.1 403 Forbidden - Доступ запрещен. Неверная авторизация
```

### Пример запроса
```
PUT /shop
Accept: application/json
Content-Type: application/json
```

Request Body:
```json
{
  "rates": {
    "usd": 8700,
    "eur": 11570
  }
}
```

### Ответ

```
HTTP/1.1 200 OK
```

### Примеры ошибочных запросов

```
PUT /shop
Accept: application/json
Content-Type: application/json
```
Request Body:
```json
{
  "rates": {
    "usd": 8700
  }
}
```

### Ответ

```
HTTP/1.1 400 Bad Request
```
```json
{
    "errors": {
        "rates": ["Key 'EUR' is required and must not be empty"]
    }
}
```

--

Request Body:
```json
{
  "rates": {
    "usd": 8700,
    "eur": 10900
  }
}
```

### Ответ
```
HTTP/1.1 400 Bad Request
```
```json
{
    "errors": {
        "rates": [
          "'USD' field must be between 9 000 and 11 000",
          "'EUR' field must be between 11 000 and 14 000"
        ]
    }
}
```
