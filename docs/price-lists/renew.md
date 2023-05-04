## Обновление актуальности

### PUT /pricelist/{PositionId}/renew

Обновляет актуальность указанной или всех позиций магазина

- Ресурс **/pricelist/{PositionId}/renew**
- HTTP-метод **PUT**
- Формат ответа **JSON**

### Path-параметры

| Параметр | Тип | Описание |
|--------|--------|--------|
| position_id | string | идентификатор позиции |

### Пример запроса

```http
PUT /pricelist/1/renew
Accept: application/json
Authorization: Bearer <token>
```

### Пример успешного ответа

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

### Пример запроса для обновления актуальности всех позиций магазина

```http
PUT /pricelist/all/renew
Accept: application/json
Authorization: Bearer <token>
```

### Пример успешного ответа

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

### Пример ответа при отправке запроса с id несуществующей позиции

```http
HTTP/1.1 404 Not Found
```
```json
{
    "errors": {
        99: "Not found"
    }
}
```
