## Обновление актуальности

### PUT /pricelist/renew

Обновляет актуальность указанных позиций

- Ресурс **/pricelist/renew**
- HTTP-метод **PUT**
- Тип данных: **application/json, application/x-json**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Пример запроса

```http
PUT /pricelist/renew
Accept: application/json
Authorization: Bearer <token>
```

### Пример успешного ответ

```http
HTTP/1.1 200 OK
```
```json
[
    {
        "id": 1, 
        "dateUpdate": "2013-01-01 12:00:00"
    },
    {
        "id": 2, 
        "dateUpdate": "2013-01-01 12:00:00"
    }
]
```

### Пример запроса для обновления актуальности только указанных позиций (ID=1,2,3)

```http
PUT /pricelist/renew
Accept: application/json
Authorization: Bearer <token>
```
```json
[
    1,2,3
]
```

### Пример ответа

```http
HTTP/1.1 200 OK
```
```json
[
    {
        "all": "2013-01-01 12:00:00"
    }
]
```

### Пример ответа, если указанная позиция не существует

```
HTTP/1.1 404 Not Found
```
```json
{
    "errors": {
        99: "Not found"
    }
}
```
Если одна из указанных позиций не существует, то в этом случае ни одна позиция не обновляется.
